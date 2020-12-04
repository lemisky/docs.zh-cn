---
title: 中断性变更：Vector2.Lerp 和 Vector4.Lerp 的行为变更
description: 了解核心 .NET 库中的以下 .NET 5.0 中断性变更：Vector2.Lerp 和 Vector4.Lerp 的实现已更改，以正确考虑浮点数舍入误差。
ms.date: 11/01/2020
ms.openlocfilehash: 8e363a559dba8b7563c40637c47f101d59951216
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759107"
---
# <a name="behavior-change-for-vector2lerp-and-vector4lerp"></a><span data-ttu-id="eda2f-103">Vector2.Lerp 和 Vector4.Lerp 的行为变更</span><span class="sxs-lookup"><span data-stu-id="eda2f-103">Behavior change for Vector2.Lerp and Vector4.Lerp</span></span>

<span data-ttu-id="eda2f-104"><xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=nameWithType> 和 <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=nameWithType> 的实现已更改，以正确考虑浮点数舍入误差。</span><span class="sxs-lookup"><span data-stu-id="eda2f-104">The implementation of <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=nameWithType> and <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=nameWithType> changed to correctly account for a floating-point rounding error.</span></span>

## <a name="change-description"></a><span data-ttu-id="eda2f-105">更改描述</span><span class="sxs-lookup"><span data-stu-id="eda2f-105">Change description</span></span>

<span data-ttu-id="eda2f-106">以前，<xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=nameWithType> 和 <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=nameWithType> 实现为 `value1 + (value2 - value1) * amount`。</span><span class="sxs-lookup"><span data-stu-id="eda2f-106">Previously, <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=nameWithType> and <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=nameWithType> were implemented as `value1 + (value2 - value1) * amount`.</span></span> <span data-ttu-id="eda2f-107">但是，由于浮点数舍入误差，在 `amount` 为 `1.0f` 时，此算法不会始终返回 `value2`。</span><span class="sxs-lookup"><span data-stu-id="eda2f-107">However, due to a floating-point rounding error, this algorithm doesn't always return `value2` when `amount` is `1.0f`.</span></span>

<span data-ttu-id="eda2f-108">在 .NET 5.0 及更高版本中，该实现使用与 <xref:System.Numerics.Vector3.Lerp(System.Numerics.Vector3,System.Numerics.Vector3,System.Single)?displayProperty=nameWithType> 相同的算法，即 `(value1 * (1.0f - amount)) + (value2 * amount)`。</span><span class="sxs-lookup"><span data-stu-id="eda2f-108">In .NET 5.0 and later, the implementation uses the same algorithm as <xref:System.Numerics.Vector3.Lerp(System.Numerics.Vector3,System.Numerics.Vector3,System.Single)?displayProperty=nameWithType>, which is `(value1 * (1.0f - amount)) + (value2 * amount)`.</span></span> <span data-ttu-id="eda2f-109">此算法可正确考虑舍入误差。</span><span class="sxs-lookup"><span data-stu-id="eda2f-109">This algorithm correctly accounts for the rounding error.</span></span> <span data-ttu-id="eda2f-110">现在，当 `amount` 为 `1.0f` 时，结果为精确的 `value2`。</span><span class="sxs-lookup"><span data-stu-id="eda2f-110">Now, when `amount` is `1.0f`, the result is precisely `value2`.</span></span> <span data-ttu-id="eda2f-111">更新的算法还允许使用 <xref:System.MathF.FusedMultiplyAdd%2A?displayProperty=nameWithType>（如果可用）自由地优化算法。</span><span class="sxs-lookup"><span data-stu-id="eda2f-111">The updated algorithm also allows the algorithm to be freely optimized using <xref:System.MathF.FusedMultiplyAdd%2A?displayProperty=nameWithType> when it's available.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="eda2f-112">引入的版本</span><span class="sxs-lookup"><span data-stu-id="eda2f-112">Version introduced</span></span>

<span data-ttu-id="eda2f-113">5.0</span><span class="sxs-lookup"><span data-stu-id="eda2f-113">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="eda2f-114">建议操作</span><span class="sxs-lookup"><span data-stu-id="eda2f-114">Recommended action</span></span>

<span data-ttu-id="eda2f-115">无需执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="eda2f-115">No action is necessary.</span></span> <span data-ttu-id="eda2f-116">但是，如果你想要保留旧行为，则可以实现自己的 `Lerp` 函数，使用先前的算法 `value1 + (value2 - value1) * amount`。</span><span class="sxs-lookup"><span data-stu-id="eda2f-116">However, if you want to maintain the old behavior, you can implement your own `Lerp` function that uses the previous algorithm of `value1 + (value2 - value1) * amount`.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="eda2f-117">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="eda2f-117">Affected APIs</span></span>

- <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=fullName>
- <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=fullName>

<!--

#### Category

Core .NET libraries

### Affected APIs

- `M:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)`
- `M:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)`

-->
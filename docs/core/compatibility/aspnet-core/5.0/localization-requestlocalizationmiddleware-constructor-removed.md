---
title: 中断性变更：本地化：请求本地化中间件中删除了已过时的构造函数
description: 了解 ASP.NET Core 5.0 中的以下中断性变更：本地化：请求本地化中间件中删除了已过时的构造函数
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 53dd0f25078dae140d34d6d21d66983f78b8bdb0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759271"
---
# <a name="localization-obsolete-constructor-removed-in-request-localization-middleware"></a><span data-ttu-id="d3ff9-103">本地化：请求本地化中间件中删除了已过时的构造函数</span><span class="sxs-lookup"><span data-stu-id="d3ff9-103">Localization: Obsolete constructor removed in request localization middleware</span></span>

<span data-ttu-id="d3ff9-104">缺少 <xref:Microsoft.Extensions.Logging.ILoggerFactory> 参数的 <xref:Microsoft.AspNetCore.Localization.RequestLocalizationMiddleware> 构造函数[在此提交中](https://github.com/dotnet/aspnetcore/commit/ba8c6ccf6fd3eeb7fc42a159d362b15eae4fb3a0)被标记为已过时。</span><span class="sxs-lookup"><span data-stu-id="d3ff9-104">The <xref:Microsoft.AspNetCore.Localization.RequestLocalizationMiddleware> constructor that lacks an <xref:Microsoft.Extensions.Logging.ILoggerFactory> parameter was marked as obsolete [in this commit](https://github.com/dotnet/aspnetcore/commit/ba8c6ccf6fd3eeb7fc42a159d362b15eae4fb3a0).</span></span> <span data-ttu-id="d3ff9-105">ASP.NET Core 5.0 中删除了已过时的构造函数。</span><span class="sxs-lookup"><span data-stu-id="d3ff9-105">In ASP.NET Core 5.0, the obsolete constructor was removed.</span></span> <span data-ttu-id="d3ff9-106">有关讨论，请参阅 [dotnet/aspnetcore#23785](https://github.com/dotnet/aspnetcore/issues/23785)。</span><span class="sxs-lookup"><span data-stu-id="d3ff9-106">For discussion, see [dotnet/aspnetcore#23785](https://github.com/dotnet/aspnetcore/issues/23785).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="d3ff9-107">引入的版本</span><span class="sxs-lookup"><span data-stu-id="d3ff9-107">Version introduced</span></span>

<span data-ttu-id="d3ff9-108">5.0 预览版 8</span><span class="sxs-lookup"><span data-stu-id="d3ff9-108">5.0 Preview 8</span></span>

## <a name="old-behavior"></a><span data-ttu-id="d3ff9-109">旧行为</span><span class="sxs-lookup"><span data-stu-id="d3ff9-109">Old behavior</span></span>

<span data-ttu-id="d3ff9-110">存在已过时的 `RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions<RequestLocalizationOptions>)` 构造函数。</span><span class="sxs-lookup"><span data-stu-id="d3ff9-110">The obsolete `RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions<RequestLocalizationOptions>)` constructor exists.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="d3ff9-111">新行为</span><span class="sxs-lookup"><span data-stu-id="d3ff9-111">New behavior</span></span>

<span data-ttu-id="d3ff9-112">不存在已过时的 `RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions<RequestLocalizationOptions>)` 构造函数。</span><span class="sxs-lookup"><span data-stu-id="d3ff9-112">The obsolete `RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions<RequestLocalizationOptions>)` constructor doesn't exist.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="d3ff9-113">更改原因</span><span class="sxs-lookup"><span data-stu-id="d3ff9-113">Reason for change</span></span>

<span data-ttu-id="d3ff9-114">此更改可确保请求本地化中间件始终有权访问记录器。</span><span class="sxs-lookup"><span data-stu-id="d3ff9-114">This change ensures that the request localization middleware always has access to a logger.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="d3ff9-115">建议操作</span><span class="sxs-lookup"><span data-stu-id="d3ff9-115">Recommended action</span></span>

<span data-ttu-id="d3ff9-116">在手动构造 `RequestLocalizationMiddleware` 实例时，在构造函数中传递 `ILoggerFactory` 实例。</span><span class="sxs-lookup"><span data-stu-id="d3ff9-116">When manually constructing an instance of `RequestLocalizationMiddleware`, pass an `ILoggerFactory` instance in the constructor.</span></span> <span data-ttu-id="d3ff9-117">如果在该上下文中没有可用的有效 `ILoggerFactory` 实例，请考虑为中间件构造函数传递 <xref:Microsoft.Extensions.Logging.Abstractions.NullLoggerFactory> 实例。</span><span class="sxs-lookup"><span data-stu-id="d3ff9-117">If a valid `ILoggerFactory` instance isn't available in that context, consider passing the middleware constructor a <xref:Microsoft.Extensions.Logging.Abstractions.NullLoggerFactory> instance.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="d3ff9-118">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="d3ff9-118">Affected APIs</span></span>

[<span data-ttu-id="d3ff9-119">RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions\<RequestLocalizationOptions>)</span><span class="sxs-lookup"><span data-stu-id="d3ff9-119">RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions\<RequestLocalizationOptions>)</span></span>](/dotnet/api/microsoft.aspnetcore.localization.requestlocalizationmiddleware.-ctor?view=aspnetcore-3.1#Microsoft_AspNetCore_Localization_RequestLocalizationMiddleware__ctor_Microsoft_AspNetCore_Http_RequestDelegate_Microsoft_Extensions_Options_IOptions_Microsoft_AspNetCore_Builder_RequestLocalizationOptions__)

<!--

### Category

ASP.NET Core

### Affected APIs

`M:Microsoft.AspNetCore.Localization.RequestLocalizationMiddleware.#ctor(Microsoft.AspNetCore.Http.RequestDelegate,Microsoft.Extensions.Options.IOptions{Microsoft.AspNetCore.Builder.RequestLocalizationOptions})`

-->
---
description: 了解详细信息： ICorDebugHeapSegmentEnum：： Next 方法
title: ICorDebugHeapSegmentEnum::Next 方法
ms.date: 03/30/2017
api_name:
- Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapSegmentEnum::Next
helpviewer_keywords:
- ICorDebugHeapSegmentEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugHeapSegmentEnum interface [.NET Framework debugging]
ms.assetid: 51625fd0-7399-49c7-b22b-5dfb05451fe6
topic_type:
- apiref
ms.openlocfilehash: 8d2ddfb4df82969fa9cf580ed8a7f903f9d6c260
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803670"
---
# <a name="icordebugheapsegmentenumnext-method"></a>ICorDebugHeapSegmentEnum::Next 方法

获取指定数量的 [COR_SEGMENT](cor-segment-structure.md) 实例，这些实例包含有关托管堆的内存区域的信息。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_SEGMENT segments[],
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>参数  

 celt  
 中要检索的段数。  
  
 段  
 弄指针数组，其中每个都指向一个 [COR_SEGMENT](cor-segment-structure.md) 对象，该对象提供有关托管堆中的内存区域的信息。  
  
 pceltFetched  
 弄一个指针，指向在中实际返回的 [COR_SEGMENT](cor-segment-structure.md) 对象的数量 `segments` 。 如果 `celt` 为 1，此值可能为 `null`。  
  
## <a name="remarks"></a>备注  
  
## <a name="requirements"></a>要求  

 **平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICorDebugHeapSegmentEnum 接口](icordebugheapsegmentenum-interface.md)
- [调试接口](debugging-interfaces.md)

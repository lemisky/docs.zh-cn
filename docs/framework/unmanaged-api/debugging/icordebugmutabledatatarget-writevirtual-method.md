---
description: 了解详细信息： ICorDebugMutableDataTarget：： WriteVirtual 方法
title: ICorDebugMutableDataTarget::WriteVirtual 方法
ms.date: 03/30/2017
ms.assetid: 80833648-58a7-491a-8dc8-9a48e9bb3adc
ms.openlocfilehash: 3f3400456b7af51f4b24d7e14e35d641f03a8bfd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637815"
---
# <a name="icordebugmutabledatatargetwritevirtual-method"></a>ICorDebugMutableDataTarget::WriteVirtual 方法

将内存写入目标进程地址空间。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT WriteVirtual(  
   [in] CORDB_ADDRESS address,  
   [in, size_is(bytesRequested)] const BYTE * pBuffer,  
   [in] ULONG32 bytesRequested);  
```  
  
## <a name="parameters"></a>参数  

 `address`  
 [in] 要在此处写入 `pBuffer` 的内容的地址。  
  
 `pBuffer`  
 [in] 指向包含要写入字节的字节数组的指针。  
  
 `address`  
 [in] `pBuffer` 中的字节数。  
  
## <a name="return-value"></a>返回值  

 若成功，则为`S_OK`若失败，则为 `HRESULT`。  
  
## <a name="remarks"></a>备注  

 如果无法写入任何字节，方法调用失败且不更改目标地址空间中的任何字节。 （否则，目标状态不一致，从而使进一步的调试不可靠。）  
  
## <a name="requirements"></a>要求  

 **平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICorDebugMutableDataTarget 接口](icordebugmutabledatatarget-interface.md)
- [调试接口](debugging-interfaces.md)

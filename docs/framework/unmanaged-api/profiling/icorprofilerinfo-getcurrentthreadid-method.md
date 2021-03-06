---
description: 了解详细信息： ICorProfilerInfo：： GetCurrentThreadID 方法
title: ICorProfilerInfo::GetCurrentThreadID 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetCurrentThreadID
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetCurrentThreadID
helpviewer_keywords:
- GetCurrentThreadID method, ICorProfilerInfo interface [.NET Framework profiling]
- ICorProfilerInfo::GetCurrentThreadID method [.NET Framework profiling]
ms.assetid: 39bbdb30-6a7a-4202-8da3-67ae9a0ab3a8
topic_type:
- apiref
ms.openlocfilehash: 562c6cb61f13e9ab568d18c7d179872cbc7cdb06
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2021
ms.locfileid: "99647634"
---
# <a name="icorprofilerinfogetcurrentthreadid-method"></a>ICorProfilerInfo::GetCurrentThreadID 方法

获取当前线程的 ID （如果它是托管线程）。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetCurrentThreadID(  
    [out] ThreadID *pThreadId);  
```  
  
## <a name="parameters"></a>参数  

 `pThreadId`  
 弄指向托管线程的返回 ID 的指针。  
  
## <a name="remarks"></a>备注  

 如果当前线程是内部运行时线程或其他非托管线程，则 `GetCurrentThreadID` 返回 CORPROF_E_NOT_MANAGED_THREAD 作为 HRESULT，并且参数的返回值 `pThreadId` 将为 null。  
  
## <a name="requirements"></a>要求  

 **平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICorProfilerInfo 接口](icorprofilerinfo-interface.md)

---
description: 了解详细信息： ISymENCUnmanagedMethod：： GetLineFromOffset 方法
title: ISymENCUnmanagedMethod::GetLineFromOffset 方法
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetLineFromOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetLineFromOffset
helpviewer_keywords:
- GetLineFromOffset method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetLineFromOffset method [.NET Framework debugging]
ms.assetid: cc09bad2-fb34-4d13-a521-6ec7b1a1d915
topic_type:
- apiref
ms.openlocfilehash: 18fe942b509340c89a4c3044e02bf8e9d952f91d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2021
ms.locfileid: "99737956"
---
# <a name="isymencunmanagedmethodgetlinefromoffset-method"></a>ISymENCUnmanagedMethod::GetLineFromOffset 方法

获取与偏移量关联的行信息。 如果 offset 参数 (`dwOffset`) 不是序列点，则此方法将获取与上一个偏移量关联的行信息。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetLineFromOffset(  
     [in]  ULONG32   dwOffset,  
     [out] ULONG32*  pline,  
     [out] ULONG32*  pcolumn,  
     [out] ULONG32*  pendLine,  
     [out] ULONG32*  pendColumn,  
     [out] ULONG32*  pdwStartOffset);  
```  
  
## <a name="parameters"></a>参数  

 `dwOffset`  
 中一个 `ULONG32` 包含偏移量的。  
  
 `pline`  
 弄指向接收行的的指针 `ULONG32` 。  
  
 `pcolumn`  
 弄指向接收列的的指针 `ULONG32` 。  
  
 `pendLine`  
 弄指向 `ULONG32` 的指针，该指针接收结束行。  
  
 `pendColumn`  
 弄指向的指针 `ULONG32` ，该指针接收结束列。  
  
 `pdwStartOffset`  
 弄指向 `ULONG32` 的指针，该指针接收关联的序列点。  
  
## <a name="return-value"></a>返回值  

 如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。  
  
## <a name="requirements"></a>要求  

 **标头：** CorSym，CorSym  
  
## <a name="see-also"></a>请参阅

- [ISymENCUnmanagedMethod 接口](isymencunmanagedmethod-interface.md)

---
description: 了解详细信息： IAssemblyCache：： UninstallAssembly 方法
title: IAssemblyCache::UninstallAssembly 方法
ms.date: 03/30/2017
api_name:
- IAssemblyCache.UninstallAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache::UninstallAssembly
helpviewer_keywords:
- UninstallAssembly method [.NET Framework fusion]
- IAssemblyCache::UninstallAssembly method [.NET Framework fusion]
ms.assetid: 973b2c44-8dfc-40c1-9035-10f4846627e9
topic_type:
- apiref
ms.openlocfilehash: d50108b9090b4250e8a6cec1d9b5c54bb78dee9c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760896"
---
# <a name="iassemblycacheuninstallassembly-method"></a>IAssemblyCache::UninstallAssembly 方法

从全局程序集缓存中卸载指定的程序集。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT UninstallAssembly (  
    [in] DWORD dwFlags,  
    [in] LPCWSTR pszAssemblyName,  
    [in] LPCFUSION_INSTALL_REFERENCE pRefData,  
    [out, optional] ULONG *pulDisposition  
);  
```  
  
## <a name="parameters"></a>参数  

 `dwFlags`  
 中在合成 .idl 中定义的标志。  
  
 `pszAssemblyName`  
 中要卸载的程序集的名称。  
  
 `pRefData`  
 中一个 [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) 结构，它包含程序集的安装数据。  
  
 `pulDisposition`  
 [out，optional]在合成 .idl 中定义的一个处置值。 可能的值如下所示：  
  
- IASSEMBLYCACHE_UNINSTALL_DISPOSITION_UNINSTALLED (1)   
  
- IASSEMBLYCACHE_UNINSTALL_DISPOSITION_STILL_IN_USE (2)   
  
- IASSEMBLYCACHE_UNINSTALL_DISPOSITION_ALREADY_UNINSTALLED (3)   
  
- IASSEMBLYCACHE_UNINSTALL_DISPOSITION_DELETE_PENDING (4)   
  
- IASSEMBLYCACHE_UNINSTALL_DISPOSITION_HAS_INSTALL_REFERENCES (5)   
  
- IASSEMBLYCACHE_UNINSTALL_DISPOSITION_REFERENCE_NOT_FOUND (6)   
  
## <a name="requirements"></a>要求  

 **平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** 合成。h  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [IAssemblyCache 接口](iassemblycache-interface.md)

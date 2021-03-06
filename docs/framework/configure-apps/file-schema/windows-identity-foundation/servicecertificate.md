---
description: 了解详细信息： <serviceCertificate>
title: <serviceCertificate>
ms.date: 03/30/2017
ms.assetid: 42c7f291-2ec3-43c5-8872-35897ff3c660
author: BrucePerlerMS
ms.openlocfilehash: d9940fd96667211b1f9fd672b824af84e0d5143a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2021
ms.locfileid: "99725319"
---
# \<serviceCertificate>

配置用于加密和解密令牌的 x.509 证书。  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceCertificate>**  
  
## <a name="syntax"></a>语法  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  

 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  

 无  
  
### <a name="child-elements"></a>子元素  
  
|元素|说明|  
|-------------|-----------------|  
|[\<certificateReference>](certificatereference.md)|指定用于在证书存储中查找和验证 x.509 证书的设置。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|说明|  
|-------------|-----------------|  
|[\<federationConfiguration>](federationconfiguration.md)|包含配置 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) 和 <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) 的设置。|  
  
## <a name="example"></a>示例  

 下面的 XML 演示如何使用 \<serviceCertificate> 元素。 XML 是从示例获取的 `CustomToken` 。  
  
```xml  
<serviceCertificate>  
  <certificateReference x509FindType="FindBySubjectName" findValue="localhost" storeLocation="LocalMachine" storeName="My"/>  
</serviceCertificate>  
```

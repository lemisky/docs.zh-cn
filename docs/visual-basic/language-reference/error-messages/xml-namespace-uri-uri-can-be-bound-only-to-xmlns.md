---
description: 了解详细信息： BC31183： XML 命名空间 URI `http://www.w3.org/XML/1998/namespace` ; 只能绑定到 "xmlns"
title: XML 命名空间 URI“<uri>”可只绑定到“xmlns”
ms.date: 07/20/2015
f1_keywords:
- bc31183
- vbc31183
helpviewer_keywords:
- BC31183
ms.assetid: 0ab1dbce-8397-4959-b2cd-f58798b051a0
ms.openlocfilehash: e6a552f4754a12b8e80e5333232d0c48432f7a63
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2021
ms.locfileid: "99701386"
---
# <a name="bc31183-xml-namespace-uri-httpwwww3orgxml1998namespace-can-be-bound-only-to-xmlns"></a>BC31183： XML 命名空间 URI `http://www.w3.org/XML/1998/namespace` ; 只能绑定到 "xmlns"

URI `http://www.w3.org/XML/1998/namespace` 用于 XML 命名空间声明。 此 URI 是保留命名空间，不能包含在 XML 命名空间声明中。

 **错误 ID：** BC31183

## <a name="to-correct-this-error"></a>更正此错误

删除 XML 命名空间声明，或将 URI 替换 `http://www.w3.org/XML/1998/namespace` 为有效的命名空间 URI。

## <a name="see-also"></a>请参阅

- [Imports 语句（XML 命名空间）](../statements/imports-statement-xml-namespace.md)
- [XML 文本](../xml-literals/index.md)
- [XML](../../programming-guide/language-features/xml/index.md)

---
title: Benutzerdefiniert (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.custom
dev_langs:
- C++
helpviewer_keywords:
- custom attributes, defining
ms.assetid: 3abac928-4d55-4ea6-8cf6-8427a4ad79f1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e55fd4ad47470a86a0a3d61cc847c20fb21768e8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="custom-c"></a>custom (C++)
Definiert die Metadaten für ein Objekt in der Typbibliothek.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      [ custom(  
   uuid,   
   value  
) ];  
```  
  
#### <a name="parameters"></a>Parameter  
 *UUID*  
 Eine eindeutige ID.  
  
 *Wert*  
 Ein Wert, der eine Variante abgelegt werden kann.  
  
## <a name="remarks"></a>Hinweise  
 Die **benutzerdefinierte** C++-Attribut bewirkt, dass die Informationen in der Typbibliothek versetzt werden soll. Sie benötigen ein Tool, das den benutzerdefinierten Wert aus der Typbibliothek liest.  
  
 Die **benutzerdefinierte** Attribut hat die gleiche Funktionalität wie die [benutzerdefinierte](http://msdn.microsoft.com/library/windows/desktop/aa366766) MIDL-Attribut.  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|Nicht-COM- `interface`, **Klasse**, `enum`s, `idl_module` Methoden, die Schnittstellenmember, die Parameter für die Benutzeroberfläche, `typedef`s, **Union**s, `struct`s|  
|**Wiederholbar**|Ja|  
|**Erforderliche Attribute**|**Co-Klasse** (wenn auf die Klasse verwendet wird)|  
|**Ungültige Attribute**|Keiner|  
  
 Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [IDL-Attribute](../windows/idl-attributes.md)   
 [Eigenständige Attribute](../windows/stand-alone-attributes.md)   
 [TypeDef, Enum, Union- und Struct-Attribute](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Parameterattribute](../windows/parameter-attributes.md)   
 [Methodenattribut](../windows/method-attributes.md)   
 [Klassenattribute](../windows/class-attributes.md)   
 [Schnittstellenattribut](../windows/interface-attributes.md)   

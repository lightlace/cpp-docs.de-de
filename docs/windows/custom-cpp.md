---
title: "custom (C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.custom"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "custom attributes, defining"
ms.assetid: 3abac928-4d55-4ea6-8cf6-8427a4ad79f1
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# custom (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Definiert Metadaten für ein Objekt in der Typbibliothek.  
  
## Syntax  
  
```  
  
      [ custom(  
   uuid,   
   value  
) ];  
```  
  
#### Parameter  
 *uuid*  
 Eine eindeutige ID.  
  
 *Wert*  
 Ein Wert, der in eine Variante abgelegt werden kann.  
  
## Hinweise  
 Das Attribut **Benutzerdefiniert** C\+\+ Informationen in die Typbibliothek wird eingefügt werden soll.  Sie benötigen ein Tool, das den benutzerdefinierten Wert aus der Typbibliothek liest.  
  
 Das **Benutzerdefiniert**\-Attribut verfügt über die gleichen Funktionen wie das [Benutzerdefiniert](http://msdn.microsoft.com/library/windows/desktop/aa366766) MIDL\-Attribut.  
  
## Anforderungen  
  
### Attribut\-Kontext  
  
|||  
|-|-|  
|**Betrifft**|Nicht\-COM `interface`, **Klasse**, `enum`s `idl_module`\-Schnittstellenmember, Schnittstellen, Methoden, Parameter `typedef`s **Union**s `struct`s|  
|**Wiederholbar**|Ja|  
|**Erforderliche Attribute**|**coclass** \(wenn Sie auf Klasse verwendet werden\)|  
|**Ungültige Attribute**|None|  
  
 Weitere Informationen über das kontexte finden Sie unter [Attribut\-Kontexte](../windows/attribute-contexts.md).  
  
## Siehe auch  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Stand\-Alone Attributes](../windows/stand-alone-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Parameter Attributes](../windows/parameter-attributes.md)   
 [Method Attributes](../windows/method-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Interface Attributes](../windows/interface-attributes.md)   
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)
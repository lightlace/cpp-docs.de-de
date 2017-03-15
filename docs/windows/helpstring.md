---
title: "helpstring | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.helpstring"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "helpstring attribute [C++]"
ms.assetid: 0401e905-a63e-4fad-98d0-d1efea111966
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# helpstring
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt eine Zeichenfolge an, durch die das zugehörige Element beschrieben wird.  
  
## Syntax  
  
```  
  
      [ helpstring(  
   "string"  
) ]  
```  
  
#### Parameter  
 `string`  
 Der Text der Hilfezeichenfolge.  
  
## Hinweise  
 Das Attribut **helpstring** C\+\+ verfügt über die gleichen Funktionen wie das [helpstring](http://msdn.microsoft.com/library/windows/desktop/aa366856) MIDL\-Attribut.  
  
## Beispiel  
 Weitere Informationen finden Sie im Beispiel für [defaultvalue](../windows/defaultvalue.md) als Beispiel zur Verwendung **helpstring**verwendet.  
  
## Anforderungen  
  
### Attribut\-Kontext  
  
|||  
|-|-|  
|**Betrifft**|`interface`, `typedef`, Methoden, Eigenschaften, **Klasse**|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|None|  
|**Ungültige Attribute**|None|  
  
 Weitere Informationen finden Sie unter [Attribut\-Kontexte](../windows/attribute-contexts.md).  
  
## Siehe auch  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Interface Attributes](../windows/interface-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Method Attributes](../windows/method-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [helpfile](../windows/helpfile.md)   
 [helpcontext](../windows/helpcontext.md)   
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)
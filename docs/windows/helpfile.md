---
title: "helpfile | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.helpfile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "helpfile attribute"
ms.assetid: d75161c1-1363-4019-ae09-e7e3b8a3971e
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# helpfile
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Legt den Namen der Hilfedatei für eine Typbibliothek fest.  
  
## Syntax  
  
```  
  
      [ helpfile(  
   "filename"  
) ]  
```  
  
#### Parameter  
 *filename*  
 Der Name der Datei, die die Hilfethemen enthält.  
  
## Hinweise  
 Das Attribut **helpfile** C\+\+ verfügt über die gleichen Funktionen wie das [helpfile](http://msdn.microsoft.com/library/windows/desktop/aa366853) MIDL\-Attribut.  
  
## Beispiel  
 Weitere Informationen finden Sie im Beispiel für [Modul](../windows/module-cpp.md) als Beispiel zur Verwendung **helpfile**verwendet.  
  
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
 [helpcontext](../windows/helpcontext.md)   
 [helpstring](../windows/helpstring.md)   
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)
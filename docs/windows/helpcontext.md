---
title: "helpcontext | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.helpcontext"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "helpcontext attribute"
ms.assetid: 6fbb022d-a4b7-4989-a02f-7f18a9b0ad96
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# helpcontext
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt eine Kontext\-ID an, die der Benutzer Informationen über dieses Element in der Hilfedatei können.  
  
## Syntax  
  
```  
  
      [ helpcontext(  
   id  
) ]  
```  
  
#### Parameter  
 `id`  
 Die Kontext\-ID des Hilfethemas.  Weitere Informationen finden Sie unter [HTML\-Hilfe: Kontextbezogene Hilfe für Programme](../mfc/html-help-context-sensitive-help-for-your-programs.md) Informationen zu Kontext ID.  
  
## Hinweise  
 Das Attribut **helpcontext** C\+\+ verfügt über die gleichen Funktionen wie das [helpcontext](http://msdn.microsoft.com/library/windows/desktop/aa366851) MIDL\-Attribut.  
  
## Beispiel  
 Weitere Informationen finden Sie im Beispiel für [defaultvalue](../windows/defaultvalue.md) als Beispiel zur Verwendung **helpcontext**verwendet.  
  
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
 [helpstring](../windows/helpstring.md)   
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)
---
title: "last_is"
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
  - "vc-attr.last_is"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "last_is attribute"
ms.assetid: 9e045ac0-fa38-4249-af55-67bde5d0a58c
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# last_is
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt den Index des letzten gesendet werden sollen, Arrayelements an.  
  
## Syntax  
  
```  
  
      [ last_is(  
   "expression"  
) ]  
```  
  
#### Parameter  
 *expression*  
 Eine oder mehrere C\-Sprache Ausdrücke.  Leere Argument slots sind zulässig.  
  
## Hinweise  
 Das Attribut **last\_is** C\+\+ verfügt über die gleichen Funktionen wie das [last\_is](http://msdn.microsoft.com/library/windows/desktop/aa367066) MIDL\-Attribut.  
  
## Beispiel  
 Weitere Informationen finden Sie unter [first\_is](../windows/first-is.md) als ein Beispiel dafür, wie Sie einen Abschnitt eines Arrays angibt.  
  
## Anforderungen  
  
### Attribut\-Kontext  
  
|||  
|-|-|  
|**Betrifft**|Feld in `struct`**Union**, Schnittstellen oder Parameter, Schnittstellenmethode|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|None|  
|**Ungültige Attribute**|None|  
  
 Weitere Informationen finden Sie unter [Attribut\-Kontexte](../windows/attribute-contexts.md).  
  
## Siehe auch  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Parameter Attributes](../windows/parameter-attributes.md)   
 [first\_is](../windows/first-is.md)   
 [max\_is](../windows/max-is.md)   
 [length\_is](../windows/length-is.md)   
 [size\_is](../windows/size-is.md)   
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)
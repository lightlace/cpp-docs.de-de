---
title: "max_is"
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
  - "vc-attr.max_is"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "max_is attribute"
ms.assetid: 7c851f5c-6649-4d77-a792-247c37d8f560
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# max_is
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Legt den Höchstwert für einen gültigen Arrayindex.  
  
## Syntax  
  
```  
  
      [ max_is(  
   "expression"  
) ]  
```  
  
#### Parameter  
 *expression*  
 Eine oder mehrere C\-Sprache Ausdrücke.  Leere Argument slots sind zulässig.  
  
## Hinweise  
 Das Attribut **max\_is** C\+\+ verfügt über die gleichen Funktionen wie das [max\_is](http://msdn.microsoft.com/library/windows/desktop/aa367074) MIDL\-Attribut.  
  
## Anforderungen  
  
### Attribut\-Kontext  
  
|||  
|-|-|  
|**Betrifft**|Feld in `struct`**Union**, Schnittstellen oder Parameter, Schnittstellenmethode|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|None|  
|**Ungültige Attribute**|**size\_is**|  
  
 Weitere Informationen finden Sie unter [Attribut\-Kontexte](../windows/attribute-contexts.md).  
  
## Beispiel  
 Weitere Informationen finden Sie unter [first\_is](../windows/first-is.md) als ein Beispiel dafür, wie Sie einen Abschnitt eines Arrays angibt.  
  
## Siehe auch  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Parameter Attributes](../windows/parameter-attributes.md)   
 [first\_is](../windows/first-is.md)   
 [last\_is](../windows/last-is.md)   
 [length\_is](../windows/length-is.md)   
 [size\_is](../windows/size-is.md)   
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)
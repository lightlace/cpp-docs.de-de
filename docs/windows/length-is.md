---
title: "length_is | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.length_is"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "length_is attribute"
ms.assetid: 1d99b883-84bb-4b1e-b098-eb780fc94f40
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# length_is
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt die Anzahl der zu sendenden auf Arrayelemente.  
  
## Syntax  
  
```  
  
      [ length_is(  
   "expression"  
) ]  
```  
  
#### Parameter  
 *expression*  
 Eine oder mehrere C\-Sprache Ausdrücke.  Leere Argument slots sind zulässig.  
  
## Hinweise  
 Das Attribut **length\_is** C\+\+ verfügt über die gleichen Funktionen wie das [length\_is](http://msdn.microsoft.com/library/windows/desktop/aa367068) MIDL\-Attribut.  
  
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
 [last\_is](../windows/last-is.md)   
 [size\_is](../windows/size-is.md)   
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)
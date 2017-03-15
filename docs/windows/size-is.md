---
title: "size_is | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.size_is"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "size_is attribute"
ms.assetid: 70192d09-f6c5-4d52-b3fe-303f8cb10aa5
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# size_is
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Geben Sie die Größe des zugeordneten Speichers für sortierte Zeiger, sortierte Zeiger auf sortierten Zeigern und einzel\- oder mehrdimensionalen Felder an.  
  
## Syntax  
  
```  
  
      [ size_is(  
   "expression"  
) ]  
```  
  
#### Parameter  
 *expression*  
 Die Größe des Arbeitsspeichers belegt für sortierte Zeiger.  
  
## Hinweise  
 Das Attribut **size\_is** C\+\+ verfügt über die gleichen Funktionen wie das [size\_is](http://msdn.microsoft.com/library/windows/desktop/aa367164) MIDL\-Attribut.  
  
## Beispiel  
 Weitere Informationen finden Sie im Beispiel für [first\_is](../windows/first-is.md) für ein Beispiel dafür, wie Sie einen Abschnitt eines Arrays angibt.  
  
## Anforderungen  
  
### Attribut\-Kontext  
  
|||  
|-|-|  
|**Betrifft**|Feld in `struct`**Union**, Schnittstellen oder Parameter, Schnittstellenmethode|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|None|  
|**Ungültige Attribute**|**max\_is**|  
  
 Weitere Informationen über das kontexte finden Sie unter [Attribut\-Kontexte](../windows/attribute-contexts.md).  
  
## Siehe auch  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Parameter Attributes](../windows/parameter-attributes.md)   
 [first\_is](../windows/first-is.md)   
 [last\_is](../windows/last-is.md)   
 [max\_is](../windows/max-is.md)   
 [length\_is](../windows/length-is.md)   
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)
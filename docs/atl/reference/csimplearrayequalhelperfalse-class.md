---
title: "CSimpleArrayEqualHelperFalse Class"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "ATL.CSimpleArrayEqualHelperFalse<T>"
  - "ATL::CSimpleArrayEqualHelperFalse"
  - "ATL.CSimpleArrayEqualHelperFalse"
  - "ATL::CSimpleArrayEqualHelperFalse<T>"
  - "CSimpleArrayEqualHelperFalse"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSimpleArrayEqualHelperFalse class"
ms.assetid: 6918af6f-d23d-49eb-8482-c44272f5ffeb
caps.latest.revision: 19
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# CSimpleArrayEqualHelperFalse Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse ist eine Hilfe für die [CSimpleArray](../../atl/reference/csimplearray-class.md)\-Klasse.  
  
## Syntax  
  
```  
  
      template <  
   class T   
>   
class CSimpleArrayEqualHelperFalse  
```  
  
#### Parameter  
 `T`  
 Eine abgeleitete Klasse.  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CSimpleArrayEqualHelperFalse::IsEqual](../Topic/CSimpleArrayEqualHelperFalse::IsEqual.md)|\(Statische\) Gibt falsch.|  
  
## Hinweise  
 Diese Merkmalklasse ist eine Ergänzung zur `CSimpleArray`\-Klasse.  Sie gibt immer false zurück und zusätzlich, ruft `ATLASSERT` mit einem Argument des false auf, wenn eine verwiesen wird.  In Situationen, in denen der Übereinstimmungstest nicht ausreichend definiert wird, kann diese Klasse enthaltenen Elementen eines Arrays, um für die meisten Methoden ordnungsgemäß funktioniert jedoch in einer klar definierte Weise für Methoden fehl, die von Vergleichen wie [CSimpleArray::Find](../Topic/CSimpleArray::Find.md) abhängen.  
  
## Anforderungen  
 **Header:** atlsimpcoll.h  
  
## Siehe auch  
 [CSimpleArrayEqualHelper Class](../../atl/reference/csimplearrayequalhelper-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)
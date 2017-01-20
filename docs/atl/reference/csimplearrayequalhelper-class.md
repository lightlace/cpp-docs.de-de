---
title: "CSimpleArrayEqualHelper Class"
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
  - "CSimpleArrayEqualHelper"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSimpleArrayEqualHelper class"
ms.assetid: a2b55d89-78c9-42ef-842c-5304c6d20ad6
caps.latest.revision: 19
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# CSimpleArrayEqualHelper Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse ist eine Hilfe für die [CSimpleArray](../../atl/reference/csimplearray-class.md)\-Klasse.  
  
## Syntax  
  
```  
  
      template <  
   class T   
>  
class CSimpleArrayEqualHelper  
```  
  
#### Parameter  
 `T`  
 Eine abgeleitete Klasse.  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CSimpleArrayEqualHelper::IsEqual](../Topic/CSimpleArrayEqualHelper::IsEqual.md)|\(Statische\) Tests zwei `CSimpleArray`\-Objektelemente für Gleichheit.|  
  
## Hinweise  
 Diese Merkmalklasse ist eine Ergänzung zur `CSimpleArray`\-Klasse.  Sie stellt eine Methode zum Vergleichen von zwei Elementen bereit, die in einem `CSimpleArray`\-Objekt gespeichert werden.  Standardmäßig werden die Elemente mithilfe **operator\=\(\)** verglichen, jedoch, wenn das Array Typen der komplexen Daten enthält, die ihren eigenen Gleichheitsoperator enthalten, müssen Sie diese Klasse überschreiben.  
  
## Anforderungen  
 **Header:** atlsimpcoll.h  
  
## Siehe auch  
 [CSimpleArray Class](../../atl/reference/csimplearray-class.md)   
 [CSimpleArrayEqualHelperFalse Class](../../atl/reference/csimplearrayequalhelperfalse-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)
---
title: "CSimpleMapEqualHelperFalse Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CSimpleMapEqualHelperFalse"
  - "CSimpleMapEqualHelperFalse"
  - "ATL.CSimpleMapEqualHelperFalse"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSimpleMapEqualHelperFalse class"
ms.assetid: a873eea3-e130-45cc-a476-61ee79511c3b
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CSimpleMapEqualHelperFalse Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse ist eine Hilfe für die [CSimpleMap](../../atl/reference/csimplemap-class.md)\-Klasse.  
  
## Syntax  
  
```  
  
template < class TKey, class TVal > class CSimpleMapEqualHelperFalse  
  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CSimpleMapEqualHelperFalse::IsEqualKey](../Topic/CSimpleMapEqualHelperFalse::IsEqualKey.md)|\(Statisch\) testet zwei Schlüssel für Gleichheit.|  
|[CSimpleMapEqualHelperFalse::IsEqualValue](../Topic/CSimpleMapEqualHelperFalse::IsEqualValue.md)|\(Statische\) Gibt falsch.|  
  
## Hinweise  
 Diese Merkmalklasse ist eine Ergänzung zur `CSimpleMap`\-Klasse.  Sie stellt eine Methode zum Vergleichen von zwei Elemente bereit, die im `CSimpleMap`\-Objekt enthalten, werden von speziell zwei Wertselementen oder zwei Schlüsselelementen.  
  
 Der Wertsvergleich gibt immer false zurück, und zusätzlich, ruft `ATLASSERT` mit einem Argument des false auf, wenn eine verwiesen wird.  In Situationen, in denen der Übereinstimmungstest nicht ausreichend definiert wird, kann diese Klasse eine Zuordnung, die Schlüssel enthält, die für die meisten Methoden ordnungsgemäß funktioniert jedoch in einer klar definierte Weise für Methoden fehl, die von Vergleichen wie [CSimpleMap::FindVal](../Topic/CSimpleMap::FindVal.md) abhängen.  
  
## Anforderungen  
 **Header:** atlsimpcoll.h  
  
## Siehe auch  
 [CSimpleMapEqualHelper Class](../../atl/reference/csimplemapequalhelper-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)
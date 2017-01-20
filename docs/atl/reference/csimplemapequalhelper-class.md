---
title: "CSimpleMapEqualHelper Class"
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
  - "CSimpleMapEqualHelper"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSimpleMapEqualHelper class"
ms.assetid: 9bb2968a-d609-405c-8272-ff3b42df6164
caps.latest.revision: 20
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# CSimpleMapEqualHelper Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse ist eine Hilfe für die [CSimpleMap](../../atl/reference/csimplemap-class.md)\-Klasse.  
  
## Syntax  
  
```  
  
      template <  
   class TKey,  
   class TVal   
>  
class CSimpleMapEqualHelper  
```  
  
#### Parameter  
 `TKey`  
 Das Schlüsselelement.  
  
 `TVal`  
 Das Wertselement.  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CSimpleMapEqualHelper::IsEqualKey](../Topic/CSimpleMapEqualHelper::IsEqualKey.md)|\(Statisch\) testet zwei Schlüssel für Gleichheit.|  
|[CSimpleMapEqualHelper::IsEqualValue](../Topic/CSimpleMapEqualHelper::IsEqualValue.md)|\(Statisch\) testet Gleichheit zweier Werte.|  
  
## Hinweise  
 Diese Merkmalklasse ist eine Ergänzung zur `CSimpleMap`\-Klasse.  Sie stellt Methoden zum Vergleichen von zwei `CSimpleMap`\-Objektelementen \(insbesondere, Schlüssel und die Wertskomponenten\) für Gleichheit bereit.  Standardmäßig werden die Schlüssel und Werte mithilfe `operator==()` verglichen, jedoch, wenn die Zuordnung der komplexen Typen Daten enthält, die ihren eigenen Gleichheitsoperator fehlt, kann diese Klasse überschrieben werden, um die zusätzliche erforderliche Funktionalität bereitzustellen.  
  
## Anforderungen  
 **Header:** atlsimpcoll.h  
  
## Siehe auch  
 [CSimpleMapEqualHelperFalse Class](../../atl/reference/csimplemapequalhelperfalse-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)
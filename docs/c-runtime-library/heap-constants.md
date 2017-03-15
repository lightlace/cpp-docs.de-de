---
title: "Heap-Konstanten | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_HEAPBADPTR"
  - "_HEAPEMPTY"
  - "_HEAPBADBEGIN"
  - "_HEAPOK"
  - "_HEAPBADNODE"
  - "_HEAPEND"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_HEAPBADBEGIN-Konstanten"
  - "_HEAPBADNODE-Konstanten"
  - "_HEAPBADPTR-Konstanten"
  - "_HEAPEMPTY-Konstanten"
  - "_HEAPEND-Konstanten"
  - "_HEAPOK-Konstanten"
  - "heap-Konstanten"
  - "HEAPBADBEGIN-Konstanten"
  - "HEAPBADNODE-Konstanten"
  - "HEAPBADPTR-Konstanten"
  - "HEAPEMPTY-Konstanten"
  - "HEAPEND-Konstanten"
  - "HEAPOK-Konstanten"
ms.assetid: 3f751bb9-2dc4-486f-b5f5-9061c96d3754
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Heap-Konstanten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntax  
  
```  
  
#include <malloc.h>  
  
```  
  
## Hinweise  
 Diese Konstanten geben den Rückgabewert, der Status des Heaps angibt.  
  
|Konstante|Bedeutung|  
|---------------|---------------|  
|`_HEAPBADBEGIN`|Ursprüngliche Header wurde nicht gefunden oder war ungültig.|  
|`_HEAPBADNODE`|Ungültiger Knoten gefunden Heap oder ist beschädigt.|  
|`_HEAPBADPTR`|Feld **\_pentry** von **\_HEAPINFO**\-Struktur enthält gültigen Zeiger nicht in Heap Routine \(nur `_heapwalk` \).|  
|`_HEAPEMPTY`|Heap kann nicht initialisiert.|  
|`_HEAPEND`|Ende des Heaps wurde erfolgreich erreicht \(nur `_heapwalk` Routine\).|  
|`_HEAPOK`|Heap ist konsistent \(`_heapset` und nur `_heapchk` Routinen.\)  Keine Fehler bisher; **\_HEAPINFO**\-Struktur enthält Informationen zu folgenden Eintrag \(nur `_heapwalk` Routine\).|  
  
## Siehe auch  
 [\_heapchk](../c-runtime-library/reference/heapchk.md)   
 [\_heapset](../c-runtime-library/heapset.md)   
 [\_heapwalk](../c-runtime-library/reference/heapwalk.md)   
 [Globale Konstanten](../c-runtime-library/global-constants.md)
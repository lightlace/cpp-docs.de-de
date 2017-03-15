---
title: "_CRT_DISABLE_PERFCRIT_LOCKS | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_CRT_DISABLE_PERFCRIT_LOCKS"
  - "CRT_DISABLE_PERFCRIT_LOCKS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_CRT_DISABLE_PERFCRIT_LOCKS-Konstante"
  - "CRT_DISABLE_PERFCRIT_LOCKS-Konstante"
ms.assetid: 36cc2d86-cdb1-4b2b-a03c-c0d3818e7c6f
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# _CRT_DISABLE_PERFCRIT_LOCKS
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Deaktiviert leistungskritischen Sperre in den E\/A\-Vorgänge.  
  
## Syntax  
  
```  
#define _CRT_DISABLE_PERFCRIT_LOCKS  
```  
  
## Hinweise  
 Durch die Definition dieses Symbols können die Leistung in Singlethreaded E\/A\-gebundenen Programmen verbessern, indem alle E\/A\-Vorgänge erzwingt, um ein einfädiges E\/A\-Modell anzunehmen.  Weitere Informationen finden Sie unter [Leistung von Multithreadbibliotheken](../c-runtime-library/multithreaded-libraries-performance.md).  
  
## Siehe auch  
 [Globale Konstanten](../c-runtime-library/global-constants.md)
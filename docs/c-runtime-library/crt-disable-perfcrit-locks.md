---
title: "_CRT_DISABLE_PERFCRIT_LOCKS"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "_CRT_DISABLE_PERFCRIT_LOCKS"
  - "CRT_DISABLE_PERFCRIT_LOCKS"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_CRT_DISABLE_PERFCRIT_LOCKS-Konstante"
  - "CRT_DISABLE_PERFCRIT_LOCKS-Konstante"
ms.assetid: 36cc2d86-cdb1-4b2b-a03c-c0d3818e7c6f
caps.latest.revision: 4
caps.handback.revision: "4"
ms.author: "corob"
manager: "ghogen"
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
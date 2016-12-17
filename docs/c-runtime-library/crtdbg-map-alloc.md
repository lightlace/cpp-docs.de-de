---
title: "_CRTDBG_MAP_ALLOC"
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
  - "CRTDBG_MAP_ALLOC"
  - "_CRTDBG_MAP_ALLOC"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_CRTDBG_MAP_ALLOC-Makro"
  - "Speicherbelegung, in Debugbuilds"
  - "CRTDBG_MAP_ALLOC-Makro"
ms.assetid: 435242b8-caea-4063-b765-4a608200312b
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# _CRTDBG_MAP_ALLOC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn das **\_CRTDBG\_MAP\_ALLOC**\-Flag in der Debugversion einer Anwendung definiert wird, werden die Basisausnahme Version der Heapfunktionen direkt zu entsprechenden Debugversionen zugeordnet.  Das Flag ist in Crtdbg.h verwendet, um die Zuordnung durchzuführen.  Dieses Flag ist nur verfügbar, wenn das [\_DEBUG](../c-runtime-library/debug.md)\-Flag in der Anwendung definiert wurde.  
  
 Weitere Informationen zur Verwendung der für Debugversion die Basisausnahme Version einer Heapfunktion, finden Sie unter [Verwenden der Debugversion gegen die Basisausnahme Version](../Topic/Debug%20Versions%20of%20Heap%20Allocation%20Functions.md).  
  
## Siehe auch  
 [Steuerungsflags](../c-runtime-library/control-flags.md)
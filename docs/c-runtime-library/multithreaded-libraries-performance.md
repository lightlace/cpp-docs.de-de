---
title: "Leistung von Multithreadbibliotheken | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Bibliotheken, Multithread"
  - "Multithread-Bibliotheken"
  - "Leistung, Multithreading"
  - "Threading [C++], Leistung"
ms.assetid: faa5d808-087c-463d-8f0d-8c478d137296
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# Leistung von Multithreadbibliotheken
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der Singlethreaded CRT ist nicht mehr verfügbar.  In diesem Thema wird erläutert, wie die Höchstleistung von Multithreadbibliotheken abruft.  
  
## Maximieren der Leistung  
 Die Leistung der Multithreadbibliotheken ist wurden verbessert und steht zur Leistung der NOW\-beseitigten Singlethreadanwendung Bibliotheken eng.  Für diese Situationen, wenn noch höhere Ausführungsgeschwindigkeiten erforderlich ist, sind einige neue Funktionen.  
  
-   Unabhängige Streamsperre ermöglicht es Ihnen, einen Stream zu sperren und anschließend das [\_nolock Functions](../c-runtime-library/nolock-functions.md) zu verwenden, das auf den Stream direkt zugreifen.  Dies ermöglicht die außerhalb der wichtigen Schleifen herausgehoben werden, Sperrenverwendung.  
  
-   Threadspezifisches Gebietsschema reduziert die Kosten des Gebietsschemazugriffs für Multithreadszenarien \(siehe [\_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md)\).  
  
-   Gebietsschemaabhängige Funktionen \(wenn die Namen im \_l beenden,\) annehmen das Gebietsschema als Parameter und entfernen erheblichen Kosten, \(beispielsweise [printf, \_printf\_l, wprintf, \_wprintf\_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)\).  
  
-   Optimierungen für allgemeine Codepages reduzieren die Kosten vieler kurzen Vorgänge.  
  
-   [\_CRT\_DISABLE\_PERFCRIT\_LOCKS](../c-runtime-library/crt-disable-perfcrit-locks.md) anwenden, sämtliche E\/A\-Vorgänge, um ein einfädiges E\/A\-Modell anzunehmen und die \_nolock Formulare der Funktionen verwenden.  Dies ermöglicht in hohem Maße I\/O\-based einfädige Anwendungen, eine bessere Leistung zu erzielen.  
  
-   Belichtung des CRT\-Heaphandles ermöglicht es Ihnen, den grundlegenden Fragmentierungs\-Heap \(LFH\) Windows für den CRT\-Heap zu aktivieren, der die Leistung sehr skalierten Szenarien deutlich verbessern kann.  
  
## Siehe auch  
 [CRT\-Bibliotheksfunktionen](../c-runtime-library/crt-library-features.md)
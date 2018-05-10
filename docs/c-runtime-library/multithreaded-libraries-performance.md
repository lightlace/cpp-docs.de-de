---
title: Leistung von Multithreadbibliotheken | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- threading [C++], performance
- libraries, multithreaded
- performance, multithreading
- multithreaded libraries
ms.assetid: faa5d808-087c-463d-8f0d-8c478d137296
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d738cbfe462543437ed4c620f671bb325263e3e3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="multithreaded-libraries-performance"></a>Leistung von Multithreadbibliotheken
Singlethread-CRT ist nicht mehr verfügbar. In diesem Thema wird erläutert, wie Sie maximale Leistung mit Multithreadbibliotheken erzielen.  
  
## <a name="maximizing-performance"></a>Maximieren der Leistung  
 Die Leistung von Multithreadbibliotheken wurde verbessert und erreicht fast die Leistung der jetzt beseitigten Singlethread-Bibliotheken. Für Situationen, in denen sogar eine noch höhere Leistung erforderlich ist, gibt es mehrere neue Features.  
  
-   Mit unabhängiger Datenstromsperrung können Sie einen Datenstrom sperren und anschließend [_nolock-Funktionen](../c-runtime-library/nolock-functions.md) verwenden, die direkt auf den Datenstrom zugreifen. So kann die Sperrverwendung außerhalb kritischer Schleifen gehostet werden.  
  
-   Threadspezifisches Gebietsschema reduziert die Kosten des Gebietsschemazugriffs für Multithread-Szenarien (siehe [_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md)).  
  
-   Vom Gebietsschema abhängige Funktionen (mit Namen, die mit „_l“ enden) nehmen das Gebietsschema als Parameter, was erhebliche Kosten spart (z.B. [printf, _printf_l, wprintf, _wprintf_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)).  
  
-   Optimierungen für allgemeine Codepages verringern die Kosten für viele kurze Vorgänge.  
  
-   Definieren von [_CRT_DISABLE_PERFCRIT_LOCKS](../c-runtime-library/crt-disable-perfcrit-locks.md) erzwingt, dass alle E/A-Vorgänge ein Singlethread-E/A-Modell voraussetzen und die _nolock-Formen der Funktionen verwenden. So können in hohem Maße E/A-basierte Singlethread-Anwendungen eine bessere Leistung erzielen.  
  
-   Das Verfügbarmachen des CRT-Heap-Handles ermöglicht Ihnen das Aktivieren des Windows Low Fragmentation Heap (LFH) für den CRT-Heap, wodurch die Leistung in Szenarien mit hoher Skalierung wesentlich verbessert werden kann.  
  
## <a name="see-also"></a>Siehe auch  
 [CRT-Bibliotheksfunktionen](../c-runtime-library/crt-library-features.md)
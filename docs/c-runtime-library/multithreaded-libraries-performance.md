---
title: Leistung von Multithreadbibliotheken | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- threading [C++], performance
- libraries, multithreaded
- performance, multithreading
- multithreaded libraries
ms.assetid: faa5d808-087c-463d-8f0d-8c478d137296
caps.latest.revision: 4
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: b2a6f6535092043fe2f32c08fbb522ff3c367063
ms.contentlocale: de-de
ms.lasthandoff: 05/18/2017

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

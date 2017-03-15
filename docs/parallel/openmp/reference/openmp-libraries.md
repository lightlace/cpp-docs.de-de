---
title: "OpenMP Libraries | Microsoft Docs"
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
ms.assetid: f89abf97-67e3-4327-bc30-43f85b9533a2
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# OpenMP Libraries
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Erläutert die LIB\-Dateien, die die OpenMP\-Laufzeitbibliotheken in Visual C\+\+ bilden.  
  
 Folgende Bibliotheken enthalten die Visual C\+\+\-OpenMP\-Laufzeitbibliotheks Funktionen.  
  
|OpenMP\-Laufzeitbibliothek|Eigenschaften|  
|--------------------------------|-------------------|  
|VCOMP.LIB|Debugversion, dynamischer Verknüpfung \(Importbibliothek für VCOMP.LIB\).|  
|VCOMPD.LIB|Debugversion, dynamischer Verknüpfung \(Importbibliothek für VCOMPD.LID\) \(Debug\)|  
  
 Wenn \_DEBUG in einer Kompilierung definiert ist und wenn `#include omp.h` im Quellcode ist, ist VCOMPD.LIB Standardwert lib.  Andernfalls wird VCOMP.LIB verwendet.  
  
 Sie können [\/NODEFAULTLIB \(Bibliotheken ignorieren\)](../../../build/reference/nodefaultlib-ignore-libraries.md) und lib Standard verwenden, um explizit die Verknüpfung mit lib der Auswahl entfernt werden soll.  
  
 Das OpenMP DLL befinden sich im Verzeichnis des verteilbaren Visual C\+\+ und müssen mit Anwendungen verteilt werden, die OpenMP verwenden.  
  
## Siehe auch  
 [Library Reference](../../../parallel/openmp/reference/openmp-library-reference.md)
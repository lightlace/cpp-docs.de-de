---
title: OpenMP-Bibliotheken | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
dev_langs:
- C++
ms.assetid: f89abf97-67e3-4327-bc30-43f85b9533a2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 46bd287ff8a020a4d5d7775afdb12f5571d43294
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="openmp-libraries"></a>OpenMP-Bibliotheken
Erläutert die LIB-Dateien, aus denen die OpenMP-Laufzeitbibliotheken in Visual C++ besteht.  
  
 Die folgenden Bibliotheken enthalten, die Visual C++-OpenMP-Laufzeitbibliotheksfunktionen.  
  
|OpenMP-Laufzeitbibliothek|Eigenschaften|  
|------------------------------|---------------------|  
|VCOMP.LIB|Multithreaded, dynamischer Link (Importbibliothek für VCOMP. LIB).|  
|VCOMPD. LIB|Multithreaded, dynamischer Link (Importbibliothek für VCOMPD. LID) (Debuggen)|  
  
 Wenn in einer Kompilierung _DEBUG definiert ist und `#include omp.h` im Quellcode, VCOMPD ist. LIB werden die Standard-Bibliothek. Andernfalls VCOMP. LIB wird verwendet.  
  
 Sie können [/NODEFAULTLIB (Bibliotheken ignorieren)](../../../build/reference/nodefaultlib-ignore-libraries.md) entfernen die Standard-Lib und explizit mit der Lib Ihrer Wahl verknüpfen.  
  
 Die OpenMP-DLLs befinden sich in der Visual C++ redistributable-Verzeichnis und mit Anwendungen verteilt werden, die OpenMP verwenden müssen.  
  
## <a name="see-also"></a>Siehe auch  
 [Bibliotheksverweis](../../../parallel/openmp/reference/openmp-library-reference.md)
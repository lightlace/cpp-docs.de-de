---
title: OpenMP-Bibliotheken | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: f89abf97-67e3-4327-bc30-43f85b9533a2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 760e7d138ab71244419ff71960948d4d10f125eb
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="openmp-libraries"></a>OpenMP-Bibliotheken
Erläutert die LIB-Dateien, aus denen die OpenMP-Laufzeitbibliotheken in Visual C++ besteht.  
  
 Die folgenden Bibliotheken enthalten, die Visual C++-OpenMP-Laufzeitbibliotheksfunktionen.  
  
|OpenMP-Laufzeitbibliothek|Eigenschaften|  
|------------------------------|---------------------|  
|VCOMP.LIB|Multithreaded, dynamischer Link (Importbibliothek für VCOMP. LIB).|  
|VCOMPD.LIB|Multithreaded, dynamischer Link (Importbibliothek für VCOMPD. LID) (Debuggen)|  
  
 Wenn in einer Kompilierung _DEBUG definiert ist und `#include omp.h` im Quellcode, VCOMPD ist. LIB werden die Standard-Bibliothek. Andernfalls VCOMP. LIB wird verwendet.  
  
 Sie können [/NODEFAULTLIB (Bibliotheken ignorieren)](../../../build/reference/nodefaultlib-ignore-libraries.md) entfernen die Standard-Lib und explizit mit der Lib Ihrer Wahl verknüpfen.  
  
 Die OpenMP-DLLs befinden sich in der Visual C++ redistributable-Verzeichnis und mit Anwendungen verteilt werden, die OpenMP verwenden müssen.  
  
## <a name="see-also"></a>Siehe auch  
 [Bibliotheksverweis](../../../parallel/openmp/reference/openmp-library-reference.md)
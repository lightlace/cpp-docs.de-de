---
title: OpenMP-Bibliotheken
ms.date: 10/24/2018
ms.assetid: f89abf97-67e3-4327-bc30-43f85b9533a2
ms.openlocfilehash: 75f772c953a2120a02f72d8bdfc73c1baaaef390
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50530337"
---
# <a name="openmp-libraries"></a>OpenMP-Bibliotheken

Erläutert die LIB-Dateien, aus denen die OpenMP-Laufzeitbibliotheken in Visual C++ besteht.

Die folgenden Bibliotheken enthalten, die Visual C++-OpenMP-Laufzeitbibliotheksfunktionen.

|OpenMP-Laufzeitbibliothek|Eigenschaften|
|------------------------------|---------------------|
|VCOMP.LIB|Multithreaded, dynamischer Link (Importbibliothek für VCOMP. LIB).|
|VCOMPD. LIB|Multithreaded, dynamischer Link (Importbibliothek für VCOMPD. Deckel) (Debuggen)|

Wenn in einer Kompilierung _DEBUG definiert ist und `#include omp.h` im Quellcode VCOMPD ist. LIB, werden die Standard-Bibliothek. Andernfalls VCOMP. LIB wird verwendet.

Sie können [/NODEFAULTLIB (Bibliotheken ignorieren)](../../../build/reference/nodefaultlib-ignore-libraries.md) , entfernen Sie die Standard-Bibliothek und explizit mit den Lib Ihrer Wahl verknüpfen.

Die OpenMP-DLLs befinden sich in der Visual C++ redistributable-Verzeichnis und mit Anwendungen verteilt werden, die OpenMP verwenden müssen.

## <a name="see-also"></a>Siehe auch

[Referenz zur Bibliothek](openmp-library-reference.md)

---
title: OpenMP-Bibliotheksverweis
ms.date: 03/20/2019
ms.assetid: a25188c6-edde-43d0-84b5-780e797b08fc
ms.openlocfilehash: 6f4bbeca54bff1fc44a3576362edca9c30926d5a
ms.sourcegitcommit: 14b292596bc9b9b883a9c58cd3e366b282a1f7b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2019
ms.locfileid: "60124693"
---
# <a name="openmp-library-reference"></a>OpenMP-Bibliotheksverweis

Enthält Links zu Konstrukten, die in der OpenMP-API verwendet.

Die Visual C++-Implementierung des OpenMP umfasst die folgenden Konstrukte.

|Konstrukt|Beschreibung|
|---------------|-----------------|
|[Anweisungen](openmp-directives.md)|Enthält Links zu Anweisungen, die in der OpenMP-API verwendet.|
|[Klauseln](openmp-directives.md)|Enthält Links zu den Klauseln, die in der OpenMP-API verwendet.|
|[Funktionen](openmp-functions.md)|Enthält Links zu Funktionen, die in der OpenMP-API verwendet.|
|[Umgebungsvariablen](openmp-environment-variables.md)|Enthält Links zu den Umgebungsvariablen, die in der OpenMP-API verwendet.|

Das visuelle Element C++ OpenMP-Laufzeitbibliotheksfunktionen in den folgenden Bibliotheken enthalten sind.

|OpenMP-Laufzeitbibliothek|Eigenschaften|
|------------------------------|---------------------|
|VCOMP.LIB|Multithreaded, dynamischer Link (Importbibliothek für VCOMP. LIB).|
|VCOMPD.LIB|Multithreaded, dynamischer Link (Importbibliothek für VCOMPD. Deckel) (Debuggen)|

Wenn in einer Kompilierung _DEBUG definiert ist und `#include omp.h` im Quellcode VCOMPD ist. LIB, wird die standardmäßige Lib, anderenfalls VCOMP sein. LIB wird verwendet.

Sie können [/NODEFAULTLIB (Bibliotheken ignorieren)](../../../build/reference/nodefaultlib-ignore-libraries.md) , entfernen Sie die Standard-Bibliothek und explizit mit den Lib Ihrer Wahl verknüpfen.

Die OpenMP-DLLs befinden sich in der Visual C++ redistributable-Verzeichnis und mit Anwendungen verteilt werden, die OpenMP verwenden müssen.

## <a name="see-also"></a>Siehe auch

[OpenMP](../../../parallel/openmp/openmp-in-visual-cpp.md)
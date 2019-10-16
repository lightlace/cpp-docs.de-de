---
title: OpenMP-Bibliotheksverweis
ms.date: 07/30/2019
ms.assetid: a25188c6-edde-43d0-84b5-780e797b08fc
ms.openlocfilehash: c63ae5ba7f04d8ee6bd02418792804373fa71e6b
ms.sourcegitcommit: 170f5de63b0fec8e38c252b6afdc08343f4243a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72348221"
---
# <a name="openmp-library-reference"></a>OpenMP-Bibliotheksverweis

Enthält Links zu Konstrukten, die in der OpenMP-API verwendet werden.

Die visuelle C++ Implementierung von OpenMP Standard umfasst die folgenden Konstrukte.

|Konstrukt|Beschreibung|
|---------------|-----------------|
|[Anweisungen](openmp-directives.md)|Stellt Links zu Anweisungen bereit, die in der OpenMP-API verwendet werden.|
|[Klauseln](openmp-clauses.md)|Enthält Links zu Klauseln, die in der OpenMP-API verwendet werden.|
|[Funktionen](openmp-functions.md)|Enthält Links zu Funktionen, die in der OpenMP-API verwendet werden.|
|[Umgebungsvariablen](openmp-environment-variables.md)|Enthält Links zu Umgebungsvariablen, die in der OpenMP-API verwendet werden.|

Die Visual C++ OpenMP-Lauf Zeit Bibliotheksfunktionen sind in den folgenden Bibliotheken enthalten.

|OpenMP-Lauf Zeit Bibliothek|Eigenschaften|
|------------------------------|---------------------|
|Vcomp. LIB|Multithreaded, dynamischer Link (Import Bibliothek für vcomp. LIB).|
|Vcompd. LIB|Multithreaded, dynamischer Link (Import Bibliothek für vcompd). LID) (Debuggen)|

, Wenn _DEBUG in einer Kompilierung definiert ist und `#include <omp.h>` im Quellcode ist, vcompd. Lib ist die Standard-lib, andernfalls vcomp. LIB wird verwendet.

Sie können [/NODEFAULTLIB (Bibliotheken ignorieren)](../../../build/reference/nodefaultlib-ignore-libraries.md) verwenden, um die Standard-lib zu entfernen und explizit mit der lib Ihrer Wahl zu verknüpfen.

Die OpenMP-DLLs befinden sich im C++ verteilbaren Visual-Verzeichnis und müssen mit Anwendungen, die OpenMP verwenden, verteilt werden.

## <a name="see-also"></a>Siehe auch

[OpenMP](../../../parallel/openmp/openmp-in-visual-cpp.md)

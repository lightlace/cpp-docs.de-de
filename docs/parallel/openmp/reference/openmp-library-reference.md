---
title: OpenMP-Bibliotheksverweis
ms.date: 07/30/2019
ms.assetid: a25188c6-edde-43d0-84b5-780e797b08fc
ms.openlocfilehash: c78c2677741714ab48d49a4443ad753369ec4500
ms.sourcegitcommit: 725e86dabe2901175ecc63261c3bf05802dddff4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/31/2019
ms.locfileid: "68682592"
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
|VCOMP.LIB|Multithreaded, dynamischer Link (Import Bibliothek für vcomp. LIB).|
|VCOMPD.LIB|Multithreaded, dynamischer Link (Import Bibliothek für vcompd). LID) (Debuggen)|

, Wenn _DEBUG in einer Kompilierung definiert ist `#include omp.h` und im Quellcode ist, vcompd. Lib ist die Standard-lib, andernfalls vcomp. LIB wird verwendet.

Sie können [/NODEFAULTLIB (Bibliotheken ignorieren)](../../../build/reference/nodefaultlib-ignore-libraries.md) verwenden, um die Standard-lib zu entfernen und explizit mit der lib Ihrer Wahl zu verknüpfen.

Die OpenMP-DLLs befinden sich im C++ verteilbaren Visual-Verzeichnis und müssen mit Anwendungen, die OpenMP verwenden, verteilt werden.

## <a name="see-also"></a>Siehe auch

[OpenMP](../../../parallel/openmp/openmp-in-visual-cpp.md)
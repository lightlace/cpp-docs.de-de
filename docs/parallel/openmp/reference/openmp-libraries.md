---
title: OpenMP-Bibliotheken | Microsoft-Dokumentation
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
ms.openlocfilehash: c9a4ccfefeaeb9446731027db44b849233bfefd6
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46391214"
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

[Referenz zur Bibliothek](../../../parallel/openmp/reference/openmp-library-reference.md)
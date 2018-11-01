---
title: OpenMP-Bibliotheken | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/24/2018
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
ms.openlocfilehash: 7620b0ea710a5474fbbbf614691ceeb1e5cc945e
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50062001"
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

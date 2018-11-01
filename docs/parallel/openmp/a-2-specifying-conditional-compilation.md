---
title: A.2   Angeben der bedingten Kompilierung
ms.date: 11/04/2016
ms.assetid: de4a21b9-f987-4738-9f13-c4795f6f2dff
ms.openlocfilehash: 92ae22ffac1b1a1c3fc45a9a7a883203ff6d251e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50491220"
---
# <a name="a2---specifying-conditional-compilation"></a>A.2   Angeben der bedingten Kompilierung

Die folgenden Beispiele veranschaulichen die Verwendung des für die bedingte Kompilierung, die mit dem Makro OpenMP `_OPENMP` ([Abschnitt 2.2](../../parallel/openmp/2-2-conditional-compilation.md) auf Seite "8"). Bei der OpenMP-Kompilierung die `_OPENMP` Makro definiert wird.

```
# ifdef _OPENMP
    printf_s("Compiled by an OpenMP-compliant implementation.\n");
# endif
```

Der definierte Präprozessoroperator kann mehr als ein Makro in einer einzelnen Richtlinie getestet werden.

```
# if defined(_OPENMP) && defined(VERBOSE)
    printf_s("Compiled by an OpenMP-compliant implementation.\n");
# endif
```
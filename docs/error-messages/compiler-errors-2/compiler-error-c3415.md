---
title: Compilerfehler C3415
ms.date: 11/04/2016
f1_keywords:
- C3415
helpviewer_keywords:
- C3415
ms.assetid: fa2db8ab-2820-4ec3-a740-fb5e2adcfb29
ms.openlocfilehash: 3d4163fac83e24d30f29aed92e7a1ec1fc9e362f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50482003"
---
# <a name="compiler-error-c3415"></a>Compilerfehler C3415

Mehrere 'Abschnittsname'-Abschnitte mit unterschiedlichen Attributen gefunden ('Wert').

Es wurden in [section](../../preprocessor/section.md) -Pragmas in Konflikt stehende Werte angegeben.

`value` ist die aktuelle Einstellung für den Abschnitt, wie in ntimage.h angegeben. Zum Beispiel:

```
// Section contains extended relocations.
#define IMAGE_SCN_LNK_NRELOC_OVFL            0x01000000
// Section can be discarded.
#define IMAGE_SCN_MEM_DISCARDABLE            0x02000000
// Section is not cachable.
#define IMAGE_SCN_MEM_NOT_CACHED             0x04000000
// Section is not pageable.
#define IMAGE_SCN_MEM_NOT_PAGED              0x08000000
// Section is shareable.
#define IMAGE_SCN_MEM_SHARED                 0x10000000
// Section is executable.
#define IMAGE_SCN_MEM_EXECUTE                0x20000000
// Section is readable.
#define IMAGE_SCN_MEM_READ                   0x40000000
// Section is writeable.
#define IMAGE_SCN_MEM_WRITE                  0x80000000
```

Im folgenden Beispiel wird C3415 generiert:

```
// C3415.cpp
#pragma section("mysec1",write)
#pragma section("mysec1",read)   // C3415
```
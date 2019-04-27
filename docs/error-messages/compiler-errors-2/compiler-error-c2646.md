---
title: Compilerfehler C2646
ms.date: 11/04/2016
f1_keywords:
- C2646
helpviewer_keywords:
- C2646
ms.assetid: 92ff1f02-5eaf-40a5-8b7a-a682f149e967
ms.openlocfilehash: c02d7216df42681ae2ec733ae932d22861c1f0ee
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62282208"
---
# <a name="compiler-error-c2646"></a>Compilerfehler C2646

Eine anonyme Struktur oder Union im globalen Gültigkeitsbereich oder im Namespacebereich muss als statisch deklariert werden.

Eine anonyme Struktur oder Union verfügt über einen globalen Gültigkeitsbereich oder Namespacebereich, ist jedoch nicht als `static` deklariert.

Im folgenden Beispiel wird C2646 generiert und gezeigt, wie Sie diesen Fehler beheben:

```
// C2646.cpp
// compile with: /c
union { int i; };   // C2646 not static

// OK
static union { int j; };
union U { int i; };
```
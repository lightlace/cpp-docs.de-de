---
title: Compilerfehler C2341
ms.date: 11/04/2016
f1_keywords:
- C2341
helpviewer_keywords:
- C2341
ms.assetid: aa2a7da5-e1c8-4225-9939-5bdc50158f31
ms.openlocfilehash: 4356182758398fa7ed1ec6a069affa4bb99ace1a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62188219"
---
# <a name="compiler-error-c2341"></a>Compilerfehler C2341

'Abschnittsname': Segment muss definiert werden, verwenden #pragma Data_seg, Code_seg oder im vorherigen Abschnitt verwenden

Ein [zuordnen](../../cpp/allocate.md) Anweisung verweist auf ein Segment, das noch nicht durch definiert [Code_seg](../../preprocessor/code-seg.md), [Data_seg](../../preprocessor/data-seg.md), oder [Abschnitt](../../preprocessor/section.md) Pragmas.

Im folgende Beispiel wird die C2341 generiert:

```
// C2341.cpp
// compile with: /c
__declspec(allocate(".test"))   // C2341
int j = 1;
```

Mögliche Lösung:

```
// C2341b.cpp
// compile with: /c
#pragma data_seg(".test")
__declspec(allocate(".test"))
int j = 1;
```
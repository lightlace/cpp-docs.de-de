---
title: Compilerfehler C2357
ms.date: 11/04/2016
f1_keywords:
- C2357
helpviewer_keywords:
- C2357
ms.assetid: d1083945-0ea2-4385-9e66-8c665978806c
ms.openlocfilehash: ce1926468bac7e44485be5c0a0944fdf12dce3d8
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759918"
---
# <a name="compiler-error-c2357"></a>Compilerfehler C2357

"Bezeichner": muss eine Funktion vom Typ "Typ" sein.

Der Code deklariert eine Version der `atexit`-Funktion, die nicht mit der vom Compiler intern deklarierten Version identisch ist. Deklarieren Sie `atexit` wie folgt:

```
int __cdecl atexit(void (__cdecl *)());
```

Weitere Informationen finden Sie unter [init_seg](../../preprocessor/init-seg.md).

Im folgenden Beispiel wird C2357 generiert:

```cpp
// C2357.cpp
// compile with: /c
// C2357 expected
#pragma warning(disable : 4075)
// Uncomment the following line to resolve.
// int __cdecl myexit(void (__cdecl *)());
#pragma init_seg(".mine$m",myexit)
```

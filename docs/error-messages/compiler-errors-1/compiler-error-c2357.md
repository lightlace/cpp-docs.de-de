---
title: Compilerfehler C2357
ms.date: 11/04/2016
f1_keywords:
- C2357
helpviewer_keywords:
- C2357
ms.assetid: d1083945-0ea2-4385-9e66-8c665978806c
ms.openlocfilehash: 1872672e776ad13bf16be5ae69729f4f68d8f3b0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50531780"
---
# <a name="compiler-error-c2357"></a>Compilerfehler C2357

'Bezeichner': eine Funktion vom Typ 'Typ' sein muss

Ihr Code deklariert eine Version der `atexit` -Funktion, die stimmt nicht mit der Version vom Compiler intern deklariert. Deklarieren Sie `atexit` wie folgt:

```
int __cdecl atexit(void (__cdecl *)());
```

Weitere Informationen finden Sie unter [Init_seg](../../preprocessor/init-seg.md).

Im folgende Beispiel wird die C2357 generiert:

```
// C2357.cpp
// compile with: /c
// C2357 expected
#pragma warning(disable : 4075)
// Uncomment the following line to resolve.
// int __cdecl myexit(void (__cdecl *)());
#pragma init_seg(".mine$m",myexit)
```
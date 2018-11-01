---
title: Compilerfehler C3898
ms.date: 11/04/2016
f1_keywords:
- C3898
helpviewer_keywords:
- C3898
ms.assetid: d9a90df6-87e4-4fe7-ab01-c226ee86bf10
ms.openlocfilehash: 503f295d62c598e3138b1a001d6b350c0d90ea84
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50549733"
---
# <a name="compiler-error-c3898"></a>Compilerfehler C3898

'Var': Typ-Datenmember können nur Member von verwalteten Typen sein

Ein [Initonly](../../dotnet/initonly-cpp-cli.md) Datenmember in einer systemeigenen Klasse deklariert wurde.  Ein `initonly` -Datenmember kann nur in einer CLR-Klasse deklariert werden.

Im folgende Beispiel wird die C3898 generiert:

```
// C3898.cpp
// compile with: /clr
struct Y1 {
   initonly
   static int data_var = 9;   // C3898
};
```

Mögliche Lösung:

```
// C3898b.cpp
// compile with: /clr /c
ref struct Y1 {
   initonly
   static int data_var = 9;
};
```
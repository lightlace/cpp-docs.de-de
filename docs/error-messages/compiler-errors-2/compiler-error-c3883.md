---
title: Compilerfehler C3883 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3883
dev_langs:
- C++
helpviewer_keywords:
- C3883
ms.assetid: cdd1c1f4-f268-4469-9c62-d52303114b0c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4387eacb4e35c82af5c2617771b8c887dae42c4e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46045470"
---
# <a name="compiler-error-c3883"></a>Compilerfehler C3883

"Var": ein statischer Initonly-Datenmember muss initialisiert werden

Eine Variable, die mit markierten [Initonly](../../dotnet/initonly-cpp-cli.md) wurde nicht ordnungsgemäß initialisiert.

Im folgende Beispiel wird die C3883 generiert:

```
// C3883.cpp
// compile with: /clr
ref struct Y1 {
   initonly
   static int staticConst1;   // C3883
};
```

Das folgende Beispiel zeigt eine mögliche Lösung:

```
// C3883b.cpp
// compile with: /clr /c
ref struct Y1 {
   initonly
   static int staticConst2 = 0;
};
```

Im folgende Beispiel wird veranschaulicht, wie in einem statischen Konstruktor initialisiert werden:

```
// C3883c.cpp
// compile with: /clr /LD
ref struct Y1 {
   initonly
   static int staticConst1;

   static Y1() {
      staticConst1 = 0;
   }
};
```
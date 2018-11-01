---
title: Compilerfehler C3226
ms.date: 11/04/2016
f1_keywords:
- C3226
helpviewer_keywords:
- C3226
ms.assetid: 636106ca-6f4e-4303-a6a0-8803221ec67d
ms.openlocfilehash: 39b715b580d6fca9c15e5b9e2b63a9afb609eb16
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50660108"
---
# <a name="compiler-error-c3226"></a>Compilerfehler C3226

Innerhalb einer generischen Deklaration ist keine Vorlagendeklaration zulässig.

Verwenden Sie eine generische Deklaration innerhalb einer generischen Klasse.

Im folgenden Beispiel wird C3226 generiert:

```
// C3226.cpp
// compile with: /clr
generic <class T>
ref class C {
   template <class T1>   // C3226
   ref struct S1 {};
};
```

Das folgende Beispiel zeigt eine mögliche Lösung:

```
// C3226b.cpp
// compile with: /clr /c
generic <class T>
ref class C {
   generic <class T1>
   ref struct S1 {};
};
```
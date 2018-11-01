---
title: Compilerfehler C2811
ms.date: 11/04/2016
f1_keywords:
- C2811
helpviewer_keywords:
- C2811
ms.assetid: 6a44b18e-44c1-49d8-9b99-e0545b9a6e7d
ms.openlocfilehash: 8dfc462cc0eedfff1661ae38f79bbb79c5c1a8fa
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50520262"
---
# <a name="compiler-error-c2811"></a>Compilerfehler C2811

"Typ1": kann nicht von 'type2', ein Ref erben Klasse kann nur von einer Verweisklasse oder Schnittstellenklasse erben

Sie versucht, eine nicht verwaltete Klasse als Basisklasse für eine verwaltete Klasse zu verwenden.

Im folgende Beispiel wird die C2811 generiert:

```
// C2811.cpp
// compile with: /clr /c
struct S{};
ref struct T {};
ref class C : public S {};   // C2811
ref class D : public T {};   // OK
```
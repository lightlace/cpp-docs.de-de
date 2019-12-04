---
title: Compilerfehler C2776
ms.date: 11/04/2016
f1_keywords:
- C2776
helpviewer_keywords:
- C2776
ms.assetid: 9d80addc-62c7-40fc-a2cc-60303abb87df
ms.openlocfilehash: 79758c88e595e6d5ebb5cd4b39a8df8fc1339752
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74740064"
---
# <a name="compiler-error-c2776"></a>Compilerfehler C2776

nur eine "Get"-Methode kann pro Eigenschaft angegeben werden.

Sie können nur eine `get` Funktion im erweiterten Attribut der [Eigenschaft](../../cpp/property-cpp.md) angeben. Dieser Fehler tritt auf, wenn mehrere `get` Funktionen angegeben sind.

Im folgenden Beispiel wird C2776 generiert:

```cpp
// C2776.cpp
struct A {
   __declspec(property(get=GetProp,get=GetPropToo))
   // try the following line instead
   // __declspec(property(get=GetProp))
      int prop;   // C2776
   int GetProp(void);
   int GetPropToo(void);
};
```

---
title: Compilerfehler C2776
ms.date: 11/04/2016
f1_keywords:
- C2776
helpviewer_keywords:
- C2776
ms.assetid: 9d80addc-62c7-40fc-a2cc-60303abb87df
ms.openlocfilehash: 200fbc5c42a6b735c072c093ec4cb4f081031824
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50652142"
---
# <a name="compiler-error-c2776"></a>Compilerfehler C2776

nur ein "get"-Methode kann pro Eigenschaft angegeben werden

Sie können nur eine angeben `get` Funktion in der [Eigenschaft](../../cpp/property-cpp.md) erweitertes Attribut. Dieser Fehler tritt auf, wenn mehrere `get` Funktionen angegeben werden.

Im folgende Beispiel wird die C2776 generiert:

```
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
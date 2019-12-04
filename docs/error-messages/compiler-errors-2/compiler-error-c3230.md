---
title: Compilerfehler C3230
ms.date: 11/04/2016
f1_keywords:
- C3230
helpviewer_keywords:
- C3230
ms.assetid: 5ec53f25-59f6-4801-81e7-7b68bf04994d
ms.openlocfilehash: 69ea279ac5e11c03f366711484ba0c250fc50225
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74743314"
---
# <a name="compiler-error-c3230"></a>Compilerfehler C3230

'Funktion': Das Vorlagentypargument für 'Vorlage' kann keinen generischen Typparameter enthalten: 'param'

Vorlagen werden zur Kompilierzeit, aber Generics zur Laufzeit instanziiert. Daher ist es nicht möglich, generischen Code zu generieren, der die Vorlage aufrufen kann, da die Vorlage nicht zur Laufzeit instanziiert werden kann, wenn der generische Typ schließlich bekannt ist.

Im folgenden Beispiel wird C3230 generiert:

```cpp
// C3230.cpp
// compile with: /clr /LD
template <class S>
void f(S t);

generic <class U>
ref class C {
   void f1(U x) {
      f(x);   // C3230
   }
};
```

---
title: Compilerfehler C3231
ms.date: 11/04/2016
f1_keywords:
- C3231
helpviewer_keywords:
- C3231
ms.assetid: fe5dc352-e634-45fa-9534-3da176294c98
ms.openlocfilehash: 3bc8293f0cbed7c2093cfe9dd0513b690b8c76f0
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74750337"
---
# <a name="compiler-error-c3231"></a>Compilerfehler C3231

"Arg": das Vorlagentyp Argument kann keinen generischen Typparameter verwenden.

Vorlagen werden zur Kompilierzeit, aber Generics zur Laufzeit instanziiert. Daher ist es nicht möglich, generischen Code zu generieren, der die Vorlage aufrufen kann, da die Vorlage nicht zur Laufzeit instanziiert werden kann, wenn der generische Typ schließlich bekannt ist.

Im folgenden Beispiel wird C3231 generiert:

```cpp
// C3231.cpp
// compile with: /clr /LD
template <class T> class A;

generic <class T>
ref class C {
   void f() {
      A<T> a;   // C3231
   }
};
```

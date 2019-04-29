---
title: Compilerfehler C2903
ms.date: 11/04/2016
f1_keywords:
- C2903
helpviewer_keywords:
- C2903
ms.assetid: bf6b223f-4921-48c7-82b9-ff318b42c801
ms.openlocfilehash: 7002e45770c994d5cd10e1cd632561be57246086
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62378530"
---
# <a name="compiler-error-c2903"></a>Compilerfehler C2903

'Bezeichner': Symbol ist weder eine Klassenvorlage noch eine Funktionsvorlage.

Der Code versucht die explizite Instanziierung eines Elements, bei dem es sich nicht um eine Vorlage handelt.

Im folgenden Beispiel wird C2903 generiert:

```
// C2903.cpp
// compile with: /c
namespace N {
   template<class T> class X {};
   class Y {};
}
void g() {
   N::template Y y;   // C2903
   N::X<N::Y> y;   // OK
}
```

C2903 kann auch auftreten, wenn Generics verwendet werden:

```
// C2903b.cpp
// compile with: /clr /c
namespace N {
   class Y {};
   generic<class T> ref class Z {};
}

void f() {
   N::generic Y y;   // C2903
   N:: generic Z<int>^ z;   // OK
}
```
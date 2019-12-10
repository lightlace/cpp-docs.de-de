---
title: Compilerwarnung (Stufe 4) C4239
ms.date: 11/04/2016
f1_keywords:
- C4239
helpviewer_keywords:
- C4239
ms.assetid: a23dc16a-649e-4870-9a24-275de1584fcd
ms.openlocfilehash: a882fa7f78f68cb2400e4924a9ba2f17e6ee7003
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74991457"
---
# <a name="compiler-warning-level-4-c4239"></a>Compilerwarnung (Stufe 4) C4239

nicht dem Standard entsprechende Erweiterung verwendet: ' Token ': Konvertierung von ' type ' in ' type '

Diese Typkonvertierung ist vom C++ Standard nicht zulässig, aber hier als Erweiterung zulässig. Auf diese Warnung folgt immer mindestens eine Erklärung, in der die Verletzung der Sprachregel beschrieben wird.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4239 generiert.

```cpp
// C4239.cpp
// compile with: /W4 /c
struct C {
   C() {}
};

void func(void) {
   C & rC = C();   // C4239
   const C & rC2 = C();   // OK
   rC2;
}
```

## <a name="example"></a>Beispiel

Die Konvertierung eines ganzzahligen Typs in einen Aufzählungstyp ist nicht streng zulässig.

Im folgenden Beispiel wird C4239 generiert.

```cpp
// C4239b.cpp
// compile with: /W4 /c
enum E { value };
struct S {
   E e : 2;
} s = { 5 };   // C4239
// try the following line instead
// } s = { (E)5 };
```

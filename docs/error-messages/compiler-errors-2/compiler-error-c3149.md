---
title: Compilerfehler C3149
ms.date: 11/04/2016
f1_keywords:
- C3149
helpviewer_keywords:
- C3149
ms.assetid: cf6e2616-2f06-46da-8a8a-d449cb481c51
ms.openlocfilehash: 8238dcec821256dad8101cd7ad59b2d85882c218
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345512"
---
# <a name="compiler-error-c3149"></a>Compilerfehler C3149

'Typ': Dieser Typ ohne eine der obersten Ebene 'Char' kann nicht verwendet

Eine Deklaration wurde nicht ordnungsgemäß angegeben.

Beispielsweise kann definiert einen CLR-Typ im globalen Gültigkeitsbereich und versucht, eine Variable des Typs als Teil der Definition zu erstellen. Da globale Variablen von CLR-Typen nicht zulässig sind, generiert der Compiler C3149 generiert.

Deklarieren Sie Variablen, die von CLR-Typen in der Definition einer Funktion oder der Typ, um diesen Fehler zu beheben.

Im folgende Beispiel wird die C3149 generiert:

```
// C3149.cpp
// compile with: /clr
using namespace System;
int main() {
   // declare an array of value types
   array< Int32 ^> IntArray;   // C3149
   array< Int32>^ IntArray2;   // OK
}
```

Im folgende Beispiel wird die C3149 generiert:

```
// C3149b.cpp
// compile with: /clr /c
delegate int MyDelegate(const int, int);
void Test1(MyDelegate m) {}   // C3149
void Test2(MyDelegate ^ m) {}   // OK
```

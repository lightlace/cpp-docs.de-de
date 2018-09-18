---
title: Compilerfehler C3149 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3149
dev_langs:
- C++
helpviewer_keywords:
- C3149
ms.assetid: cf6e2616-2f06-46da-8a8a-d449cb481c51
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2a522bfd3ba236661f206d8d4e4b550179c06b3f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46033120"
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

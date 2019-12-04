---
title: Compilerfehler C2057
ms.date: 11/04/2016
f1_keywords:
- C2057
helpviewer_keywords:
- C2057
ms.assetid: 038a99d6-1f5a-42fa-8449-03b4ff11ee0b
ms.openlocfilehash: 37dbc2f6ae0614215f0a3de20baa601b48db9450
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74742443"
---
# <a name="compiler-error-c2057"></a>Compilerfehler C2057

Konstanter Ausdruck erwartet

Der Kontext erfordert einen konstanten Ausdruck bzw. einen Ausdruck, dessen Wert zur Kompilierzeit bekannt ist.

Der Compiler muss die Größe eines Typs zur Kompilierungszeit kennen, um Speicherplatz für eine Instanz dieses Typs zuzuweisen.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2057 generiert und gezeigt, wie Sie diesen Fehler beheben:

```cpp
// C2057.cpp
int i;
int b[i];   // C2057 - value of i is unknown at compile time
int main() {
   const int i = 8;
   int b[i]; // OK - value of i is fixed and known to compiler
}
```

## <a name="example"></a>Beispiel

C# verfügt über restriktivere Regeln für konstante Ausdrücke.  Im folgenden Beispiel wird C2057 generiert und gezeigt, wie Sie diesen Fehler beheben:

```
// C2057b.c
#define ArraySize1 10
int main() {
   const int ArraySize2 = 10;
   int h[ArraySize2];   // C2057 - C does not allow variables here
   int h[ArraySize1];   // OK - uses preprocessor constant
}
```

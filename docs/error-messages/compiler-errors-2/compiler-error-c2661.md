---
title: Compilerfehler C2661
ms.date: 11/04/2016
f1_keywords:
- C2661
helpviewer_keywords:
- C2661
ms.assetid: 60021467-71cd-451b-9877-23840c69309f
ms.openlocfilehash: e4d0e8a1c707374e0e93a5687351a9360fa17c0f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756044"
---
# <a name="compiler-error-c2661"></a>Compilerfehler C2661

"Function": keine überladene Funktion nimmt Zahlen Parameter an

Mögliche Ursachen:

1. Falsche tatsächliche Parameter im Funktions Aufruf.

1. Fehlende Funktionsdeklaration.

Im folgenden Beispiel wird C2661 generiert:

```cpp
// C2661.cpp
void func( int ){}
void func( int, int ){}
int main() {
   func( );   // C2661 func( void ) was not declared
   func( 1 );   // OK func( int ) was declared
}
```

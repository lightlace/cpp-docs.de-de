---
title: Compilerwarnung (Stufe 2) C4244
ms.date: 11/04/2016
f1_keywords:
- C4244
helpviewer_keywords:
- C4244
ms.assetid: 2c19d157-21d1-42c2-a6c0-3f30f2ce3813
ms.openlocfilehash: 43d8a992801d556ce85577f5f9da1bec584cb173
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052129"
---
# <a name="compiler-warning-level-2-c4244"></a>Compilerwarnung (Stufe 2) C4244

' Argument ': Konvertierung von ' Typ1 ' in ' Typ2 ', möglicher Datenverlust

Ein Gleit kommatyp wurde in einen ganzzahligen Typ konvertiert.  Möglicherweise ist ein Datenverlust aufgetreten.

Wenn C4244 angezeigt wird, sollten Sie das Programm für das Verwenden von kompatiblen Typen ändern Logik zu Ihrem Code hinzufügen, um sicherzustellen, dass der Bereich möglicher Werte immer mit den verwendeten Typen kompatibel sind.

C4244 kann auch auf Ebene 3 und 4 ausgelöst werden. Weitere Informationen finden Sie unter [Compilerwarnung (Stufen 3 und 4) C4244](../../error-messages/compiler-warnings/compiler-warning-levels-3-and-4-c4244.md) .

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4244 generiert:

```cpp
// C4244_level2.cpp
// compile with: /W2

int f(int x){ return 0; }
int main() {
   double x = 10.1;
   int i = 10;
   return (f(x));   // C4244
   // try the following line instead
   // return (f(i));
}
```
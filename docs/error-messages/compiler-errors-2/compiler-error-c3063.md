---
title: Compilerfehler C3063
ms.date: 11/04/2016
f1_keywords:
- C3063
helpviewer_keywords:
- C3063
ms.assetid: 0ecf6f1f-e4a7-487a-9fd5-79d8ac470001
ms.openlocfilehash: 9e53d9fe273a392695212df6dbeb679822a39068
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50485533"
---
# <a name="compiler-error-c3063"></a>Compilerfehler C3063

Operator 'Operator': alle Operanden müssen den gleichen Enumerationstyp aufweisen

Bei Verwendung von Operatoren auf Enumeratoren müssen beide Operanden des Enumerationstyps sein. Weitere Informationen finden Sie unter [wie: definieren und Verarbeiten von Enumerationen in C++ / CLI](../../dotnet/how-to-define-and-consume-enums-in-cpp-cli.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3063 generiert und gezeigt, wie Sie diesen Fehler beheben:

```
// C3063.cpp
// compile with: /clr
enum class E { a, b } e, mask;
int main() {
   if ( ( e & mask ) != 0 ) ;   // C3063 no operator!= (E, int)

   if ( ( e & mask ) != E() )   // OK
      ;
}
```
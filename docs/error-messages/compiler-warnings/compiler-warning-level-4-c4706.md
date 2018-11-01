---
title: Compilerwarnung (Stufe 4) C4706
ms.date: 11/04/2016
f1_keywords:
- C4706
helpviewer_keywords:
- C4706
ms.assetid: 89cd3f4f-812c-4a4b-9426-65a5a6d1b99c
ms.openlocfilehash: e57470fcd8e7b014084b094c9ca5e39f0a86d85e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50630026"
---
# <a name="compiler-warning-level-4-c4706"></a>Compilerwarnung (Stufe 4) C4706

Zuweisung in bedingtem Ausdruck

Der Testwert in einem bedingten Ausdruck war das Ergebnis einer Zuweisung.

Eine Zuweisung hat es sich um einen Wert (der Wert auf der linken Seite der Zuweisung), der gesetzlich in einem anderen Ausdruck verwenden, einschließlich einem Testausdruck verwendet werden kann.

Im folgende Beispiel wird die C4706 generiert:

```
// C4706a.cpp
// compile with: /W4
int main()
{
   int a = 0, b = 0;
   if ( a  = b ) // C4706
   {
   }
}
```

Die Warnung wird auch auftreten, wenn Sie die Klammern um die testbedingung doppelklicken:

```
// C4706b.cpp
// compile with: /W4
int main()
{
   int a = 0, b = 0;
   if ( ( a  =  b ) ) // C4706
   {
   }
}
```

Wenn Sie beabsichtigen, eine Beziehung zu testen und zu verwenden, nicht um eine Zuordnung vorgenommen der `==` Operator. Z. B. die folgende Zeile wird getestet, ob ein und b sind gleich:

```
// C4706c.cpp
// compile with: /W4
int main()
{
   int a = 0, b = 0;
   if ( a == b )
   {
   }
}
```

Wenn Sie den Test mit dem Wert des Ergebnis einer Zuweisung vornehmen möchten, testen Sie, stellen Sie sicher, dass die Zuweisung nicht NULL oder not null ist. Der folgende Code generiert diese Warnung z. B. nicht:

```
// C4706d.cpp
// compile with: /W4
int main()
{
   int a = 0, b = 0;
   if ( ( a = b ) != 0 )
   {
   }
}
```
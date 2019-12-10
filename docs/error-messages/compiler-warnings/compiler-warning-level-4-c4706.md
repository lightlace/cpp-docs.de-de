---
title: Compilerwarnung (Stufe 4) C4706
ms.date: 11/04/2016
f1_keywords:
- C4706
helpviewer_keywords:
- C4706
ms.assetid: 89cd3f4f-812c-4a4b-9426-65a5a6d1b99c
ms.openlocfilehash: 2ff8794dcf29539b492f53bfdf6f0810988c0f72
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74989904"
---
# <a name="compiler-warning-level-4-c4706"></a>Compilerwarnung (Stufe 4) C4706

Zuweisung in bedingtem Ausdruck

Der Testwert in einem bedingten Ausdruck war das Ergebnis einer Zuweisung.

Eine Zuweisung verfügt über einen Wert (der Wert auf der linken Seite der Zuweisung), der in einem anderen Ausdruck, einschließlich eines Test Ausdrucks, legal verwendet werden kann.

Im folgenden Beispiel wird C4706 generiert:

```cpp
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

Die Warnung tritt auch dann auf, wenn Sie die Test Bedingung um die Klammern herum verdoppeln:

```cpp
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

Wenn Sie beabsichtigen, eine Beziehung zu testen und keine Zuweisung vorzunehmen, verwenden Sie den `==`-Operator. Die folgende Zeile testet z. b., ob a und b gleich sind:

```cpp
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

Wenn Sie beabsichtigen, den Testwert als Ergebnis einer Zuweisung zu erstellen, testen Sie, um sicherzustellen, dass die Zuweisung ungleich 0 (null) oder nicht NULL ist. Der folgende Code generiert beispielsweise keine Warnung:

```cpp
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

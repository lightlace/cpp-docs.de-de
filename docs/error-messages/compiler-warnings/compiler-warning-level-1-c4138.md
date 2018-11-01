---
title: Compilerwarnung (Stufe 1) C4138
ms.date: 11/04/2016
f1_keywords:
- C4138
helpviewer_keywords:
- C4138
ms.assetid: 65ebf929-bba0-4237-923b-c1b66adfe17d
ms.openlocfilehash: 96f8915b9bec166496ca4305d796ce8ef514ca15
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50481678"
---
# <a name="compiler-warning-level-1-c4138"></a>Compilerwarnung (Stufe 1) C4138

"*/" wurde außerhalb des Kommentars gefunden

Dem schließenden Kommentartrennzeichen geht kein öffnendes Kommentartrennzeichen voran. Der Compiler nimmt an, dass zwischen dem Sternchen (<strong>\*</strong>) und dem Schrägstrich (/) ein Leerzeichen steht.

## <a name="example"></a>Beispiel

```
// C4138a.cpp
// compile with: /W1
int */*comment*/ptr;   // C4138 Ambiguous first delimiter causes warning
int main()
{
}
```

Diese Warnung kann auf den Versuch zurückzuführen sein, Kommentare zu schachteln.

Die Warnung kann behoben werden, wenn Sie Codeabschnitte, die Kommentare enthalten, auskommentieren, den Code in einen **#if/#endif** -Block einschließen und den steuernden Ausdruck auf 0 (null) festlegen:

```
// C4138b.cpp
// compile with: /W1
#if 0
int my_variable;   /* Declaration currently not needed */
#endif
int main()
{
}
```
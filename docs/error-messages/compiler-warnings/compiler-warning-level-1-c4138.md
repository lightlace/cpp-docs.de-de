---
title: Compilerwarnung (Stufe 1) C4138 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4138
dev_langs:
- C++
helpviewer_keywords:
- C4138
ms.assetid: 65ebf929-bba0-4237-923b-c1b66adfe17d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0d2e637c73482b1a59034d6a269ea2240445bdef
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46046906"
---
# <a name="compiler-warning-level-1-c4138"></a>Compilerwarnung (Stufe 1) C4138

"*/" wurde außerhalb des Kommentars gefunden

Dem schließenden Kommentartrennzeichen geht kein öffnendes Kommentartrennzeichen voran. Der Compiler nimmt an, dass zwischen dem Sternchen (<strong>\**</strong>) und dem Schrägstrich (/) ein Leerzeichen steht.

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
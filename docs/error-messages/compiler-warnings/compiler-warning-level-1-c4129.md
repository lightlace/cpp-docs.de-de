---
title: Compilerwarnung (Stufe 1) C4129
ms.date: 11/04/2016
f1_keywords:
- C4129
helpviewer_keywords:
- C4129
ms.assetid: a4190c64-4bfb-48fd-8e98-52720bc0d878
ms.openlocfilehash: dc4f4c4c1feeba543ce0baa71e1ee5dfd81fdcae
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50428667"
---
# <a name="compiler-warning-level-1-c4129"></a>Compilerwarnung (Stufe 1) C4129

'Zeichen': nicht erkannte Zeichen-Escapesequenz

Die `character` hinter einem umgekehrten Schrägstrich (\\) in einer Zeichen- oder Konstante nicht als gültige Escape-Sequenz erkannt wird. Der umgekehrte Schrägstrich wird ignoriert und nicht gedruckt. Das Zeichen, die dem umgekehrten Schrägstrich folgt, wird ausgegeben.

Um einen einzelnen umgekehrten Schrägstrich drucken möchten, geben Sie einen doppelten umgekehrten Schrägstrich (\\\\).

Der C++-standard, klicken Sie im Abschnitt 2.13.2 werden Escape-Sequenzen.

Im folgende Beispiel wird die C4129 generiert:

```
// C4129.cpp
// compile with: /W1
int main() {
   char array1[] = "\/709";   // C4129
   char array2[] = "\n709";   // OK
}
```
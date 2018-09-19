---
title: Compilerwarnung (Stufe 1) C4129 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4129
dev_langs:
- C++
helpviewer_keywords:
- C4129
ms.assetid: a4190c64-4bfb-48fd-8e98-52720bc0d878
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6e02f38044180c45e221099d2874b7f8ff48d62f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46098445"
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
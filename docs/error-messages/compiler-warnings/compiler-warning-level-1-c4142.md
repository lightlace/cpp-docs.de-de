---
title: Compilerwarnung (Stufe 1) C4142
ms.date: 11/04/2016
f1_keywords:
- C4142
helpviewer_keywords:
- C4142
ms.assetid: 1fdfc3dc-60a2-4f00-b133-20e400f9b7a6
ms.openlocfilehash: 762f52c9f051a660cce68d424e02fc45422376e2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62302279"
---
# <a name="compiler-warning-level-1-c4142"></a>Compilerwarnung (Stufe 1) C4142

unbedenklich Neudefinition eines Typs

Ein Typ ist in einer Weise neu definiert, die keine Auswirkungen auf den generierten Code hat.

Dieser Fehler kann eine der folgenden Ursachen haben:

- Eine Memberfunktion einer abgeleiteten Klasse verfügt über einen anderen Rückgabetyp aus der entsprechenden Memberfunktion der Basisklasse.

- Ein Typ, der definiert, mit der `typedef` Befehl mit einer anderen Syntax Neudefinition.

Im folgende Beispiel wird die C4142 generiert:

```
// C4142.c
// compile with: /W1
float X2;
X2 = 2.0 + 1.0;   // C4142

int main() {
   float X2;
   X2 = 2.0 + 1.0;   // OK
}
```
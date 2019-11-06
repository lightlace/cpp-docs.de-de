---
title: Compilerwarnung (Stufe 1) C4142
ms.date: 11/04/2016
f1_keywords:
- C4142
helpviewer_keywords:
- C4142
ms.assetid: 1fdfc3dc-60a2-4f00-b133-20e400f9b7a6
ms.openlocfilehash: 97b13ad65335df435d071c106f577aefca7e072d
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2019
ms.locfileid: "73625012"
---
# <a name="compiler-warning-level-1-c4142"></a>Compilerwarnung (Stufe 1) C4142

ungutartige Neudefinition des Typs

Ein Typ wird auf eine Weise neu definiert, die keine Auswirkung auf den generierten Code hat.

Dieser Fehler kann eine der folgenden Ursachen haben:

- Eine Member-Funktion einer abgeleiteten Klasse weist einen anderen Rückgabetyp aus der entsprechenden Member-Funktion der Basisklasse auf.

- Ein mit dem `typedef`-Befehl definierter Typ wird mit einer anderen Syntax neu definiert.

Im folgenden Beispiel wird C4142 generiert:

```c
// C4142.c
// compile with: /W1
float X2;
X2 = 2.0 + 1.0;   // C4142

int main() {
   float X2;
   X2 = 2.0 + 1.0;   // OK
}
```
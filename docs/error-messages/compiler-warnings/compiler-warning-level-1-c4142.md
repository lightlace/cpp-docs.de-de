---
title: Compilerwarnung (Stufe 1) C4142 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4142
dev_langs:
- C++
helpviewer_keywords:
- C4142
ms.assetid: 1fdfc3dc-60a2-4f00-b133-20e400f9b7a6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 011f71c1d57f03c2be9bac3df67cd0ed90aa8017
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46117386"
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
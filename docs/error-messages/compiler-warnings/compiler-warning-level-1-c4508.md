---
title: Compilerwarnung (Stufe 1) C4508
ms.date: 11/04/2016
f1_keywords:
- C4508
helpviewer_keywords:
- C4508
ms.assetid: c05f113b-b789-4df0-a4ef-78bce4767021
ms.openlocfilehash: 394a59a472100cc30476b5bb87f30c45d867f94b
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966297"
---
# <a name="compiler-warning-level-1-c4508"></a>Compilerwarnung (Stufe 1) C4508

"Function": Funktion sollte einen Wert zurückgeben. der Rückgabetyp "void" wird angenommen

Für die Funktion wurde kein Rückgabetyp angegeben. In diesem Fall sollte auch C4430 ausgelöst werden, und der Compiler implementiert die von C4430 gemeldete Korrektur (Standardwert ist int).

Um diese Warnung zu beheben, deklarieren Sie explizit den Rückgabetyp der Funktionen.

Im folgenden Beispiel wird C4508 generiert:

```cpp
// C4508.cpp
// compile with: /W1 /c
#pragma warning (disable : 4430)
func() {}   // C4508
void func2() {}   // OK
```
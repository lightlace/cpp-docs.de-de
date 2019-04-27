---
title: Compilerwarnung (Stufe 1) C4508
ms.date: 11/04/2016
f1_keywords:
- C4508
helpviewer_keywords:
- C4508
ms.assetid: c05f113b-b789-4df0-a4ef-78bce4767021
ms.openlocfilehash: c96db3d4bd1124c96b22363531b7739d0757b613
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160808"
---
# <a name="compiler-warning-level-1-c4508"></a>Compilerwarnung (Stufe 1) C4508

'Funktion': Funktion sollte einen Wert zurückgeben "void" Rückgabetyp davon ausgegangen, dass

Die Funktion weist kein Rückgabetyp angegeben. In diesem Fall C4430 ebenfalls ausgelöst, und der Compiler implementiert die C4430 (Standardmäßig ist der Wert ist vom Datentyp Int) gemeldet.

Um diese Warnung zu beheben, müssen deklarieren Sie den Rückgabetyp der Funktionen explizit.

Im folgende Beispiel wird die C4508 generiert:

```
// C4508.cpp
// compile with: /W1 /c
#pragma warning (disable : 4430)
func() {}   // C4508
void func2() {}   // OK
```
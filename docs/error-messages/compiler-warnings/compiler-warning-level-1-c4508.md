---
title: Compilerwarnung (Stufe 1) C4508 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4508
dev_langs:
- C++
helpviewer_keywords:
- C4508
ms.assetid: c05f113b-b789-4df0-a4ef-78bce4767021
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e5abc1d81c3e94c02a63f73c84f3f5e5c7e9b0b0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46038939"
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
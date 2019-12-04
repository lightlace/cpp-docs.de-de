---
title: Compilerfehler C2548
ms.date: 11/04/2016
f1_keywords:
- C2548
helpviewer_keywords:
- C2548
ms.assetid: 01e9c835-9bf3-4020-9295-5ee448c519f3
ms.openlocfilehash: f89208314c1d2e8ddb5100da72aa600a411b4608
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756798"
---
# <a name="compiler-error-c2548"></a>Compilerfehler C2548

' Class:: Member ': fehlender Standardparameter für Parameter Parameter.

In der Standardparameter Liste fehlt ein Parameter. Wenn Sie einen Standardparameter an einer beliebigen Stelle in einer Parameterliste angeben, müssen Sie für alle nachfolgenden Parameter Standardparameter definieren.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2548 generiert:

```cpp
// C2548.cpp
// compile with: /c
void func( int = 1, int, int = 3);  // C2548

// OK
void func2( int, int, int = 3);
void func3( int, int = 2, int = 3);
```

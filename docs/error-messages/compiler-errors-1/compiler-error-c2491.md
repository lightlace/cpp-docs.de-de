---
title: Compilerfehler C2491
ms.date: 11/04/2016
f1_keywords:
- C2491
helpviewer_keywords:
- C2491
ms.assetid: 4e5a8f81-124e-402c-a5ec-d35a89b5469e
ms.openlocfilehash: 7ee7fb6e66ca9d5e09ad0eb445262c5f87d2060e
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757071"
---
# <a name="compiler-error-c2491"></a>Compilerfehler C2491

'Bezeichner': Definition von Dllimport-Funktion nicht zulässig

Daten, statische Datenmember und Funktionen können als `dllimport`s deklariert werden, jedoch nicht als `dllimport`s definiert werden.

Um dieses Problem zu beheben, entfernen Sie den `__declspec(dllimport)`-Bezeichner aus der Definition der Funktion.

Im folgenden Beispiel wird C2491 generiert:

```cpp
// C2491.cpp
// compile with: /c
// function definition
void __declspec(dllimport) funcB() {}   // C2491

// function declaration
void __declspec(dllimport) funcB();   // OK
```

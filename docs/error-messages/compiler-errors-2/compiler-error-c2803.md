---
title: Compilerfehler C2803
ms.date: 11/04/2016
f1_keywords:
- C2803
helpviewer_keywords:
- C2803
ms.assetid: 2cdbe374-8cc4-4c4e-ba15-062a7479e937
ms.openlocfilehash: d39f737ba02f3fa9c9d5f61594ddf730db6739a5
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760659"
---
# <a name="compiler-error-c2803"></a>Compilerfehler C2803

"Operator Operator" muss mindestens einen formalen Parameter vom Typ "Class" aufweisen.

Dem überladenen Operator fehlt ein Parameter des Klassen Typs.

Sie müssen mindestens einen Parameter als Verweis übergeben (ohne Zeiger, aber Verweise) oder nach Wert, um "a < b" schreiben zu können (a und b sind vom Typ Klasse a).

Wenn beide Parameter Zeiger sind, handelt es sich um einen reinen Vergleich von Zeiger Adressen, und es wird keine benutzerdefinierte Konvertierung verwendet.

Im folgenden Beispiel wird C2803 generiert:

```cpp
// C2803.cpp
// compile with: /c
class A{};
bool operator< (const A *left, const A *right);   // C2803
// try the following line instead
// bool operator< (const A& left, const A& right);
```

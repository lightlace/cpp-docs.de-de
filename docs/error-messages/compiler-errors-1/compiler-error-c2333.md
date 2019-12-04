---
title: Compilerfehler C2333
ms.date: 11/04/2016
f1_keywords:
- C2333
helpviewer_keywords:
- C2333
ms.assetid: 2636fc1e-d3e7-4e68-8628-3c81a99ba813
ms.openlocfilehash: cca7f0d3bd75cca8fdd621fb425dec42e6560f4e
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74747747"
---
# <a name="compiler-error-c2333"></a>Compilerfehler C2333

"Function": Fehler in Funktionsdeklaration; der Funktions Text wird übersprungen.

Dieser Fehler tritt nach einem anderen Fehler auf, der in der Klasse definiert ist.

Im folgenden Beispiel wird C2333 generiert:

```cpp
// C2333.cpp
struct s1 {
   s1(s1) {}   // C2333
};
```

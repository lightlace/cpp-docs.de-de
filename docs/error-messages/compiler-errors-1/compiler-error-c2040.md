---
title: Compilerfehler C2040
ms.date: 11/04/2016
f1_keywords:
- C2040
helpviewer_keywords:
- C2040
ms.assetid: 74ca3592-1469-4965-ab34-a4815e2fbefe
ms.openlocfilehash: 8002d7168354b1213d01ca390a03b1baa5e35c88
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74740415"
---
# <a name="compiler-error-c2040"></a>Compilerfehler C2040

„Operator“: „Bezeichner1“ unterscheidet sich in Ebenen der Dereferenzierung von „Bezeichner2“.

Ein Ausdruck, der die angegebenen Operanden beinhaltet, verfügt über nicht kompatible oder implizit konvertierte Operandentypen. Wenn beide Operanden arithmetisch bzw. beide Operatoren nicht arithmetisch sind (z. B. Array oder Zeiger), werden sie unverändert verwendet. Wenn ein Operand arithmetisch ist und der andere nicht, wird der arithmetische Operand in den Typ des nicht arithmetischen Operanden konvertiert.

Im folgenden Beispiel wird C2040 generiert und gezeigt, wie Sie diesen Fehler beheben.

```cpp
// C2040.cpp
// Compile by using: cl /c /W3 C2040.cpp
bool test() {
   char c = '3';
   return c == "3"; // C2446, C2040
   // return c == '3'; // OK
}
```

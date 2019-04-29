---
title: Compilerfehler C2040
ms.date: 11/04/2016
f1_keywords:
- C2040
helpviewer_keywords:
- C2040
ms.assetid: 74ca3592-1469-4965-ab34-a4815e2fbefe
ms.openlocfilehash: b45ec25f1ed516ae73b242fdcc7c66f68c92f724
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62387109"
---
# <a name="compiler-error-c2040"></a>Compilerfehler C2040

„Operator“: „Bezeichner1“ unterscheidet sich in Ebenen der Dereferenzierung von „Bezeichner2“.

Ein Ausdruck, der die angegebenen Operanden beinhaltet, verfügt über nicht kompatible oder implizit konvertierte Operandentypen. Wenn beide Operanden arithmetisch bzw. beide Operatoren nicht arithmetisch sind (z. B. Array oder Zeiger), werden sie unverändert verwendet. Wenn ein Operand arithmetisch ist und der andere nicht, wird der arithmetische Operand in den Typ des nicht arithmetischen Operanden konvertiert.

Im folgenden Beispiel wird C2040 generiert und gezeigt, wie Sie diesen Fehler beheben.

```
// C2040.cpp
// Compile by using: cl /c /W3 C2040.cpp
bool test() {
   char c = '3';
   return c == "3"; // C2446, C2040
   // return c == '3'; // OK
}
```
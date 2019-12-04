---
title: Compilerfehler C2422
ms.date: 11/04/2016
f1_keywords:
- C2422
helpviewer_keywords:
- C2422
ms.assetid: ef0ec302-4028-4778-b134-0b8cea4bcad9
ms.openlocfilehash: 39f779ee846cf4f328f9c7af59ae394d97d7a3ca
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74744731"
---
# <a name="compiler-error-c2422"></a>Compilerfehler C2422

Ungültige Segment Überschreibung in "Operand"

Inline-Assemblycode verwendet fälschlicherweise einen Segment Überschreibungs Operator (Doppelpunkt) für einen Operanden.  Folgende Ursachen sind möglich:

- Das Register vor dem Operator ist kein Segment Register.

- Das Register, das dem Operator vorangestellt ist, ist nicht das einzige Segment Register im Operanden.

- Der Segment Überschreibungs Operator wird innerhalb eines Dereferenzierungsoperators (eckige Klammern) angezeigt.

- Der Ausdruck, der auf den Segment Überschreibungs Operator folgt, ist kein unmittelbarer Operand oder Speicher Operand.

Im folgenden Beispiel wird C2422 generiert:

```cpp
// C2422.cpp
// processor: x86
int main() {
   _asm {
      mov AX, [BX:ES]   // C2422
      mov AX, ES   // OK
   }
}
```

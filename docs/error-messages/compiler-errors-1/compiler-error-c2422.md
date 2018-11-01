---
title: Compilerfehler C2422
ms.date: 11/04/2016
f1_keywords:
- C2422
helpviewer_keywords:
- C2422
ms.assetid: ef0ec302-4028-4778-b134-0b8cea4bcad9
ms.openlocfilehash: 524eeadb6cf066d3eba3a7e88c45a9e2b993c0ae
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50509134"
---
# <a name="compiler-error-c2422"></a>Compilerfehler C2422

Unzulässige direkte segmentüberschreibung in "Operand"

Inline-Assemblycode verwendet fälschlicherweise einen Segment außer Kraft setzen-Operator (Doppelpunkt) bei einem Operanden aus.  Mögliche Ursachen sind:

- Das Register, die vor der Operator ist kein Segmentregister.

- Das Register, die vor der Operator ist nicht das einzige Segmentregister im Operanden.

- Die Segment-Operator außer Kraft setzen, wird in ein Dereferenzierungsoperator (eckige Klammern) angezeigt.

- Der Ausdruck nach dem die Außerkraftsetzung Segment-Operator ist nicht unmittelbarer Operand oder einen Speicheroperanden.

Im folgende Beispiel wird die C2422 generiert:

```
// C2422.cpp
// processor: x86
int main() {
   _asm {
      mov AX, [BX:ES]   // C2422
      mov AX, ES   // OK
   }
}
```
---
title: Compilerfehler C2422 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2422
dev_langs:
- C++
helpviewer_keywords:
- C2422
ms.assetid: ef0ec302-4028-4778-b134-0b8cea4bcad9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 17421f2d4a7823c0e2fbb34a54a7c562223c798c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46047030"
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
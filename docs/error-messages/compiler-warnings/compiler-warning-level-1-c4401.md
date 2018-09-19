---
title: Compilerwarnung (Stufe 1) C4401 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4401
dev_langs:
- C++
helpviewer_keywords:
- C4401
ms.assetid: 2e7ca136-f144-4b40-b847-82976e8643fc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5f9f7bfcf826b9bda4232a8f4068d8be45dc3ab5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46043546"
---
# <a name="compiler-warning-level-1-c4401"></a>Compilerwarnung (Stufe 1) C4401

"Bitfeld": Member ist ein Bitfeld

Inline-Assemblycode versucht, die Zugriff auf einen Member Bitfeld. Inline-Assembly kann nicht Bitfeldmember, zugreifen, damit die letzte Ausrichtungsgrenze vor dem Bitfeld-Element verwendet wird.

Um diese Warnung zu vermeiden, wandeln Sie das Bitfeld in einen geeigneten Typ vor dem Übermitteln des Verweis Inline-Assemblycode. Im folgende Beispiel wird die C4401 generiert:

```
// C4401.cpp
// compile with: /W1
// processor: x86
typedef struct bitfield {
   signed bit : 1;
} mybitfield;

int main() {
   mybitfield bf;
   bf.bit = 0;
   __asm {
      mov bf.bit,0;   // C4401
   }

   /* use the following __asm block to resolve the warning
   int i = (int)bf.bit;
   __asm {
      mov i,0;
   }
   */
}
```
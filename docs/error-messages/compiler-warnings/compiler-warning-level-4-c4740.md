---
title: Compilerwarnung (Stufe 4) C4740
ms.date: 11/04/2016
f1_keywords:
- C4740
helpviewer_keywords:
- C4740
ms.assetid: 85528969-966a-44b4-8a2f-971704c64477
ms.openlocfilehash: 679f577eb7911b401473ee570e367ed5a8a094eb
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74989488"
---
# <a name="compiler-warning-level-4-c4740"></a>Compilerwarnung (Stufe 4) C4740

Flow in oder aus Inline-ASM-Code unterdrückt globale Optimierung

Wenn ein `asm` Block ein-oder ausspringt, sind globale Optimierungen für diese Funktion deaktiviert.

Im folgenden Beispiel wird C4740 generiert:

```cpp
// C4740.cpp
// compile with: /O2 /W4
// processor: x86
int main() {
   __asm jmp tester
   tester:;
}
```

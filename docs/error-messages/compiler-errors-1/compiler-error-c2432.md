---
title: Compilerfehler C2432
ms.date: 11/04/2016
f1_keywords:
- C2432
helpviewer_keywords:
- C2432
ms.assetid: 0e3326e8-cab1-45a5-b48d-61edd33793e8
ms.openlocfilehash: d4234626bc246d6da87be68b03d44562dd5990ff
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74744510"
---
# <a name="compiler-error-c2432"></a>Compilerfehler C2432

Unzulässiger Verweis auf 16-Bit-Daten in "Identifier".

Ein 16-Bit-Register wird als Index oder Basisregister verwendet. Der Compiler unterstützt keinen Verweis auf 16-Bit-Daten. 16-Bit-Register können nicht als Index-oder Basisregister verwendet werden, wenn für 32-Bit-Code kompiliert wird.

Im folgenden Beispiel wird C2432 generiert:

```cpp
// C2432.cpp
// processor: x86
int main() {
   _asm mov eax, DWORD PTR [bx]   // C2432
}
```

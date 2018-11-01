---
title: Compilerfehler C2432
ms.date: 11/04/2016
f1_keywords:
- C2432
helpviewer_keywords:
- C2432
ms.assetid: 0e3326e8-cab1-45a5-b48d-61edd33793e8
ms.openlocfilehash: e2983d966a6290ce19713c63feb502c8ffc74bf1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50631237"
---
# <a name="compiler-error-c2432"></a>Compilerfehler C2432

illegaler Verweis auf 16-Bit-Daten in 'Bezeichner'

Ein 16-Bit-Register wird als ein Index oder ein Basisregister verwendet. Der Compiler unterstützt nicht das Verweisen auf 16-Bit-Daten. 16-Bit-Register können nicht als Index oder Basisregister verwendet werden, bei der Kompilierung für 32-Bit-Code.

Im folgende Beispiel wird die C2432 generiert:

```
// C2432.cpp
// processor: x86
int main() {
   _asm mov eax, DWORD PTR [bx]   // C2432
}
```
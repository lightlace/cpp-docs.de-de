---
title: Compilerfehler C2432 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2432
dev_langs:
- C++
helpviewer_keywords:
- C2432
ms.assetid: 0e3326e8-cab1-45a5-b48d-61edd33793e8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9ca8c2c62415b6ec3c29c820a23677a87a2695c5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46055909"
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
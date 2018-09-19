---
title: Compilerwarnung (Stufe 1) C4630 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4630
dev_langs:
- C++
helpviewer_keywords:
- C4630
ms.assetid: d8926376-7acc-4fc7-8438-6f0de3468870
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dadfd4cd38d1b1d0e67e49e81102135a8ced1d00
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46054726"
---
# <a name="compiler-warning-level-1-c4630"></a>Compilerwarnung (Stufe 1) C4630

'Symbol': Speicherklassenspezifizierer "Extern" nicht für Elementdefinition

Ein Datenmember oder eine Memberfunktion ist definiert als `extern`. Member können nicht extern und sein, jedoch können komplette Objekte. Der Compiler ignoriert die `extern` Schlüsselwort. Im folgende Beispiel wird die C4630 generiert:

```
// C4630.cpp
// compile with: /W1 /LD
class A {
   void func();
};

extern void A::func() {   // C4630, remove 'extern' to resolve
}
```
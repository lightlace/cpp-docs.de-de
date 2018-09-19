---
title: Compilerfehler C3866 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3866
dev_langs:
- C++
helpviewer_keywords:
- C3866
ms.assetid: 685870af-2440-4cdf-a6cb-284a5b96ef9d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eb56440dd67bc59e7719acdf70cee2784c889db2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46048902"
---
# <a name="compiler-error-c3866"></a>Compilerfehler C3866

die Argumentliste der Funktion Aufruf fehlt

In einer nicht statischen Member-Funktion ein Destruktor oder Finalizer-Aufruf eine Argumentliste keine.

Im folgende Beispiel wird die C3866 generiert:

```
// C3866.cpp
// compile with: /c
class C {
   ~C();
   void f() {
      this->~C;   // C3866
      this->~C();   // OK
   }
};
```
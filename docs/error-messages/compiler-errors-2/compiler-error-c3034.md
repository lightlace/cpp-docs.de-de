---
title: Compilerfehler C3034 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3034
dev_langs:
- C++
helpviewer_keywords:
- C3034
ms.assetid: 49db8bac-2720-4622-94e3-7988f1603fa3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6e3d96e975450241a5baae60758beadfe40dbe5e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46091457"
---
# <a name="compiler-error-c3034"></a>Compilerfehler C3034

Die OpenMP directive1-Direktive von kann nicht direkt in der directive1-Direktive geschachtelt werden.

Bestimmte Direktiven können nicht geschachtelt werden. Um diesen Fehler zu beheben, können Sie die Anweisungen der beiden Direktiven in den Block einer Direktive zusammenführen, oder Sie können aufeinander folgende Direktiven erstellen.

Im folgenden Beispiel wird C3034 generiert:

```
// C3034.cpp
// compile with: /openmp /link vcomps.lib
int main() {

   #pragma omp single
   {
      #pragma omp single   // C3034
      {
      ;
      }
   }

   // Two consecutive single clauses are OK.
   #pragma omp single
   {
   }

   #pragma omp single
   {
   }
}
```
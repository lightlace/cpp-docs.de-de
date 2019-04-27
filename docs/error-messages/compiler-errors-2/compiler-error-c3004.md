---
title: Compilerfehler C3004
ms.date: 11/04/2016
f1_keywords:
- C3004
helpviewer_keywords:
- C3004
ms.assetid: 819c2b57-8366-4ca7-9135-1f0c5e5b6bb6
ms.openlocfilehash: 88f781f8cb3e661998651bb4b1a7b0d54b183a0a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62208281"
---
# <a name="compiler-error-c3004"></a>Compilerfehler C3004

„clause“: Die Klausel ist für die directive-Direktive von OpenMP nicht gültig.

Eine OpenMP-Klausel wurde in einer Direktive verwendet, für die sie nicht aktiviert ist.

Im folgenden Beispiel wird C3004 generiert:

```
// C3004.c
// compile with: /openmp
int main()
{
   int x, y, z;

   // Shared clause not allowed for 'single' directive.
   #pragma omp single shared(x, y)   // C3004

   x = y;
}
```
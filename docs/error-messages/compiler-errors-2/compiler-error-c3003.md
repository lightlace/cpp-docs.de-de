---
title: Compilerfehler C3003
ms.date: 11/04/2016
f1_keywords:
- C3003
helpviewer_keywords:
- C3003
ms.assetid: 22e74f99-bb7f-4518-ab0d-934d5d49bcc7
ms.openlocfilehash: 6d15d8bde8855b8dcc4857492acdeb950731b503
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62152500"
---
# <a name="compiler-error-c3003"></a>Compilerfehler C3003

'Direktive': OpenMP-Direktivenname nach Direktivenklauseln nicht zulässig.

Ein OpenMP-Direktivenname darf nicht auf eine OpenMP-Direktivenklausel folgen.

Im folgenden Beispiel wird C3003 generiert:

```
// C3003.c
// compile with: /openmp
int main()
{
   int x, y, z;
   #pragma omp parallel shared(x, y, z) for   // C3003
}
```
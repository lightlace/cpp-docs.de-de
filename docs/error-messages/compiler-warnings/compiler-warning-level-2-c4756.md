---
title: Compilerwarnung (Stufe 2) C4756
ms.date: 11/04/2016
f1_keywords:
- C4756
helpviewer_keywords:
- C4756
ms.assetid: 5a16df83-6b82-4619-83bd-319af4ef1d1d
ms.openlocfilehash: 0e4e0d5e227795a45eb22e3fcb17bdfa600d69e9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402423"
---
# <a name="compiler-warning-level-2-c4756"></a>Compilerwarnung (Stufe 2) C4756

Überlauf bei arithmetischer Auswertung einer Konstanten

Der Compiler hat eine Ausnahme während der Durchführung von Arithmetik während der Kompilierung generiert.

Im folgende Beispiel wird die C4756 generiert:

```
// C4756.cpp
// compile with: /W2 /Od
int main()
{
   float f = 1e100+1e100;   // C4756
}
```
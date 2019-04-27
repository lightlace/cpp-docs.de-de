---
title: Compilerwarnung (Stufe 1) C4227
ms.date: 11/04/2016
f1_keywords:
- C4227
helpviewer_keywords:
- C4227
ms.assetid: 78f98374-c00b-4000-aefa-1b1c67b4666b
ms.openlocfilehash: a93b7f225149f9b557ad6238376ffd1bafec82d3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62207537"
---
# <a name="compiler-warning-level-1-c4227"></a>Compilerwarnung (Stufe 1) C4227

Anachronismus verwendet: Qualifizierer auf Verweise werden ignoriert.

Mithilfe von Qualifizierern wie `const` oder `volatile` mit C++-Verweise ist eine veraltete Methode.

## <a name="example"></a>Beispiel

```
// C4227.cpp
// compile with: /W1 /c
int j = 0;
int &const i = j;   // C4227
```
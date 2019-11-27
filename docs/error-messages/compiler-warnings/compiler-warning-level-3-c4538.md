---
title: Compilerwarnung (Stufe 3) C4538
ms.date: 11/04/2016
f1_keywords:
- C4538
helpviewer_keywords:
- C4538
ms.assetid: 747e3d51-b6d0-41c1-a726-7af3253b59d7
ms.openlocfilehash: b60d919952b07e63d28a373414f1307d2031f00d
ms.sourcegitcommit: 217fac22604639ebd62d366a69e6071ad5b724ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2019
ms.locfileid: "74188950"
---
# <a name="compiler-warning-level-3-c4538"></a>Compilerwarnung (Stufe 3) C4538

"Typ": Konstante/volatile-Qualifizierer für diesen Typ werden nicht unterstützt.

Ein qualifizierungsschlüsselwort wurde falsch auf ein Array angewendet. Weitere Informationen finden Sie unter [Array](../../extensions/arrays-cpp-component-extensions.md).

Im folgenden Beispiel wird C4538 generiert:

```cpp
// C4538.cpp
// compile with: /clr /W3 /LD
const array<int> ^f1();   // C4538
array<const int> ^f2();   // OK
```
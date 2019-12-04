---
title: Compilerfehler C3886
ms.date: 11/04/2016
f1_keywords:
- C3886
helpviewer_keywords:
- C3886
ms.assetid: 485f6c12-cc1b-4146-9034-409a0a5e615e
ms.openlocfilehash: 2e7ba0fcc76d723cebb5b82315faf36313b1d7db
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74736632"
---
# <a name="compiler-error-c3886"></a>Compilerfehler C3886

"var": ein literaldatenmember muss initialisiert werden.

Eine [literalvariable](../../extensions/literal-cpp-component-extensions.md) muss bei deklaralisierung initialisiert werden.

Im folgenden Beispiel wird C3886 generiert:

```cpp
// C3886.cpp
// compile with: /clr /c
ref struct Y1 {
   literal int staticConst;   // C3886
   literal int staticConst2 = 0;   // OK
};
```

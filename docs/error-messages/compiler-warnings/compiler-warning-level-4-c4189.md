---
title: Compilerwarnung (Stufe 4) C4189
ms.date: 11/04/2016
f1_keywords:
- C4189
helpviewer_keywords:
- C4189
ms.assetid: 7ad9242c-228e-4054-8244-5e914b618ef3
ms.openlocfilehash: d403373fe200f10cb2f2c210b8cd8f58b7429198
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74991511"
---
# <a name="compiler-warning-level-4-c4189"></a>Compilerwarnung (Stufe 4) C4189

"Bezeichner": Lokale Variable ist initialisiert, aber nicht referenziert

Eine Variable wird deklariert und initialisiert, aber nicht verwendet.

Im folgenden Beispiel wird C4189 generiert.

```cpp
// C4189.cpp
// compile with: /W4
int main() {
   int a = 1;   // C4189, remove declaration to resolve
}
```

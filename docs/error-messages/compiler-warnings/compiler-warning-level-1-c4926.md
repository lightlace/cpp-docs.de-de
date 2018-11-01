---
title: Compilerwarnung (Stufe 1) C4926
ms.date: 11/04/2016
f1_keywords:
- C4926
helpviewer_keywords:
- C4926
ms.assetid: 5717fce0-146f-4ef2-bde0-e9a01c0922d1
ms.openlocfilehash: 839d0b8ffad947e7031ca618b255588f54b82770
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50634901"
---
# <a name="compiler-warning-level-1-c4926"></a>Compilerwarnung (Stufe 1) C4926

"Bezeichner": Symbol ist bereits definiert: Attribute werden ignoriert

Es wurde eine Vorausdeklaration gefunden, aber ein attributiertes Konstrukt mit demselben Namen ist bereits vorhanden. Die Attribute für die Vorausdeklaration werden ignoriert.

Im folgenden Beispiel wird C4926 generiert.

```
// C4926.cpp
// compile with: /W1
[module(name="MyLib")];

[coclass]
struct a {
};

[coclass]
struct a;   // C4926

int main() {
}
```
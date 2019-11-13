---
title: Compilerwarnung (Stufe 1) C4926
ms.date: 11/04/2016
f1_keywords:
- C4926
helpviewer_keywords:
- C4926
ms.assetid: 5717fce0-146f-4ef2-bde0-e9a01c0922d1
ms.openlocfilehash: a68e251209cb9664552b4324de108f2cf7ce3f37
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2019
ms.locfileid: "74050218"
---
# <a name="compiler-warning-level-1-c4926"></a>Compilerwarnung (Stufe 1) C4926

"Bezeichner": Symbol ist bereits definiert: Attribute werden ignoriert

Es wurde eine Vorausdeklaration gefunden, aber ein attributiertes Konstrukt mit demselben Namen ist bereits vorhanden. Die Attribute für die Vorausdeklaration werden ignoriert.

Im folgenden Beispiel wird C4926 generiert.

```cpp
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
---
title: Compilerwarnung (Stufe 1) C4926
ms.date: 11/04/2016
f1_keywords:
- C4926
helpviewer_keywords:
- C4926
ms.assetid: 5717fce0-146f-4ef2-bde0-e9a01c0922d1
ms.openlocfilehash: 839d0b8ffad947e7031ca618b255588f54b82770
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62393466"
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
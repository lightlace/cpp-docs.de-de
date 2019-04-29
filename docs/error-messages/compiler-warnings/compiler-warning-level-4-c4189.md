---
title: Compilerwarnung (Stufe 4) C4189
ms.date: 11/04/2016
f1_keywords:
- C4189
helpviewer_keywords:
- C4189
ms.assetid: 7ad9242c-228e-4054-8244-5e914b618ef3
ms.openlocfilehash: 6463379529897598d560d6bcc22bd3a278a66477
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401279"
---
# <a name="compiler-warning-level-4-c4189"></a>Compilerwarnung (Stufe 4) C4189

"Bezeichner": Lokale Variable ist initialisiert, aber nicht referenziert

Eine Variable wird deklariert und initialisiert, aber nicht verwendet.

Im folgenden Beispiel wird C4189 generiert.

```
// C4189.cpp
// compile with: /W4
int main() {
   int a = 1;   // C4189, remove declaration to resolve
}
```
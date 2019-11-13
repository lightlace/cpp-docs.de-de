---
title: Compilerwarnung (Stufe 3) C4390
ms.date: 11/04/2016
f1_keywords:
- C4390
helpviewer_keywords:
- C4390
ms.assetid: c95c2f1b-9bce-4b1f-a80c-565d4cde0b1e
ms.openlocfilehash: 8402c6a2d0fcbb4704b833ac7ae2b070c7af3a48
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2019
ms.locfileid: "74051591"
---
# <a name="compiler-warning-level-3-c4390"></a>Compilerwarnung (Stufe 3) C4390

";": leere kontrollierte Anweisung gefunden; ist das beabsichtigt?

Ein Semikolon wurde nach einer Steuerelement Anweisung gefunden, die keine Anweisungen enthält.

Wenn Sie C4390 aufgrund eines Makros erhalten, sollten Sie das [Warning](../../preprocessor/warning.md) -Pragma verwenden, um C4390 im Modul zu deaktivieren, das das Makro enthält.

Im folgenden Beispiel wird C4390 generiert:

```cpp
// C4390.cpp
// compile with: /W3
int main() {
   int i = 0;
   if (i);   // C4390
      i++;
}
```
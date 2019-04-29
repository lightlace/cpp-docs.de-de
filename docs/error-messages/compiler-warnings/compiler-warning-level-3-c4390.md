---
title: Compilerwarnung (Stufe 3) C4390
ms.date: 11/04/2016
f1_keywords:
- C4390
helpviewer_keywords:
- C4390
ms.assetid: c95c2f1b-9bce-4b1f-a80c-565d4cde0b1e
ms.openlocfilehash: 4ca00f892adc8fe3ac1bffb59a27ea1744249dea
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401981"
---
# <a name="compiler-warning-level-3-c4390"></a>Compilerwarnung (Stufe 3) C4390

";": leere kontrollierte Anweisung aufgetreten; ist dies beabsichtigt?

Ein Semikolon wurde nach einer Control-Anweisung gefunden, die keine Anweisungen enthält.

Wenn Sie wegen eines Makros C4390 erhalten, verwenden Sie die [Warnung](../../preprocessor/warning.md) Pragma, um das Modul mit dem Makro C4390 deaktivieren.

Im folgende Beispiel wird die C4390 generiert:

```
// C4390.cpp
// compile with: /W3
int main() {
   int i = 0;
   if (i);   // C4390
      i++;
}
```
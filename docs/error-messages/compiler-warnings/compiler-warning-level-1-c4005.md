---
title: Compilerwarnung (Stufe 1) C4005
ms.date: 11/04/2016
f1_keywords:
- C4005
helpviewer_keywords:
- C4005
ms.assetid: 7f2dc79a-9fcb-4d5b-be61-120d9cb487ad
ms.openlocfilehash: 71b23ec719198d15a99b4fcfd50db8b151e03226
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2019
ms.locfileid: "73627358"
---
# <a name="compiler-warning-level-1-c4005"></a>Compilerwarnung (Stufe 1) C4005

"Bezeichner": Makro Neudefinition

Der Makro Bezeichner wird zweimal definiert. Der Compiler verwendet die zweite Makro Definition.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:

1. Definieren eines Makros in der Befehlszeile und im Code mit einer `#define`-Direktive.

1. Makros, die aus Includedateien importiert wurden.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>So beheben Sie den Fehler (unterschiedliche Lösungsmöglichkeiten)

1. Entfernen Sie eine der Definitionen.

1. Verwenden Sie eine [#undef](../../preprocessor/hash-undef-directive-c-cpp.md) -Direktive vor der zweiten Definition.

Im folgenden Beispiel wird C4005 generiert:

```cpp
// C4005.cpp
// compile with: /W1 /EHsc
#include <iostream>
using namespace std;

#define TEST "test1"
#define TEST "test2"   // C4005 delete or rename to resolve the warning

int main() {
   cout << TEST << endl;
}
```
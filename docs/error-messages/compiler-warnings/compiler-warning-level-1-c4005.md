---
title: Compilerwarnung (Stufe 1) C4005
ms.date: 11/04/2016
f1_keywords:
- C4005
helpviewer_keywords:
- C4005
ms.assetid: 7f2dc79a-9fcb-4d5b-be61-120d9cb487ad
ms.openlocfilehash: 76aab2160bd5f7918771dcf63b7297a869da751e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62187338"
---
# <a name="compiler-warning-level-1-c4005"></a>Compilerwarnung (Stufe 1) C4005

'Bezeichner': Makro-Neudefinition

Die Makro-ID ist zweimal definiert. Der Compiler verwendet die zweite Makrodefinition.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:

1. Definieren ein Makro aus, in der Befehlszeile und im Code durch einen `#define` Richtlinie.

1. Makros, die aus der Include-Dateien importiert werden.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>So beheben Sie den Fehler (unterschiedliche Lösungsmöglichkeiten)

1. Entfernen Sie eine der Definitionen.

1. Verwenden einer [#undef](../../preprocessor/hash-undef-directive-c-cpp.md) Direktive, bevor Sie die zweite Definition.

Im folgende Beispiel wird die C4005 generiert:

```
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
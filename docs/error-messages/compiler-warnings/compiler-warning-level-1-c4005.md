---
title: Compilerwarnung (Stufe 1) C4005 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4005
dev_langs:
- C++
helpviewer_keywords:
- C4005
ms.assetid: 7f2dc79a-9fcb-4d5b-be61-120d9cb487ad
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8be172086e316c991f461b3ac42f58739801cfa7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46022967"
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
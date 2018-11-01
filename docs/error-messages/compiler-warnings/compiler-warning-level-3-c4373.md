---
title: Compilerwarnung (Stufe 3) C4373
ms.date: 11/04/2016
f1_keywords:
- C4373
helpviewer_keywords:
- C4373
ms.assetid: 670c0ba3-b7d6-4aed-b207-1cb84da3bcde
ms.openlocfilehash: 031b32a03d93a51f6fa00041a5b0bdf99e6eacf1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50456055"
---
# <a name="compiler-warning-level-3-c4373"></a>Compilerwarnung (Stufe 3) C4373

> "*Funktion*": virtuelle Funktion überschreibt*Basisfunktion*', frühere Versionen des Compilers nicht überschrieben, wenn der Parameter nur durch Const/Volatile-Qualifizierer Compilerversionen

## <a name="remarks"></a>Hinweise

Die Anwendung enthält eine Methode in einer abgeleiteten Klasse, die eine virtuelle Methode in einer Basisklasse überschreibt, und die Parameter in der überschreibenden Methode unterscheiden sich nur durch einen [const](../../cpp/const-cpp.md) - oder [volatile](../../cpp/volatile-cpp.md) -Qualifizierer von den Parametern der virtuellen Methode. Dies bedeutet, dass der Compiler einen Funktionsverweis an die Methode in der Basisklasse oder abgeleiteten Klasse binden muss.

Versionen des Compilers vor Visual Studio 2008 binden die Funktion an die Methode in der Basisklasse und geben dann eine Warnmeldung angezeigt. Nachfolgende Versionen des Compilers ignorieren die `const` oder `volatile` Qualifizierer, binden die Funktion an die Methode in der abgeleiteten Klasse und dann die Warnung **C4373**. Das zuletzt genannte Verhalten entspricht dem C++-Standard.

## <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird die Warnung C4373 generiert: Um dieses Problem zu beheben, können Sie entweder vornehmen, überschreiben die gleichen CV-Qualifizierer als die Basis-Member-Funktion verwenden, oder wenn Sie nicht, dass Sie eine Außerkraftsetzung erstellen möchten, Sie erhalten der Funktion in der abgeleiteten Klasse einen anderen Namen.

```cpp
// c4373.cpp
// compile with: /c /W3
#include <stdio.h>
struct Base
{
    virtual void f(int i) {
        printf("base\n");
    }
};

struct Derived : Base
{
    void f(const int i) {  // C4373
        printf("derived\n");
    }
};

void main()
{
    Derived d;
    Base* p = &d;
    p->f(1);
}
```

```Output
derived
```
---
title: Compilerwarnung (Stufe 3) C4373
ms.date: 11/04/2016
f1_keywords:
- C4373
helpviewer_keywords:
- C4373
ms.assetid: 670c0ba3-b7d6-4aed-b207-1cb84da3bcde
ms.openlocfilehash: 5891d4679b74695f187fb50bb24fe941882fdcc7
ms.sourcegitcommit: a930a9b47bd95599265d6ba83bb87e46ae748949
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2020
ms.locfileid: "76518347"
---
# <a name="compiler-warning-level-3-c4373"></a>Compilerwarnung (Stufe 3) C4373

> '*function*': virtual function overrides '*base_function*', previous versions of the compiler did not override when parameters only differed by const/volatile qualifiers

## <a name="remarks"></a>Hinweise

Die Anwendung enthält eine Methode in einer abgeleiteten Klasse, die eine virtuelle Methode in einer Basisklasse überschreibt, und die Parameter in der überschreibenden Methode unterscheiden sich nur durch einen [const](../../cpp/const-cpp.md) - oder [volatile](../../cpp/volatile-cpp.md) -Qualifizierer von den Parametern der virtuellen Methode. Dies bedeutet, dass der Compiler einen Funktionsverweis an die Methode in der Basisklasse oder abgeleiteten Klasse binden muss.

Versions of the compiler prior to Visual Studio 2008 bind the function to the method in the base class, then issue a warning message. Subsequent versions of the compiler ignore the `const` or `volatile` qualifier, bind the function to the method in the derived class, then issue warning **C4373**. Das zuletzt genannte Verhalten entspricht dem C++-Standard.

## <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird die Warnung C4373 generiert: To resolve this issue, you can either make the override use the same CV-qualifiers as the base member function, or if you did not intend to create an override, you can give the function in the derived class a different name.

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

int main()
{
    Derived d;
    Base* p = &d;
    p->f(1);
}
```

```Output
derived
```

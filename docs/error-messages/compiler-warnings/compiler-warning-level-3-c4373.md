---
title: Compilerwarnung (Stufe 3) C4373 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- C4373
dev_langs:
- C++
helpviewer_keywords:
- C4373
ms.assetid: 670c0ba3-b7d6-4aed-b207-1cb84da3bcde
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e1694c8d15ad65b39a27af8ae5aae02e9c729896
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="compiler-warning-level-3-c4373"></a>Compilerwarnung (Stufe 3) C4373

> "*Funktion*": virtuelle Funktion überschreibt*Basisfunktion*", frühere Versionen des Compilers nicht überschrieben, wenn der Parameter nur durch Const/Volatile-Qualifizierer beinhalteten

## <a name="remarks"></a>Hinweise

Die Anwendung enthält eine Methode in einer abgeleiteten Klasse, die eine virtuelle Methode in einer Basisklasse überschreibt, und die Parameter in der überschreibenden Methode unterscheiden sich nur durch einen [const](../../cpp/const-cpp.md) - oder [volatile](../../cpp/volatile-cpp.md) -Qualifizierer von den Parametern der virtuellen Methode. Dies bedeutet, dass der Compiler einen Funktionsverweis an die Methode in der Basisklasse oder abgeleiteten Klasse binden muss.

Compilerversionen vor Visual Studio 2008 binden die Funktion an die Methode in der Basisklasse und geben dann eine Warnmeldung angezeigt. Nachfolgende Versionen des Compilers ignorieren die `const` oder `volatile` Qualifizierer, binden die Funktion an die Methode in der abgeleiteten Klasse und geben Sie die Warnung dann **C4373**. Das zuletzt genannte Verhalten entspricht dem C++-Standard.

## <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird die Warnung C4373 generiert: Um dieses Problem zu beheben, können Sie die Außerkraftsetzung der gleichen CV-Qualifizierer als die Basis-Memberfunktion verwenden herstellen, oder wenn Sie nicht, dass Sie eine Außerkraftsetzung erstellen möchten, Sie erhalten der Funktion in der abgeleiteten Klasse einen anderen Namen.

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
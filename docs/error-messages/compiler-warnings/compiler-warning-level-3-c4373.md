---
title: Compilerwarnung (Stufe 3) C4373 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4373
dev_langs:
- C++
helpviewer_keywords:
- C4373
ms.assetid: 670c0ba3-b7d6-4aed-b207-1cb84da3bcde
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 43523cb5f4c024ec3e937e88fca7f78c341ab19d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4373"></a>Compilerwarnung (Stufe 3) C4373
"%$S": Virtuelle Funktion überschreibt "%$pS". Vorherige Compilerversionen werden nicht überschrieben, wenn sich die Parameter nur durch const/volatile-Qualifizierer unterscheiden.  
  
 Die Anwendung enthält eine Methode in einer abgeleiteten Klasse, die eine virtuelle Methode in einer Basisklasse überschreibt, und die Parameter in der überschreibenden Methode unterscheiden sich nur durch einen [const](../../cpp/const-cpp.md) - oder [volatile](../../cpp/volatile-cpp.md) -Qualifizierer von den Parametern der virtuellen Methode. Dies bedeutet, dass der Compiler einen Funktionsverweis an die Methode in der Basisklasse oder abgeleiteten Klasse binden muss.  
  
 Compilerversionen vor [!INCLUDE[cpp_orcas_long](../../cpp/includes/cpp_orcas_long_md.md)] binden die Funktion an die Methode in der Basisklasse und geben dann eine Warnmeldung aus. Nachfolgende Compilerversionen ignorieren den `const` - oder `volatile` -Qualifizierer, binden die Funktion an die Methode in der abgeleiteten Klasse und geben dann die Warnung `C4373`aus. Das zuletzt genannte Verhalten entspricht dem C++-Standard.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird die Warnung C4373 generiert:  
  
```  
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
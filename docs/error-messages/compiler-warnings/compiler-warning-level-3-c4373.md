---
title: Compilerwarnung (Stufe 3) C4373 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 36d4491f8a621f1ee97de9682faf94a26a89fa70
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-3-c4373"></a>Compilerwarnung (Stufe 3) C4373
"%$S": Virtuelle Funktion überschreibt "%$pS". Vorherige Compilerversionen werden nicht überschrieben, wenn sich die Parameter nur durch const/volatile-Qualifizierer unterscheiden.  
  
 Die Anwendung enthält eine Methode in einer abgeleiteten Klasse, die eine virtuelle Methode in einer Basisklasse überschreibt, und die Parameter in der überschreibenden Methode unterscheiden sich nur durch eine [const](../../cpp/const-cpp.md) oder [volatile](../../cpp/volatile-cpp.md) Qualifizierer von den Parametern der virtuellen Methode. Dies bedeutet, dass der Compiler einen Funktionsverweis an die Methode in der Basisklasse oder abgeleiteten Klasse binden muss.  
  
 Compilerversionen vor [!INCLUDE[cpp_orcas_long](../../cpp/includes/cpp_orcas_long_md.md)] binden die Funktion an die Methode in der Basisklasse aus, und klicken Sie dann eine Warnmeldung ausgeben. Nachfolgende Compilerversionen ignorieren den `const` - oder `volatile` -Qualifizierer, binden die Funktion an die Methode in der abgeleiteten Klasse und geben dann die Warnung `C4373`aus. Das zuletzt genannte Verhalten entspricht dem C++-Standard.  
  
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

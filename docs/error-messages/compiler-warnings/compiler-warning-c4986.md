---
title: Compilerwarnung C4986 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4986
dev_langs:
- C++
helpviewer_keywords:
- C4986
ms.assetid: a3a7b008-29dd-4203-85f3-7740ab6790bb
caps.latest.revision: 4
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 67e4ad3f5170b4f7dc0e938e7b7830dacbde0e26
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-warning-c4986"></a>Compilerwarnung C4986
'Funktion': Ausnahmespezifikation stimmt nicht mit der vorherigen Deklaration überein  
  
 Diese Warnung kann generiert werden, wenn eine Ausnahmespezifikation in einer Deklaration und das andere vorhanden ist.  
  
 Standardmäßig ist C4986 deaktiviert. Weitere Informationen finden Sie unter [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C4986 generiert.  
  
```cpp  
class X { };  
void f1() throw (X*);  
// ...  
void f1()  
{  
    // ...  
}    
```  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird diese Warnung.  
  
```cpp  
class X { };  
void f1() throw (X*);  
// ...  
void f1() throw (X*)  
{  
    // ...  
}    
```

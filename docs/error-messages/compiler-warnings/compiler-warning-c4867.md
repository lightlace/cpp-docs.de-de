---
title: Compilerwarnung C4867 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4867
dev_langs:
- C++
helpviewer_keywords:
- C4867
ms.assetid: 8a257d70-c3a7-462d-b285-e57c952a8bf7
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 352b38744d83b3dc163125ff5ec8d80165f60c9a
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-warning-c4867"></a>Compilerwarnung C4867
'Funktion': Funktionsaufruf fehlt die Argumentliste. Verwenden Sie "Aufruf" So erstellen einen Zeiger auf member  
  
 Ein Zeiger auf eine Memberfunktion wurde nicht ordnungsgemäß initialisiert.  
  
 Diese Warnung kann infolge einer konformitätsverbesserung für Visual C++ 2005 erstellt wurde, die generiert werden: verbesserte Pointer-to-Member-Konformität.  Code, der vor Visual C++ 2005 kompiliert wird nun C4867 generiert.  
  
 Diese Warnmeldung wird immer als Fehler ausgegeben. Verwenden Sie das [warning](../../preprocessor/warning.md) -Pragma, um diese Warnung zu deaktivieren. Weitere Informationen über C4867 und MFC/ATL finden Sie unter [_ATL_ENABLE_PTM_WARNING](../../atl/reference/compiler-options-macros.md#_atl_enable_ptm_warning).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C4867 generiert.  
  
```  
// C4867.cpp  
// compile with: /c  
class A {  
public:  
   void f(int) {}  
  
   typedef void (A::*TAmtd)(int);  
  
   struct B {  
      TAmtd p;  
   };  
  
   void g() {  
      B b = {f};   // C4867  
      B b2 = {&A::f};   // OK  
   }  
};  
```

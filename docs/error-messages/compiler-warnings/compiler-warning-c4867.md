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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a412080d05e570711fcc65926459f9d2fcc45ed3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
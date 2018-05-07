---
title: Compilerwarnung C4867 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4867
dev_langs:
- C++
helpviewer_keywords:
- C4867
ms.assetid: 8a257d70-c3a7-462d-b285-e57c952a8bf7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b46bf4866791ec82ac5984132903e22ab16e07ad
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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
---
title: Compilerwarnung C4484 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4484
dev_langs:
- C++
helpviewer_keywords:
- C4484
ms.assetid: 3d30e5b3-2297-45b7-a37a-1360056fdd0e
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 06246c811c59ff126cd61d5c10d0d30a68857c2c
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-warning-c4484"></a>Compilerwarnung C4484
'Überschreibungsfunktion': Basis Ref-Klassenmethode "Basisklassenfunktion" entspricht, ist jedoch nicht gekennzeichnet "virtual", "new" oder "override"; "new" (und nicht "virtual") wird angenommen.  
  
 Beim Kompilieren mit **"/ CLR"**, wird nicht vom Compiler implizit für eine Basisklasse-Funktion, d. h. die Funktion erhält einen neuen Platz im Vtable überschrieben. Um zu beheben, geben Sie explizit an, ob eine Funktion eine Überschreibung darstellt.  
  
 Weitere Informationen finden Sie unter:  
  
-   [/ CLR (common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [override](../../windows/override-cpp-component-extensions.md)  
  
-   [New (neuer Slot in Vtable)](../../windows/new-new-slot-in-vtable-cpp-component-extensions.md)  
  
 C4484 wird immer als Fehler ausgegeben. Verwenden der [Warnung](../../preprocessor/warning.md) -Pragma, um C4484 zu unterdrücken.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C4484 generiert.  
  
```  
// C4484.cpp  
// compile with: /clr  
ref struct A {  
   virtual void Test() {}  
};  
  
ref struct B : A {  
   void Test() {}   // C4484  
};  
  
// OK  
ref struct C {  
   virtual void Test() {}  
   virtual void Test2() {}  
};  
  
ref struct D : C {  
   virtual void Test() new {}  
   virtual void Test2() override {}  
};  
```

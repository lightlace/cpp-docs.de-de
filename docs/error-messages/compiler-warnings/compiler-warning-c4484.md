---
title: "Compilerwarnung C4484"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C4484"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4484"
ms.assetid: 3d30e5b3-2297-45b7-a37a-1360056fdd0e
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung C4484
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Überschreibungsfunktion': Stimmt mit der 'Basisklassenfunktion'\-Basismethode der Verweisklasse überein, ist jedoch nicht als 'new' oder 'override' markiert; 'new' \(und 'virtual'\) wird angenommen.  
  
 Beim Kompilieren mit **\/clr** wird die Basisklassenfunktion nicht implizit vom Compiler überschrieben. Dies hat zur Folge, dass der Funktion in der Vtable ein neuer Slot zugewiesen wird.  Um das Problem zu beheben, geben Sie explizit an, ob es sich bei einer Funktion um eine Überschreibungsfunktion handelt.  
  
 Weitere Informationen finden Sie unter:  
  
-   [\/clr \(Common Language Runtime\-Kompilierung\)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [override](../../windows/override-cpp-component-extensions.md)  
  
-   [new \(new slot in vtable\)](../../windows/new-new-slot-in-vtable-cpp-component-extensions.md)  
  
 C4484 wird immer als Fehler ausgegeben.  Verwenden Sie das [warning](../../preprocessor/warning.md)\-Pragma, um C4484 zu unterdrücken.  
  
## Beispiel  
 Im folgenden Beispiel wird C4484 generiert.  
  
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
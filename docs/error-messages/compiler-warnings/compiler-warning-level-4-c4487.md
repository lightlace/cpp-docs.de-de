---
title: "Compilerwarnung (Stufe 4) C4487 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4487"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4487"
ms.assetid: 796144cf-cd3c-4edc-b6a4-96192b7eb4f0
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# Compilerwarnung (Stufe 4) C4487
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Abgeleitete\_Klassenfunktion': Stimmt mit geerbter nicht virtueller Methode 'Basisklassenfunktion' überein, ist jedoch nicht explizit mit 'new' markiert  
  
 Eine Funktion in einer abgeleiteten Klasse verfügt über die gleiche Signatur wie eine nicht virtuelle Basisklassenfunktion.  C4487 dient als Warnung, dass die Basisklassenfunktion von der abgeleiteten Klassenfunktion nicht überschrieben wird.  Markieren Sie die abgeleitete Klassenfunktion explizit als `new`, um diese Warnung aufzulösen.  
  
 Weitere Informationen finden Sie unter [new \(new slot in vtable\)](../../windows/new-new-slot-in-vtable-cpp-component-extensions.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C4487 generiert.  
  
```  
// C4487.cpp  
// compile with: /W4 /clr  
using namespace System;  
public ref struct B {  
   void f() { Console::WriteLine("in B::f"); }  
   void g() { Console::WriteLine("in B::g"); }  
};  
  
public ref struct D : B {  
   void f() { Console::WriteLine("in D::f"); }   // C4487  
   void g() new { Console::WriteLine("in D::g"); }   // OK  
};  
  
int main() {  
   B ^ a = gcnew D;  
   // will call base class functions  
   a->f();  
   a->g();  
}  
```
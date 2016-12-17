---
title: "Compilerfehler C3351"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "C3351"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3351"
ms.assetid: c021bbbe-1067-4f51-af4f-940d2b792eb5
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3351
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Object': Delegatkonstruktor: Das zweite Argument muss eine Adresse einer statischen Memberfunktion oder einer globalen Funktion sein.  
  
 Der Compiler hat die Adresse einer Funktion erwartet, die als [static](../../misc/static-cpp.md) deklariert ist.  
  
 Im folgenden Beispiel wird C3351 generiert:  
  
```  
// C3351a.cpp // compile with: /clr delegate int D(int, int); ref class C { public: int mf(int, int) { return 1; } static int mf2(int, int) { return 1; } }; int main() { System::Delegate ^pD = gcnew D(nullptr, &C::mf);   // C3351 System::Delegate ^pD2 = gcnew D(&C::mf2); }  
```  
  
 Im folgenden Beispiel wird C3351 generiert:  
  
```  
// C3351b.cpp // compile with: /clr:oldSyntax #using <mscorlib.dll> __delegate int D(int, int); __gc class C { public: int mf(int, int) { // declare the function as static // static int mf(int, int) { return 1; } }; int main() { C *pC = new C; System::Delegate *pD = new D(0, &C::mf);   // C3351 }  
```
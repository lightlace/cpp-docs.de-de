---
title: "Compilerfehler C2691 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2691"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2691"
ms.assetid: 6925f8f3-ea60-4909-91e6-b781492c645d
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Compilerfehler C2691
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

„Datentyp“: Ein verwaltetes oder WinRT\-Array darf nicht diesen Elementtyp aufweisen.  
  
 Der Typ eines verwalteten oder WinRT\-Arrayelements kann ein Werttyp oder Verweistyp sein.  
  
 Im folgenden Beispiel wird C2691 generiert:  
  
```  
// C2691a.cpp  
// compile with: /clr  
class A {};  
  
int main() {  
   array<A>^ a1 = gcnew array<A>(20);   // C2691  
   array<int>^ a2 = gcnew array<int>(20);   // value type OK  
}  
```  
  
 Im folgenden Beispiel wird C2691 generiert:  
  
```  
// C2691b.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
int main() {  
   int * a1 __gc[];   // C2691  
   int * a1 = new int [20];   // OK  
}  
```  
  
 C2691 kann auch beim Versuch auftreten, ein verzweigtes Array mit Managed Extensions for C\+\+ zu definieren.  Verzweigte Arrays werden in der aktuellen Syntax unterstützt. Weitere Informationen hierzu finden Sie unter [Arrays](../../windows/arrays-cpp-component-extensions.md).  
  
 Im folgenden Beispiel wird C2691 generiert:  
  
```  
// C2691c.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
using namespace System;  
int main() {  
   Int32 myJaggedArray[][] = new Int32 [50][];   // C2691  
}  
```
---
title: "Compilerfehler C2107"
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
  - "C2107"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2107"
ms.assetid: 2866a121-884e-4bb5-8613-36de5817000e
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2107
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ungültiger Index, Zeigeroperation nicht erlaubt  
  
 Die Indexschreibweise wurde für einen Ausdruck verwendet, dessen Ergebnis kein Zeiger ist.  
  
## Beispiel  
 C2107 kann auftreten, wenn Sie den `this`\-Zeiger eines Werttyps falsch verwenden, um auf den Standardindexer des Typs zuzugreifen.  Weitere Informationen finden Sie unter [Semantik dieses Zeigers](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Semantics_of_the_this_pointer).  
  
 Im folgenden Beispiel wird C2107 generiert.  
  
```  
// C2107.cpp  
// compile with: /clr  
using namespace System;  
  
value struct B {  
   property String ^ default[String ^] {  
      String ^ get(String ^ data) {  
         return "abc";  
      }  
   }  
   void Test() {  
      Console::WriteLine("{0}", this["aa"]);   // C2107  
      Console::WriteLine("{0}", this->default["aa"]);   // OK  
   }  
};  
  
int main() {  
   B ^ myb = gcnew B();  
   myb->Test();  
}  
```
---
title: "Compilerfehler C3821"
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
  - "C3821"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3821"
ms.assetid: 2b327c7a-5faf-443c-ae82-944fae25b4df
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3821
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion': Ein verwalteter Typ oder eine verwaltete Funktion kann nicht in einer nicht verwalteten Funktion verwendet werden  
  
 Funktionen mit Inlineassembly oder [setjmp](../../c-runtime-library/reference/setjmp.md) können keine Werttypen oder verwaltete Klassen enthalten.  Um den Fehler zu beheben, entfernen Sie entweder die Inlineassembly und `setjmp` oder die verwalteten Objekte.  
  
 C3821 kann auch auftreten, wenn Sie versuchen, in einer vararg\-Funktion die automatische Speicherung zu verwenden.  Weitere Informationen finden Sie unter [Variable Argument Lists \(...\) \(C\+\+\/CLI\)](../../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md) und [C\+\+\-Stack\-Semantik für Referenztypen](../../dotnet/cpp-stack-semantics-for-reference-types.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C3821 generiert.  
  
```  
// C3821a.cpp  
// compile with: /clr /c  
public ref struct R {};  
void test1(...) {  
   R r;   // C3821  
}  
```  
  
## Beispiel  
 Im folgenden Beispiel wird C3821 generiert.  
  
```  
// C3821b.cpp  
// compile with: /clr  
// processor: /x86  
ref class A {  
   public:  
   int i;  
};  
  
int main() {  
   // cannot use managed classes in this function  
   A ^a;     
  
   __asm {  
      nop  
   }  
} // C3821  
```  
  
## Beispiel  
 Im folgenden Beispiel wird C3821 generiert.  
  
```  
// C3821c.cpp  
// compile with: /clr:oldSyntax  
// processor: /x86  
__gc  class A {  
   public:  
   int i;  
};  
  
int main() {  
   // cannot use managed classes in this function  
   A *a;     
  
   __asm {  
      nop  
   }  
} // C3821  
```
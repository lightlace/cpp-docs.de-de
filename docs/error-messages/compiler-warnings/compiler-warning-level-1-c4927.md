---
title: "Compilerwarnung (Stufe 1) C4927"
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
  - "C4927"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4927"
ms.assetid: 7009e740-a2ef-4130-96ba-482e092f717a
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4927
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Unzulässige Konvertierung. Es wurden mehrere benutzerdefinierte Konvertierungen implizit übernommen.  
  
 Für einen einzelnen Wert wurden mehrere benutzerdefinierte Konvertierungen implizit übernommen. Vom Compiler wurde keine explizite, sondern eine andere Konvertierung gefunden und verwendet.  
  
 Im folgenden Beispiel wird C4927 generiert:  
  
```  
// C4927.cpp  
// compile with: /W1  
struct B  
{  
   operator int ()  
   {  
      return 0;  
   }  
};  
  
struct A  
{  
   A(int i)  
   {  
   }  
  
   /*  
   // uncomment this constructor to resolve  
   A(B b)  
   {  
   }  
   */  
};  
  
A f1( B& b)  
{  
   return A(b);  
}  
  
B& f2( B& b)  
{  
   return b;  
}  
  
A f()  
{  
   B b;  
   return A(b);   // ok  
   return f1(b);  // ok  
   return b;      // C4927  
   return B(b);   // C4927  
   return f2(b);  // C4927  
}  
  
int main()  
{  
   B b;  
   A a = b;  
   A a2(b);  
}  
```
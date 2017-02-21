---
title: "Compilerfehler C3379 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3379"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3379"
ms.assetid: a66c2c4e-091c-4426-9cde-7c4cfb2ffce1
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Compilerfehler C3379
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Klasse': Eine geschachtelte Klasse kann keinen Assemblyzugriffsspezifizierer als Teil ihrer Deklaration haben  
  
 Wenn die Schlüsselwörter [public](../../cpp/public-cpp.md) und [private](../../cpp/private-cpp.md) auf einen verwalteten Typ angewendet werden, zeigen sie an, ob die Klasse über Assemblymetadaten verfügbar gemacht wird.  `public` oder `private` können nicht auf geschachtelte Klassen angewendet werden, die den Assemblyzugriff von der übergeordneten Klasse erben.  
  
 In Kombination mit [\/clr](../../build/reference/clr-common-language-runtime-compilation.md) zeigen die Schlüsselwörter `ref` und `value` an, dass es sich um eine verwaltete Klasse handelt \(siehe [Classes and Structs](../../windows/classes-and-structs-cpp-component-extensions.md)\).  
  
 Im folgenden Beispiel wird C3379 generiert:  
  
```  
// C3379a.cpp  
// compile with: /clr  
using namespace System;  
  
public ref class A {  
public:  
   static int i = 9;  
  
   public ref class BA {   // C3379  
   // try the following line instead  
   // ref class BA {  
   public:  
      static int ii = 8;  
   };  
};  
  
int main() {  
  
   A^ myA = gcnew A;  
   Console::WriteLine(myA->i);  
  
   A::BA^ myBA = gcnew A::BA;  
   Console::WriteLine(myBA->ii);  
}  
```  
  
 Im folgenden Beispiel wird C3379 generiert:  
  
```  
// C3379b.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
  
public __gc class A {  
public:  
   static int i = 9;  
  
   public __gc class BA {   // C3379  
   // try the following line instead  
   // __gc class BA {  
   public:  
      static int ii = 8;  
   };  
};  
  
int main() {  
  
   A *myA = new A;  
   Console::WriteLine(myA->i);  
  
   A::BA *myBA = new A::BA;  
   Console::WriteLine(myBA->ii);  
}  
```
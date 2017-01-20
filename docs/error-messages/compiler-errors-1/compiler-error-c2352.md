---
title: "Compilerfehler C2352"
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
  - "C2352"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2352"
ms.assetid: 0efad8cb-659f-4b3e-8f6f-9f8ec44d345c
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2352
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class::function': Unzulässiger Aufruf einer nicht statischen Memberfunktion  
  
 Eine als nicht statische Memberfunktion bezeichnete `static`Memberfunktion.  Oder es wurde eine nicht statische Memberfunktion von außerhalb der Klasse als eine statische Funktion aufgerufen.  
  
 Im folgenden Beispiel wird C2352 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C2352.cpp  
// compile with: /c  
class CMyClass {  
public:  
   static void func1();  
   void func2();  
   static void func3() {  
      func2();   // C2352 calls nonstatic func2  
      func1();   // OK calls static func1  
   }  
};  
```  
  
 Im folgenden Beispiel wird C2352 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C2352b.cpp  
class MyClass {  
public:  
   void MyFunc() {}  
   static void MyFunc2() {}  
};  
  
int main() {  
   MyClass::MyFunc();   // C2352  
   MyClass::MyFunc2();   // OK  
}  
```
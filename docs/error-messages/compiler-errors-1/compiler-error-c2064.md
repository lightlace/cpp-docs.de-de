---
title: "Compilerfehler C2064"
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
  - "C2064"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2064"
ms.assetid: 6cda05da-f437-4f50-9813-ae69538713a3
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2064
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ausdruck ergibt keine Funktion, die N Argumente übernimmt  
  
 Eine Funktion wird durch einen Ausdruck aufgerufen.  Der Ausdruck wird nicht als Zeiger auf eine Funktion ausgewertet, die die angegebene Anzahl von Argumenten akzeptiert.  
  
 In diesem Beispiel wird mit dem Code versucht, Nichtfunktionen als Funktionen aufzurufen.  Im folgenden Beispiel wird C2064 generiert:  
  
```  
// C2064.cpp  
int i, j;  
char* p;  
void func() {  
   j = i();    // C2064, i is not a function  
   p();        // C2064, p doesn't point to a function  
}  
```  
  
 Sie müssen Zeiger auf nicht statische Memberfunktionen aus dem Kontext einer Objektinstanz aufrufen.  Im folgenden Beispiel wird C2064 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C2064b.cpp  
struct C {  
   void func1(){}  
   void func2(){}  
};  
  
typedef void (C::*pFunc)();  
  
int main() {  
   C c;  
   pFunc funcArray[2] = {&C::func1, &C::func2};  
   (funcArray[0])();    // C2064   
   (c.*funcArray[0])(); // OK - function called in instance context  
}  
  
```  
  
 Memberfunktionszeiger müssen innerhalb einer Klasse den aufrufenden Objektkontext angeben.  Im folgenden Beispiel wird C2064 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C2064d.cpp  
// Compile by using: cl /c /W4 C2064d.cpp  
struct C {  
   typedef void (C::*pFunc)();  
   pFunc funcArray[2];  
   void func1(){}  
   void func2(){}  
   C() {  
      funcArray[0] = &C::func1;  
      funcArray[1] = &C::func2;  
   }  
   void func3() {  
      (funcArray[0])();   // C2064  
      (this->*funcArray[0])(); // OK - called in this instance context  
   }  
};  
```
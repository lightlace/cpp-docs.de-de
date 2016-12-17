---
title: "Compilerfehler C3731"
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
  - "C3731"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3731"
ms.assetid: 45f89fcd-464c-4bc8-8a42-edcb5416d26c
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3731
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Inkompatibles Ereignis 'Funktion1' und Handler 'Funktion2'; Ereignisquelle und Ereignishandler müssen vom selben Typ sein  
  
 Die Ereignisquelle und der Ereignisempfänger müssen vom selben Typ \(beispielsweise `native` für Typen `com` \).  Um diesen Fehler zu beheben, passen Sie die Typen von Ereignisquelle und Ereignishandler an.  
  
 Im folgenden Beispiel wird C3731 generiert:  
  
```  
// C3731.cpp  
// compile with: /clr  
#using <mscorlib.dll>  
[event_source(native)]  
struct A {  
   __event void MyEvent();  
};  
  
[event_receiver(managed)]  
// try the following line instead  
// [event_receiver(native)]  
struct B {  
   void func();  
   B(A a) {  
      __hook(&A::MyEvent, &a, &B::func);   // C3731  
   }  
};  
  
int main() {  
}  
```
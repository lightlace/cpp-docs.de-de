---
title: "Compilerfehler C2027 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2027"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2027"
ms.assetid: a39150c0-ec04-45ec-934c-a838bfe76627
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C2027
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Verwendung des undefinierten Typs 'Typ'  
  
 Typen können erst verwendet werden, nachdem sie definiert wurden.  Um den Fehler zu beheben, stellen Sie sicher, dass der Typ vollständig definiert ist, bevor Sie einen Verweis darauf erstellen.  
  
## Beispiel  
 Im folgenden Beispiel wird C2027 generiert.  
  
```  
// C2027.cpp  
class C;  
class D {  
public:  
   void func() {  
   }  
};  
  
int main() {  
   C *pC;  
   pC->func();   // C2027  
  
   D *pD;  
   pD->func();  
}  
```  
  
## Beispiel  
 Es ist möglich, einen Zeiger auf einen deklarierten, jedoch nicht definierten Typ zu deklarieren.  In Visual C\+\+ ist jedoch keinen Verweis auf einen nicht definierten Typ zulässig.  
  
 Im folgenden Beispiel wird C2027 generiert.  
  
```  
// C2027_b.cpp  
class A;  
A& CreateA();  
  
class B;  
B* CreateB();  
  
int main() {  
   CreateA();   // C2027  
   CreateB();   // OK  
}  
```
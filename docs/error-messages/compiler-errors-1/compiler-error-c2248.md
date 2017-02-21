---
title: "Compilerfehler C2248 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2248"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2248"
ms.assetid: 7a3ba0e8-d3b9-4bb9-95db-81ef17e31d23
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# Compilerfehler C2248
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Member': Kein Zugriff auf 'Zugriff' 'Member', dessen Deklaration in der 'Klasse'\-Klasse erfolgte  
  
 Member einer abgeleiteten Klasse können nicht auf `private`\-Member einer Basisklasse zugreifen.  Sie können auf keine `private`\-Member oder `protected`\-Member von Klasseninstanzen zugreifen.  
  
 Weitere Informationen zu C2248 finden Sie im Knowledge Base\-Artikel KB243351 \(nur auf Englisch verfügbar\).  
  
 Im folgenden Beispiel wird C2248 generiert:  
  
```  
// C2248.cpp  
#include <stdio.h>  
class X {  
public:  
   int  m_pubMemb;  
   void setPrivMemb( int i ) {  
      m_privMemb = i;  
      printf_s("\n%d", m_privMemb);  
   }  
protected:  
   int  m_protMemb;  
  
private:  
   int  m_privMemb;  
} x;  
  
int main() {  
   x.m_pubMemb = 4;  
   printf_s("\n%d", x.m_pubMemb);  
   x.m_protMemb = 2;   // C2248 m_protMemb is protected  
   x.m_privMemb = 3;   // C2248  m_privMemb is private  
   x.setPrivMemb(0);   // OK uses public access function  
}  
```  
  
 Ein anderes Konformitätsproblem, bei dem C2248 auftreten kann, entsteht bei der Verwendung von Friend\-Vorlagen und Spezialisierung.  Weitere Informationen finden Sie unter [Linkertoolfehler LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md).  
  
```  
// C2248_b.cpp  
template<class T>  
void f(T t) {  
   t.i;   // C2248  
}  
  
struct S {  
private:  
   int i;  
  
public:  
   S() {}  
   // Delete the following line to resolve.  
   friend void f(S);   // refer to the non-template function void f(S)  
  
   // Uncomment the following line to resolve.  
   // friend void f<S>(S);  
};  
  
int main() {  
   S s;  
   f<S>(s);  
}  
```  
  
 Ein weiteres Konformitätsproblem, bei dem C2248 auftritt, entsteht beim Versuch, den Friend einer Klasse zu deklarieren, die für die Friend\-Deklaration im Gültigkeitsbereich der Klasse nicht sichtbar ist.  Gewähren Sie in diesem Fall der übergeordneten Klasse einen Friend\-Status, um den Fehler zu beheben.  
  
```  
// C2248_c.cpp  
// compile with: /c  
class T {  
   class S {  
      class E {};  
   };  
   friend class S::E;   // C2248  
};  
  
class A {  
   class S {  
      class E {};  
      friend class A;   // grant friendship to enclosing class  
   };  
   friend class S::E;   // OK  
};  
```
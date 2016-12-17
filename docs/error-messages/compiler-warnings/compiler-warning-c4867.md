---
title: "Compilerwarnung C4867"
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
  - "C4867"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4867"
ms.assetid: 8a257d70-c3a7-462d-b285-e57c952a8bf7
caps.latest.revision: 16
caps.handback.revision: "16"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung C4867
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion': Dem Funktionsaufruf fehlt die Argumentliste. Verwenden Sie 'Aufruf', um einen Zeiger auf den Member zu erstellen  
  
 Ein Zeiger auf eine Memberfunktion wurde falsch initialisiert.  
  
 Diese Warnmeldung kann infolge einer Verbesserung der Compilerkonformität für Visual C\+\+ 2005 ausgegeben werden: Verbesserte pointer\-to\-member\-Konformität.  Code, der mit einer früheren Version als Visual C\+\+ 2005 kompiliert wird, führt zur Warnmeldung C4867.  
  
 Diese Warnmeldung wird immer als Fehler ausgegeben.  Verwenden Sie das [warning](../../preprocessor/warning.md)\-Pragma, um diese Warnung zu deaktivieren.  Weitere Informationen über C4867 und MFC\/ATL finden Sie unter [\_ATL\_ENABLE\_PTM\_WARNING](../Topic/_ATL_ENABLE_PTM_WARNING.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C4867 generiert.  
  
```  
// C4867.cpp  
// compile with: /c  
class A {  
public:  
   void f(int) {}  
  
   typedef void (A::*TAmtd)(int);  
  
   struct B {  
      TAmtd p;  
   };  
  
   void g() {  
      B b = {f};   // C4867  
      B b2 = {&A::f};   // OK  
   }  
};  
```
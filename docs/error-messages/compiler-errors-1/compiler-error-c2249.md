---
title: "Compilerfehler C2249"
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
  - "C2249"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2249"
ms.assetid: bdd6697c-e04b-49b9-8e40-d9eb6d74f2b6
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2249
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Member' : Kein Zugriff auf den Pfad für den Member, dessen Deklaration in der virtuellen Basisklasse 'Klasse' erfolgte  
  
 Der `member` wurde von einer nicht öffentlichen `virtual`\-Basisklasse oder \-Struktur geerbt.  
  
## Beispiel  
 Im folgenden Beispiel wird C2249 generiert.  
  
```  
// C2249.cpp  
class A {  
private:  
   void privFunc( void ) {};  
public:  
   void pubFunc( void ) {};  
};  
  
class B : virtual public A {} b;  
  
int main() {  
   b.privFunc();    // C2249, private member of A  
   b.pubFunc();    // OK  
}  
```  
  
## Beispiel  
 C2249 kann auch auftreten, wenn Sie versuchen, einen Stream aus der C\+\+\-Standardbibliothek einem anderen Stream zuzuweisen.  Im folgenden Beispiel wird C2249 generiert.  
  
```  
// C2249_2.cpp  
#include <iostream>  
using namespace std;  
int main() {  
   cout = cerr;   // C2249  
   #define cout cerr;   // OK  
}  
```
---
title: "Compilerwarnung (Stufe 2) C4244"
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
  - "C4244"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4244"
ms.assetid: 2c19d157-21d1-42c2-a6c0-3f30f2ce3813
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 2) C4244
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Argument': Umwandlung von 'Typ1' in 'Typ2', Datenverlust ist möglich  
  
 Ein Gleitkommatyp wurde in einen ganzzahligen Typ konvertiert.  Möglicherweise ist ein Datenverlust aufgetreten.  
  
 Wenn C4244 angezeigt wird, sollten Sie das Programm für die Verwendung kompatibler Typen ändern oder mehr Logik in den Code bringen, um sicherzustellen, dass der Bereich möglicher Werte immer mit den verwendeten Typen kompatibel ist.  
  
 C4244 kann auch auf Ebene 3 und 4 ausgelöst werden. Weitere Informationen finden Sie unter [Compilerwarnung \(Stufes 3 and 4\) C4244](../../error-messages/compiler-warnings/compiler-warning-levels-3-and-4-c4244.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C4244 generiert:  
  
```  
// C4244_level2.cpp  
// compile with: /W2  
  
int f(int x){ return 0; }  
int main() {  
   double x = 10.1;  
   int i = 10;  
   return (f(x));   // C4244  
   // try the following line instead  
   // return (f(i));  
}  
```
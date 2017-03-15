---
title: "Compilerfehler C2589 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2589"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2589"
ms.assetid: 1d7942c7-8a81-4bb4-b272-76a0019e8513
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C2589
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner': Ungültiges Symbol auf der rechten Seite von '::'  
  
 Wenn der Name einer Klasse, Struktur oder Union auf der linken Seite des Bereichsauflösungsoperators \(zwei Doppelpunkte\) steht, muss das Token auf der rechten Seite ein Klassen\-, Struktur\- oder Unionmember sein.  Ansonsten kann jeder globale Bezeichner auf der rechten Seite stehen.  
  
 Der Bereichsauflösungsoperator kann nicht überladen werden.  
  
 Im folgenden Beispiel wird C2589 generiert:  
  
```  
// C2589.cpp  
void Test(){}  
class A {};  
void operator :: ();   // C2589  
  
int main() {  
   ::Test();  
}  
```
---
title: "Compilerfehler C2600"
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
  - "C2600"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2600"
ms.assetid: cce11943-ea01-4bee-a7b0-b67d24ec6493
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2600
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion': kann keine vom Compiler generierte spezielle Memberfunktion definieren \(Deklaration in der ersten Klasse erforderlich\)  
  
 Bevor Sie Member\-Funktionen wie Konstruktoren oder Destruktoren für eine Klasse definieren können, müssen sie in der Klasse deklariert werden.  Der Compiler kann standardmäßige Konstruktoren und Destruktoren \(speziellen Memberfunktionen genannt\) generieren, wenn keine in der Klasse deklariert werden.  Wenn Sie eine dieser Funktionen ohne eine entsprechende Deklaration in der Klasse definieren, erkennt der Compiler jedoch einen Konflikt.  
  
 Beheben Sie diesen Fehler, indem Sie in der Klassendeklaration jede Member\-Funktion, die Sie außerhalb der Klassendeklaration definieren, deklarieren.  
  
 Im folgenden Beispiel wird C2600 generiert:  
  
```  
// C2600.cpp  
// compile with: /c  
class C {};  
C::~C() {}   // C2600  
  
class D {  
   D::~D();  
};  
  
D::~D() {}  
```
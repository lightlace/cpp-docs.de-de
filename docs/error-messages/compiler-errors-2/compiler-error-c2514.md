---
title: "Compilerfehler C2514 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2514"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2514"
ms.assetid: 4b7085e5-6714-4261-80b7-bc72e64ab3e8
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C2514
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Klasse': Klasse besitzt keine Konstruktoren  
  
 Für die Klasse, Struktur oder Union ist kein Konstruktor mit einer Liste von Parametern vorhanden, die den Parametern zur Instanziierung der Klasse, Struktur oder Union entsprechen.  
  
 Eine Klasse muss vollständig deklariert werden, damit sie instanziiert werden kann.  
  
 Im folgenden Beispiel wird C2514 generiert:  
  
```  
// C2514.cpp  
// compile with: /c  
class f;  
  
class g {  
public:  
    g (int x);  
};  
  
class fmaker {  
   f *func1() {  
      return new f(2);   // C2514  
   }  
  
   g *func2() {  
      return new g(2);   // OK  
   }  
};   
```
---
title: "Compilerfehler C2571 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2571"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2571"
ms.assetid: c6522616-dee9-4d7d-9bf8-30a7e1deaadf
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C2571
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion': Virtuelle Funktion kann nicht in Union 'Union' sein  
  
 Eine Union wurde mit einer virtuellen Funktion deklariert.  Sie können eine virtuelle Funktion nur in einer Klasse oder Struktur deklarieren.  Mögliche Lösungen:  
  
1.  Ändern Sie die Union in eine Klasse oder Struktur.  
  
2.  Wandeln Sie die Funktion in eine nicht virtuelle Funktion um.  
  
 Im folgenden Beispiel wird C2571 generiert:  
  
```  
// C2571.cpp  
// compile with: /c  
union A {  
   virtual void func1();   // C2571  
   void func2();   // OK  
};  
```
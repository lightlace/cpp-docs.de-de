---
title: "Compilerfehler C2733 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2733"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2733"
ms.assetid: 67f83561-c633-407c-a2ee-f9fd16e165bf
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerfehler C2733
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Zweite C\-Bindung für überladene Funktion 'Funktion' nicht zulässig  
  
 Sie haben mehr als eine überladene Funktion mit C\-Bindung deklariert.  Bei dieser Art von Bindung kann nur eine Variante einer angegebenen Funktion extern sein.  Da überladene Funktionen denselben nicht ergänzten Namen haben, können sie nicht mit C\-Programmen verwendet werden.  
  
 Im folgenden Beispiel wird C2733 generiert:  
  
```  
// C2733.cpp  
extern "C" {  
   void F1(int);  
}  
  
extern "C" {  
   void F1();   // C2733  
   // try the following line instead  
   // void F2();  
}  
```
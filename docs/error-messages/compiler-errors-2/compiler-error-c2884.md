---
title: "Compilerfehler C2884"
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
  - "C2884"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2884"
ms.assetid: 8b4d43e3-3fb5-4360-86c8-de59d8736d4f
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2884
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Name': Wurde durch using\-Deklaration definiert und steht in Konflikt mit lokaler Funktion 'Funktion'  
  
 Sie haben versucht, eine Funktion mehr als einmal zu definieren.  Die erste Definition ist eine lokale Definition.  Die zweite wurde auf der Grundlage eines Namespaces mit einer `using`\-Deklaration erstellt.  
  
 Im folgenden Beispiel wird C2884 generiert:  
  
```  
// C2884.cpp  
namespace A {  
   void z(int);  
}  
  
void f() {  
   void z(int);  
   using A::z;   // C2884 z is already defined  
}  
```
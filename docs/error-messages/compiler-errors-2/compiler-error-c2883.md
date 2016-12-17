---
title: "Compilerfehler C2883"
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
  - "C2883"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2883"
ms.assetid: 5c6d689d-ed42-41ad-b5c0-e9c2e0b8c356
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2883
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Name': Funktionsdeklaration steht in Konflikt mit 'Bezeichner', der durch eine using\-Deklaration eingeführt wurde  
  
 Sie haben versucht, eine Funktion mehr als einmal zu definieren.  Die erste Definition wurde auf der Grundlage eines Namespaces mit einer `using`\-Deklaration erstellt.  Die zweite war eine lokale Definition.  
  
 Im folgenden Beispiel wird C2883 generiert:  
  
```  
// C2883.cpp  
namespace A {  
   void z(int);  
}  
  
int main() {  
   using A::z;  
   void z(int);   // C2883  z is already defined  
}  
```
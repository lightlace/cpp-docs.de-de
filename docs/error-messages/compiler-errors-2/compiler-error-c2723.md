---
title: "Compilerfehler C2723"
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
  - "C2723"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2723"
ms.assetid: 86925601-2297-4cfd-94e2-2caf27c474c4
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2723
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

„Funktion“: Spezifizierer „Spezifizierer“ ist in Funktionsdefinition unzulässig.  
  
 Der Spezifizierer darf nicht mit einer Funktionsdefinition außerhalb einer Klassendeklaration vorkommen.  Der `virtual`\-Spezifizierer kann nur in einer Deklaration einer Memberfunktion innerhalb einer Klassendeklaration angegeben werden.  
  
 Im folgenden Beispiel wird C2723 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C2723.cpp  
struct X {  
   virtual void f();  
   virtual void g();  
};  
  
virtual void X::f() {}   // C2723  
  
// try the following line instead  
void X::g() {}  
```
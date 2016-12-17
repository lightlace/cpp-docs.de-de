---
title: "Compilerfehler C3222"
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
  - "C3222"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3222"
ms.assetid: 5624bde8-2fd0-4b8b-92ce-5dfbaf91cf93
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3222
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Parameter': Für Memberfunktionen eines verwalteten oder WinRT\-Typs oder generische Funktionen können keine Standardargumente deklariert werden.  
  
 Es ist nicht zulässig, einen Methodenparameter mit einem Standardargument zu deklarieren.  Eine überladene Form der Methode ist eine Möglichkeit, dieses Problem zu umgehen.  Das heißt, dass Sie eine Methode mit demselben Namen ohne Parameter definieren und anschließend die Variable im Methodentext initialisieren.  
  
 Im folgenden Beispiel wird C3222 generiert:  
  
```  
// C3222_2.cpp  
// compile with: /clr  
public ref class G {  
   void f( int n = 0 );   // C3222  
};  
```  
  
 Im folgenden Beispiel wird C3222 generiert:  
  
```  
// C3222.cpp  
// compile with: /clr:oldSyntax  
public __gc class G {  
   void f( int n = 0 );   // C3222  
};  
```
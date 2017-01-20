---
title: "Compilerfehler C3366"
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
  - "C3366"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3366"
ms.assetid: efc55bcf-c16d-43c1-a36f-87a6165fa2a8
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3366
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"variable": Statische Datenmember von verwalteten oder WinRT\-Typen müssen innerhalb der Klassendefinition definiert werden.  
  
 Sie haben versucht, auf einen statischen Member einer WinRT\- oder .NET\-Klasse oder \-Schnittstelle außerhalb der Definition der Klasse oder Schnittstelle zu verweisen.  
  
 Der Compiler muss die vollständige Definition der Klasse kennen \(um Metadaten nach einer Übergabe auszugeben\) und erfordert statische Datenmember für die Initialisierung innerhalb der Klasse.  
  
 Beispielsweise generiert das folgende Beispiel C3366 und zeigt, wie Sie den Fehler beheben:  
  
```  
// C3366.cpp  
// compile with: /clr /c  
ref class X {  
   public:  
   static int i;   // initialize i here to avoid C3366  
};  
  
int X::i = 5;      // C3366  
```  
  
 Das folgende Beispiel generiert C3366 und zeigt, wie Sie den Fehler beheben:  
  
```  
// C3366_b.cpp  
// compile with: /clr:oldSyntax /c  
__gc struct X {  
   static int i;   // initialize i here to avoid C3366  
};  
  
int X::i = 5;      // C3366  
```
---
title: "Compilerfehler C2477 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2477"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2477"
ms.assetid: 60bc324b-6605-4833-8099-a291efc712e7
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C2477
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Member': Statischer Datenmember darf nicht über eine abgeleitete Klasse initialisiert werden  
  
 Ein statischer Datenmember einer Vorlagenklasse wurde falsch initialisiert.  Dies ist eine wichtige Änderung gegenüber den Visual C\+\+\-Compilerversionen vor Visual Studio .NET 2003, die zwecks Konformität mit dem C\+\+ ISO\-Standard eingeführt wurde.  
  
 Im folgenden Beispiel wird C2477 generiert:  
  
```  
// C2477.cpp  
// compile with: /Za /c  
template <class T>  
struct S {  
   static int n;  
};  
  
struct X {};  
struct A: S<X> {};  
  
int A::n = 0;   // C2477  
  
template<>  
int S<X>::n = 0;  
```
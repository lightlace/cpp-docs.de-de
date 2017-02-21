---
title: "Compilerfehler C2990 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2990"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2990"
ms.assetid: 674e9f6a-6743-4af0-a7ed-cbe11103a2f8
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# Compilerfehler C2990
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Klasse': Nicht\-Klassentyp wurde bereits als Klassentyp deklariert  
  
 In einer Klasse, die nicht generisch und keine Vorlagenklasse ist, wird eine generische oder Vorlagenklasse neu definiert.  Prüfen Sie die Headerdateien auf Konflikte.  
  
 Im folgenden Beispiel wird C2990 generiert:  
  
```  
// C2990.cpp  
// compile with: /c  
template <class T>  
class C{};  
class C{};   // C2990  
```  
  
 C2990 kann auch auftreten, wenn Generika verwendet werden:  
  
```  
// C2990b.cpp  
// compile with: /clr /c  
generic <class T>  
ref struct GC;  
  
ref struct GC {};   // C2990  
```  
  
 C2990 kann auch aufgrund einer unterbrechenden Änderung im Visual C\+\+\-Compiler für Visual C\+\+ 2005 auftreten. Der Compiler erfordert jetzt, dass mehrere Deklarationen desselben Typs hinsichtlich der Vorlagenspezifikation identisch sind.  
  
 Im folgenden Beispiel wird C2990 generiert:  
  
```  
// C2990c.cpp  
// compile with: /c  
template<class T>  
class A;  
  
template<class T>  
struct A2 {  
   friend class A;   // C2990  
};  
  
// OK  
template<class T>  
struct B {  
   template<class T>  
   friend class A;  
};  
```
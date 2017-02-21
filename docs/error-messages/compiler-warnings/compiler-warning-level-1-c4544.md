---
title: "Compilerwarnung (Stufe 1) C4544 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4544"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4544"
ms.assetid: 11ee04df-41ae-435f-af44-881e801315a8
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerwarnung (Stufe 1) C4544
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'declaration': Standardvorlagenargument wird für diese Vorlagendeklaration ignoriert  
  
 Ein Standardvorlagenargument wurde an einer falschen Position angegeben und wurde ignoriert.  Ein Standardvorlagenargument für eine Klassenvorlage kann nur in der Deklaration oder Definition der Klassenvorlage und nicht auf einem Member der Klassenvorlage angegeben werden.  
  
 Im folgenden Beispiel wird C4545 generiert, und im nächsten Beispiel wird gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C4544.cpp  
// compile with: /W1 /LD  
template <class T>   
struct S  
{  
   template <class T1>   
      struct S1;  
   void f();  
};  
  
template <class T=int>  
template <class T1>  
struct S<T>::S1 {};   // C4544  
```  
  
 In diesem Beispiel gilt der Standardparameter für die Klassenvorlage `S`:  
  
```  
// C4544b.cpp  
// compile with: /LD  
template <class T = int>   
struct S  
{  
   template <class T1>   
      struct S1;  
   void f();  
};  
  
template <class T>  
template <class T1>  
struct S<T>::S1 {};  
```
---
title: "Compilerfehler C2754"
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
  - "C2754"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2754"
ms.assetid: 1cab66c5-da9d-4b81-b7fb-9cdc48ff1ccc
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2754
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Spezialisierung': Eine teilweise Spezialisierung darf keinen abhängigen Nichttyp\-Vorlagenparameter haben  
  
 Es wurde versucht, eine Vorlagenklasse mit einem abhängigen Nichttyp\-Vorlagenparameter teilweise zu spezialisieren.  Dies ist nicht zulässig.  
  
 Im folgenden Beispiel wird C2754 generiert:  
  
```  
// C2754.cpp  
// compile with: /c  
  
template<class T, T t>  
struct A {};  
  
template<class T, int N>  
struct B {};  
  
template<class T> struct A<T,5> {};   // C2754  
template<> struct A<int,5> {};   // OK  
template<class T> struct B<T,5> {};   // OK  
```
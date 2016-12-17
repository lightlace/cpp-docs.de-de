---
title: "Compilerfehler C2894"
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
  - "C2894"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2894"
ms.assetid: 4e250579-2b59-4993-a6f4-49273e7ecf06
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2894
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vorlagen können nicht mit "C"\-Bindung deklariert werden  
  
 Dieser Fehler kann durch eine Vorlage, die in einem `extern`  "C"\-Block definiert wird, verursacht werden.  
  
 Im folgenden Beispiel wird C2894 generiert:  
  
```  
// C2894.cpp  
extern "C" {  
   template<class T> class stack {};   // C2894 fail  
  
   template<class T> void f(const T &aT) {}   // C2894  
}  
```  
  
 Im folgenden Beispiel wird C2894 generiert:  
  
```  
// C2894b.cpp  
// compile with: /c  
extern "C" template<class T> void f(const T &aT) {}   // C2894  
  
template<class T> void f2(const T &aT) {}   // OK  
```
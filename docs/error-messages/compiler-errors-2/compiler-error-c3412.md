---
title: "Compilerfehler C3412"
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
  - "C3412"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3412"
ms.assetid: aa4dd43b-54ce-4cda-85c1-1a77dd6e34fa
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3412
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Vorlage': Vorlage in aktuellem Bereich kann nicht spezialisiert werden  
  
 Eine Vorlage kann nicht im Gültigkeitsbereich einer Klasse, sondern nur im globalen oder in dem des Namespaces spezialisiert werden.  
  
## Beispiel  
 Im folgenden Beispiel wird C3412 generiert.  
  
```  
// C3412.cpp  
template <class T>  
struct S {  
   template <>  
   struct S<int> {};   // C3412 in a class  
};  
```  
  
## Beispiel  
 Das folgende Beispiel zeigt eine mögliche Lösung.  
  
```  
// C3412b.cpp  
// compile with: /c  
template <class T>  
struct S {};  
  
template <>  
struct S<int> {};  
```
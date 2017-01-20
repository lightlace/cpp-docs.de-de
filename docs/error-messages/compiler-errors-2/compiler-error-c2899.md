---
title: "Compilerfehler C2899"
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
  - "C2899"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2899"
ms.assetid: a8942605-5bef-4d1c-b74a-41ae25423b22
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2899
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der Typname kann nicht außerhalb einer Vorlagendeklaration verwendet werden  
  
 Das [typename](../../cpp/typename.md)\-Schlüsselwort kann nur in einer Vorlagendefinition oder \-deklaration verwendet werden.  In einer Vorlagendeklaration kann es auf zwei Arten verwendet werden:  
  
```  
// C2899.cpp  
// compile with: /c  
template<typename T>   
class X {};  
  
// Another way  
template<class T>   
struct XX {  
   typename T::A a;   // T::A is a type  
};  
```  
  
 Im folgenden Beispiel wird C2899 generiert:  
  
```  
// C2899b.cpp  
// compile with: /c  
struct Y {  
   typedef int B;  
   typename Y::B b;   // C2899  
};  
  
```
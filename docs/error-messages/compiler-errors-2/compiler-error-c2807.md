---
title: "Compilerfehler C2807"
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
  - "C2807"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2807"
ms.assetid: bd7a207a-f379-4de6-8ee8-c7cab78b3480
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2807
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der zweite formale Parameter auf den Operator Postfix 'Operator' muss den Typ 'int' haben  
  
 Der zweite Parameter eines Operators Postfix hat den falschen Typ.  
  
 Im folgenden Beispiel wird C2807 generiert:  
  
```  
// C2807.cpp  
// compile with: /c  
class X {  
public:  
   X operator++ ( X );   // C2807 nonvoid parameter  
   X operator++ ( int );   // OK, int parameter  
};  
```
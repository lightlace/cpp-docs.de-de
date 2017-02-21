---
title: "Compilerfehler C2807 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2807"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2807"
ms.assetid: bd7a207a-f379-4de6-8ee8-c7cab78b3480
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
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
---
title: "Compilerfehler C2821"
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
  - "C2821"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2821"
ms.assetid: e8d71988-a968-4484-94db-e8c3bad74a4a
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2821
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der erste formale Parameter für den Operator "new" muss den Typ "unsigned int" haben  
  
 Der erste formale Parameter des [Operators "new"](../Topic/operator%20new%20\(%3Cnew%3E\).md) muss ein `int` ohne Vorzeichen sein.  
  
 Im folgenden Beispiel wird C2821 generiert:  
  
```  
// C2821.cpp  
// compile with: /c  
void * operator new( /* unsigned int,*/ void * );   // C2821  
void * operator new( unsigned int, void * );  
```
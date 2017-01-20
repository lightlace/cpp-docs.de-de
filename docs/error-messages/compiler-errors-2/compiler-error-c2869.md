---
title: "Compilerfehler C2869"
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
  - "C2869"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2869"
ms.assetid: 6e30c001-47f3-4101-b9f1-cc542c9fffae
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2869
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Name' : Wurde bereits als Namespace definiert  
  
 Ein bereits vergebener Name kann nicht erneut für einen Namespace verwendet werden.  
  
 Im folgenden Beispiel wird C2869 generiert:  
  
```  
// C2869.cpp  
// compile with: /c  
namespace A { int i; };  
  
class A {};   // C2869, A is already used  
```
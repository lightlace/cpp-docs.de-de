---
title: "Compilerfehler C2755"
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
  - "C2755"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2755"
ms.assetid: 8ee4eeb6-4757-4efe-9100-38ff4a96f1de
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2755
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Parameter': Nichttyp\-Parameter einer teilweisen Spezialisierung muss ein einfacher Bezeichner sein  
  
 Der Nichttyp\-Parameter muss ein einfacher Bezeichner bzw. ein Element sein, das vom Compiler zur Kompilierzeit in einen einfachen Bezeichner aufgelöst werden kann, oder ein konstanter Wert.  
  
 Im folgenden Beispiel wird C2755 generiert:  
  
```  
// C2755.cpp  
template<int I, int J>  
struct A {};  
  
template<int I>   
struct A<I,I*5> {};   // C2755  
// try the following line instead  
// struct A<I,5> {};  
```
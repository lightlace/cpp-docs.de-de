---
title: "Compilerfehler C2766 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2766"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2766"
ms.assetid: 8032f4ca-6827-4f04-9c61-c44643c85cc4
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C2766
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

explizite Spezialisierung; 'Spezialisierung' wurde bereits definiert  
  
 Doppelte explizite Spezialisierungen sind nicht zulässig.  Weitere Informationen finden Sie unter [Explizite Spezialisierung von Funktionsvorlagen](../../cpp/explicit-specialization-of-function-templates.md).  
  
 Im folgenden Beispiel wird C2766 generiert:  
  
```  
// C2766.cpp  
// compile with: /c  
template<class T>   
struct A {};  
  
template<>   
struct A<int> {};  
  
template<>   
struct A<int> {};   // C2766  
// try the following line instead  
// struct A<char> {};  
```
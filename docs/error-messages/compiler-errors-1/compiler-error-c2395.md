---
title: "Compiler Error C2395 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2395"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2395"
ms.assetid: 2d9e3b28-8c2c-4f41-a57f-61ef88fc2af0
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Compiler Error C2395
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'your\_type::operator'op'': CLR oder WinRT\-Operator ist ungültig.Mindestens ein Parameter muss einer der folgenden Typen sein: 'T', 'T%', 'T&', 'T^', 'T^%', 'T^&', wobei T \= 'your\_type' ist  
  
 Ein Operator in einer Windows\-Runtime oder einem verwalteten Typen hatte nicht mindestens einen Parameter, dessen Typ mit dem Typen des Operatorrückgabewerts identisch ist.  
  
 Im folgenden Beispiel wird C2395 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C2395.cpp  
// compile with: /clr /c  
value struct V {  
   static V operator *(int i, char c);   // C2395  
  
   // OK  
   static V operator *(V v, char c);  
   // or  
   static V operator *(int i, V& rv);  
};  
```
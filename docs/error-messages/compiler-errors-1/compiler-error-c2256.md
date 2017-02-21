---
title: "Compilerfehler C2256 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2256"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2256"
ms.assetid: 171fa2bc-8c72-49cd-afe5-d723b7acd3c5
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C2256
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Verwendung von Friend\-Spezifizierer im Zusammenhang mit 'Funktion' nicht zulässig  
  
 Ein Destruktor oder Konstruktor kann nicht als [friend](../../cpp/friend-cpp.md) angegeben werden.  
  
 Im folgenden Beispiel wird C2256 generiert:  
  
```  
// C2256.cpp  
// compile with: /c  
class C {  
public:  
   friend ~C();   // C2256  
   ~C();   // OK  
};  
```
---
title: "Compilerwarnung (Stufe 1) C4399 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4399"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4399"
ms.assetid: f58d9ba7-71a0-4c3b-b26f-f946dda8af30
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerwarnung (Stufe 1) C4399
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Symbol': Prozessspezifische Symbole sollten nicht mit \_\_declspec\(dllimport\) gekennzeichnet sein, wenn sie mit \/clr:pure kompiliert werden.  
  
 Daten eines systemeigenen Abbildes oder eines Abbildes mit systemeigenen sowie CLR\-Konstrukten können nicht in ein reines Abbild importiert werden.  Zur Behebung des Problems kompilieren Sie mit **\/clr** \(nicht **\/clr:pure**\), oder löschen Sie `__declspec(dllimport)`.  
  
## Beispiel  
 Im folgenden Beispiel wird C4399 generiert.  
  
```  
// C4399.cpp  
// compile with: /clr:pure /doc /W1 /c  
__declspec(dllimport) __declspec(process) extern const int i;   // C4399  
```
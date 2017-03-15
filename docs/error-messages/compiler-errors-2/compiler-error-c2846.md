---
title: "Compilerfehler C2846 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2846"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2846"
ms.assetid: bc090ec2-5410-4112-9ec6-261325374375
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C2846
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Konstruktor': Eine Schnittstelle kann keinen Konstruktor besitzen  
  
 Eine Visual C\+\+\-[Schnittstelle](../../cpp/interface.md) darf keinen Konstruktor aufweisen.  
  
 Im folgenden Beispiel wird C2846 generiert:  
  
```  
// C2846.cpp  
// compile with: /c  
__interface C {  
   C();   // C2846 constructor not allowed in an interface  
};  
```
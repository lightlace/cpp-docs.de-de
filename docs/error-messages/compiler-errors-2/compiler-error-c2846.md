---
title: "Compilerfehler C2846"
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
  - "C2846"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2846"
ms.assetid: bc090ec2-5410-4112-9ec6-261325374375
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
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
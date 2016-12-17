---
title: "Compilerfehler C2849"
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
  - "C2849"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2849"
ms.assetid: e28f6b3e-e0e7-4f92-b006-ebaa81d368e6
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2849
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Destruktor': Eine Schnittstelle kann keinen Destruktor besitzen  
  
 Eine Visual C\+\+\-[Schnittstelle](../../cpp/interface.md) darf keinen Destruktor aufweisen.  
  
 Im folgenden Beispiel wird C2849 generiert:  
  
```  
// C2849.cpp  
// compile with: /c  
__interface C {  
   ~C();   // C2849 destructor not allowed in an interface  
};  
```
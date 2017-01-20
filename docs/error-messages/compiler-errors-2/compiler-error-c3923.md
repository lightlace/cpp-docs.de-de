---
title: "Compilerfehler C3923"
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
  - "C3923"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3923"
ms.assetid: db8838e9-6344-4cd6-83e0-a8abeb12c4c0
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3923
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

„member“: Definitionen für lokale Klassen, Strukturen oder Unions sind in einer Memberfunktion einer verwalteten oder WinRT\-Klasse nicht zulässig.  
  
## Beispiel  
 Im folgenden Beispiel wird C3923 generiert.  
  
```  
// C3923.cpp  
// compile with: /clr /c  
ref struct x {  
   void Test() {  
      struct a {};   // C3923  
      class b {};   // C3923  
      union c {};   // C3923  
   }  
};  
```
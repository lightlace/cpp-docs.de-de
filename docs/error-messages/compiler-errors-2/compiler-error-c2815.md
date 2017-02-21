---
title: "Compilerfehler C2815 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2815"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2815"
ms.assetid: d0256fd6-0721-4c99-b03c-52d96e77a613
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C2815
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Operator delete': Der erste formale Parameter muss 'void \*' sein, aber es wurde 'Parameter' verwendet  
  
 Eine benutzerdefinierte Funktion für einen [Operator delete](../Topic/operator%20delete%20\(%3Cnew%3E\).md) muss als erstes einen formalen Parameter vom Typ `void *` enthalten.  
  
 Im folgenden Beispiel wird C2815 generiert:  
  
```  
// C2815.cpp  
// compile with: /c  
class CMyClass {  
public:  
   void mf1(int *a);  
   void operator delete(CMyClass *);   // C2815  
   void operator delete(void *);   
};  
```
---
title: "Compilerfehler C2577 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2577"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2577"
ms.assetid: fc79ef83-8362-40a2-9257-8037c3195ce4
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C2577
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Member' : Destruktor\/Finalizer kann nicht über einen Rückgabetyp verfügen  
  
 Ein Destruktor kann keinen Wert vom Typ `void` oder eines anderen Typs zurückgeben.  Entfernen Sie die `return`\-Anweisung aus der Destruktordefinition.  
  
## Beispiel  
 Im folgenden Beispiel wird C2577 generiert.  
  
```  
// C2577.cpp  
// compile with: /c  
class A {  
public:  
   A() {}  
   ~A(){  
      return 0;   // C2577  
   }  
};  
```
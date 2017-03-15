---
title: "Compilerfehler C3611 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3611"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3611"
ms.assetid: 42f3e320-41de-420a-bd05-8924cab765aa
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# Compilerfehler C3611
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion': Für eine versiegelte Funktion kann kein pure\-Spezifizierer angegeben werden  
  
 Eine versiegelte Funktion wurde falsch deklariert.  Weitere Informationen finden Sie unter [sealed](../../windows/sealed-cpp-component-extensions.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C3611 generiert.  
  
```  
// C3611.cpp  
// compile with: /clr /c  
  
ref struct V {  
   virtual void Test() sealed = 0;   // C3611  
   virtual void Test2() sealed;   // OK  
   virtual void Test3() = 0;   // OK  
};  
```
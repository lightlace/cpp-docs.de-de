---
title: "Compilerfehler C3755"
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
  - "C3755"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3755"
ms.assetid: 9317b55e-a52e-4b87-b915-5a208d6eda38
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3755
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Delegat': Ein Delegat kann nicht definiert werden  
  
 Ein [delegate](../../windows/delegate-cpp-component-extensions.md) kann deklariert, nicht aber definiert werden.  
  
## Beispiel  
 Im folgenden Beispiel wird C3755 generiert.  
  
```  
// C3755.cpp  
// compile with: /clr /c  
delegate void MyDel() {};   // C3755  
```  
  
## Beispiel  
 C3755 kann auch auftreten, wenn Sie versuchen, eine Delegatvorlage zu erstellen.  Im folgenden Beispiel wird C3755 generiert.  
  
```  
// C3755_b.cpp  
// compile with: /clr /c  
ref struct R {  
   template<class T>  
   delegate void D(int) {}   // C3755  
};  
```
---
title: "Compilerfehler C2524"
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
  - "C2524"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2524"
ms.assetid: e71d17f5-2fc2-416b-8dbd-e9bed85eb33a
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2524
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Destruktor': Die Parameterliste von Destruktor\/Finalizer muss 'void' sein  
  
 Der Destruktor oder Finalizer hat eine Parameterliste, die nicht [void](../../cpp/void-cpp.md) ist.  Andere Parametertypen sind nicht zulässig.  
  
## Beispiel  
 Im folgenden Code wird C2524 generiert.  
  
```  
// C2524.cpp  
// compile with: /c  
class A {  
   A() {}  
   ~A(int i) {}    // C2524  
   // try the following line instead  
   // ~A() {}  
};  
```  
  
## Beispiel  
 Im folgenden Code wird C2524 generiert.  
  
```  
// C2524_b.cpp  
// compile with: /clr /c  
ref struct I1 {  
protected:  
   !I1(int i);   // C2524  
   // try the following line instead  
   // !I1();  
};  
```
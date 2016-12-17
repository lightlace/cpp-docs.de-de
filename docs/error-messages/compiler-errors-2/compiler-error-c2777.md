---
title: "Compilerfehler C2777"
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
  - "C2777"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2777"
ms.assetid: 5fe158c0-2a65-488a-aca2-61d4a8b32d43
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2777
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Nur eine "put"\-Methode kann pro Eigenschaft angegeben werden  
  
 Ein [Eigenschaft](../../cpp/property-cpp.md) declspec\-Modifizierer verfügte über mehr als eine `put`\-Eigenschaft.  
  
 Im folgenden Beispiel wird C2777 generiert:  
  
```  
// C2777.cpp  
struct A {  
   __declspec(property(put=PutProp,put=PutPropToo))   // C2777  
   // try the following line instead  
   // __declspec(property(put=PutProp))  
      int prop;  
   int PutProp(void);  
   int PutPropToo(void);  
};  
```
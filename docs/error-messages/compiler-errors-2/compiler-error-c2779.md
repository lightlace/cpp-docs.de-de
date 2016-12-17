---
title: "Compilerfehler C2779"
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
  - "C2779"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2779"
ms.assetid: 4a00e492-855a-41f3-8a18-5f60ee20c2f2
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2779
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Deklaration': Eigenschaftenmethoden können nur mit nicht statischen Datenmembern verbunden werden  
  
 Das erweiterte `property`\-Attribut wurde falsch auf einen statischen Datenmember angewendet.  
  
 Im folgenden Beispiel wird C2779 generiert:  
  
```  
// C2779.cpp  
struct A {  
   static __declspec(property(put=PutProp))  
   // try the following line instead  
   __declspec(property(put=PutProp))  
      int prop;   // C2779  
   int PutProp(void);  
};  
```
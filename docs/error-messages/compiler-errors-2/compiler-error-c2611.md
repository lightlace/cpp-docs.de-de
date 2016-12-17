---
title: "Compilerfehler C2611"
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
  - "C2611"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2611"
ms.assetid: 3f2d5253-f24f-4724-83d0-6b2aa6a4e551
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2611
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Token': unzulässig nach '~' \(Bezeichner erforderlich\)  
  
 Das Token ist kein Bezeichner.  
  
 Im folgenden Beispiel wird C2611 generiert:  
  
```  
// C2611.cpp  
// compile with: /c  
class C {  
   C::~operator int();   // C2611  
   ~C();   // OK  
};  
```
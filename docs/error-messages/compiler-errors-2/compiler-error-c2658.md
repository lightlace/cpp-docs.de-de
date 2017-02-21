---
title: "Compilerfehler C2658 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2658"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2658"
ms.assetid: 638368e8-7893-4a14-abec-13c768a9543a
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C2658
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**"**   
 ***Member* ": Neudefinition in anonymes struct\/union**  
  
 In zwei anonymen Strukturen oder Unions waren Memberdeklarationen mit identischem Bezeichner, aber unterschiedlichen Typen enthalten.  Bei Verwendung von [\/Za](../../build/reference/za-ze-disable-language-extensions.md) wird dieser Fehler auch für Member mit identischem Bezeichner und Typ ausgegeben.  
  
 Im folgenden Beispiel wird C2658 generiert:  
  
```  
// C2658.cpp  
// compile with: /c  
struct X {  
   union { // can be struct too  
      int i;  
   };  
   union {  
      int i;   // Under /Za, C2658  
      // int i not needed here because it is defined in the first union  
   };  
};  
  
struct Z {  
   union {  
      char *i;  
   };  
  
   union {  
      void *i;   // C2658 redefinition of 'i'  
      // try the following line instead  
      // void *ii;  
   };  
};  
```
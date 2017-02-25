---
title: "Compilerfehler C2556 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2556"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2556"
ms.assetid: fc4399ad-45b3-49fd-be1f-0b13956a595a
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C2556
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner': Überladene Funktionen unterscheiden sich nur in ihrem Ergebnistyp  
  
 Die überladenen Funktionen haben unterschiedliche Rückgabetypen, aber die gleiche Parameterliste.  Jede überladene Funktion muss eine eigene Liste formaler Parameter haben.  
  
 Im folgenden Beispiel wird C2556 generiert:  
  
```  
// C2556.cpp  
// compile with: /c  
class C {  
   int func();  
   double func();   // C2556  
   int func(int i);   // ok parameter lists differ  
};  
```
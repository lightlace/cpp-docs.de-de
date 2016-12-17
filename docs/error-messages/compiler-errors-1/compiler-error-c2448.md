---
title: "Compilerfehler C2448"
ms.custom: na
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C2448"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2448"
ms.assetid: e255df3c-f861-4b4d-a193-8768cef061a5
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2448
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner' : Funktionsstil\-Initialisierer scheint eine Funktionsdefinition zu sein  
  
 Die Funktionsdefinition ist nicht korrekt.  
  
 Dieser Fehler kann von einer C\-Parameterliste im alten Stil verursacht werden.  
  
 Im folgenden Beispiel wird C2448 generiert:  
  
```  
// C2448.cpp  
void func(c)  
   int c;  
{}   // C2448  
```
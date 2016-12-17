---
title: "Compilerfehler C2480"
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
  - "C2480"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2480"
ms.assetid: 1a58d1c2-971b-4084-96fa-f94aa51c02f1
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2480
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner' : 'Thread' ist nur für statische Daten gültig  
  
 Sie können das `thread`\-Attribut nicht mit einer automatischen Variablen, nicht statischen Datenmembern, Funktionsparametern oder in Funktionsdeklarationen oder \-definitionen verwenden.  
  
 Verwenden Sie das `thread`\-Attribut nur für globale Variablen, statische Datenmember und lokale statische Variablen.  
  
 Im folgenden Beispiel wird C2480 generiert:  
  
```  
// C2480.cpp  
// compile with: /c  
__declspec( thread ) void func();   // C2480  
__declspec( thread ) static int i;   // OK  
```
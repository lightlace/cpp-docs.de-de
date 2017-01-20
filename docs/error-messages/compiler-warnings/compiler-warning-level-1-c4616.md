---
title: "Compilerwarnung (Stufe 1) C4616"
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
  - "C4616"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4616"
ms.assetid: 71e15265-c5bc-42ce-a6a9-4879892472b1
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4616
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#Pragmawarnung : Warnung Nummer 'Nummer' ist keine gültige Compilerwarnung  
  
 Die im [warning](../../preprocessor/warning.md)\-Pragma angegebene Warnungsnummer kann nicht erneut zugewiesen werden.  Das Pragma wurde ignoriert.  
  
 Im folgenden Beispiel wird C4616 generiert:  
  
```  
// C4616.cpp  
// compile with: /W1 /c  
#pragma warning( disable : 0 )   // C4616  
#pragma warning( disable : 999 )   // OK  
#pragma warning( disable : 4998 )   // OK  
```
---
title: "Compilerwarnung (Stufe 1) C4440"
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
  - "C4440"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4440"
ms.assetid: 78b9642a-a93e-401e-9d92-372f6451bc5d
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4440
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Neudefinition der Aufrufkonvention von 'calling\_convention1' zu 'calling\_convention2' wurde ignoriert  
  
 Eine versuchte Änderung der Aufrufkonvention wurde nicht berücksichtigt.  
  
 Im folgenden Beispiel wird C4440 generiert:  
  
```  
// C4440.cpp  
// compile with: /W1 /LD /clr  
typedef void __clrcall F();  
typedef F __cdecl *PFV;   // C4440  
```
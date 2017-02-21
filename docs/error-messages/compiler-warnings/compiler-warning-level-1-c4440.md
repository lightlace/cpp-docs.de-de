---
title: "Compilerwarnung (Stufe 1) C4440 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4440"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4440"
ms.assetid: 78b9642a-a93e-401e-9d92-372f6451bc5d
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
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
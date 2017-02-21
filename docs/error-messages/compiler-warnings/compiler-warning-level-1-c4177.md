---
title: "Compilerwarnung (Stufe 1) C4177 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4177"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4177"
ms.assetid: 2b05a5b3-696e-4f21-818e-227b9335e748
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerwarnung (Stufe 1) C4177
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Das \#pragma\-Pragma sollte sich im globalen Gültigkeitsbereich befinden.  
  
 Das [pragma](../../preprocessor/pragma-directives-and-the-pragma-keyword.md)\-Pragma sollte nicht innerhalb eines lokalen Gültigkeitsbereichs verwendet werden. Das **Pragma** ist erst gültig, wenn der globale Gültigkeitsbereich im Anschluss an den aktuellen Bereich gefunden wurde.  
  
 Im folgenden Beispiel wird C4177 generiert.  
  
```  
// C4177.cpp // compile with: /W1 // #pragma bss_seg("global")   // OK int main() { #pragma bss_seg("local")    // C4177 }  
```
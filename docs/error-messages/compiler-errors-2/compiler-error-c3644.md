---
title: "Compilerfehler C3644"
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
  - "C3644"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3644"
ms.assetid: 2e3f6c41-3ec5-4a01-82bc-f11b61ebe68e
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3644
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion': die Funktion kann nicht zum Generieren von verwaltetem Code kompiliert werden  
  
 Durch das Vorhandensein einiger Schlüsselwörter in einer Funktion wird die Funktion zu systemeigen Code kompiliert.  
  
 Im folgenden Beispiel wird C3644 generiert:  
  
```  
// C3644.cpp  
// compile with: /clr  
// processor: x86  
  
void __clrcall Func2(int i) {  
   __asm {}   // C3644  
}  
```
---
title: "Compilerfehler C2490 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2490"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2490"
ms.assetid: 9de6bddd-b2e2-4ce6-b33b-201a8c2c8c54
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C2490
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Schlüsselwort' in Funktionen mit dem 'naked'\-Attribut nicht erlaubt  
  
 Eine Funktion, die als [naked](../../cpp/naked-cpp.md) definiert wurde, kann keine strukturierte Ausnahmebehandlung verwenden.  
  
 Im folgenden Beispiel wird C2490 generiert:  
  
```  
// C2490.cpp  
// processor: x86  
__declspec( naked ) int func() {  
   __try{}   // C2490, structured exception handling  
}  
```
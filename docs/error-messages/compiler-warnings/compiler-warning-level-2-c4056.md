---
title: "Compilerwarnung (Stufe 2) C4056 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4056"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4056"
ms.assetid: a3c3a9b8-ec30-452d-96cb-3694adcce789
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerwarnung (Stufe 2) C4056
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Überlauf bei Gleitkommakonstanten\-Arithmetik  
  
 Durch die Gleitkommakonstanten\-Arithmetik wird ein Ergebnis erzeugt, das den maximal zulässigen Wert überschreitet.  
  
 Diese Warnung wird möglicherweise durch Compileroptimierungen verursacht, die während der arithmetischen Auswertung von Konstanten ausgeführt werden.  Sie können diese Warnung gefahrlos ignorieren, wenn sie durch Deaktivieren der Optimierung \([\/Od](../../build/reference/od-disable-debug.md)\) vermieden werden kann.  
  
 Im folgenden Beispiel wird C4056 generiert:  
  
```  
// C4056.cpp  
// compile with: /W2 /LD  
#pragma warning (default : 4056)  
float fp_val = 1.0e300 * 1.0e300;   // C4056  
```
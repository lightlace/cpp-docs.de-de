---
title: "NMAKE: Schwerwiegender Fehler U1070 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "U1070"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1070"
ms.assetid: 8639fc39-b4b1-48f5-ac91-0e9fb61680fd
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# NMAKE: Schwerwiegender Fehler U1070
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Schleife in Makrodefinition "Makroname"  
  
 Die angegebene Makrodefinition enthielt ein Makro, dessen Definition das angegebene Makro enthielt.  Zirkuläre Makrodefinitionen sind unzulässig.  
  
## Beispiel  
 Durch die folgenden Makrodefinitionen  
  
```  
ONE=$(TWO)  
TWO=$(ONE)  
```  
  
 wird dieser Fehler verursacht:  
  
```  
cycle in macro definition 'TWO'  
```
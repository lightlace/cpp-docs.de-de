---
title: "NMAKE: Schwerwiegender Fehler U1070"
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
  - "U1070"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1070"
ms.assetid: 8639fc39-b4b1-48f5-ac91-0e9fb61680fd
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
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
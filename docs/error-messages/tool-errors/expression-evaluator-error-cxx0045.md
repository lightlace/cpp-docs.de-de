---
title: "Ausdrucksauswertungsfehler CXX0045"
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
  - "CXX0045"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAN0045"
  - "CXX0045"
ms.assetid: 32181bc8-e79c-4ad7-a82f-47c62ec06d7d
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Ausdrucksauswertungsfehler CXX0045
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dies ist keine Funktion  
  
 Eine Argumentliste wurde an ein Symbol im Programm übergeben, das keinen Namen einer Funktion darstellt.  
  
## Beispiel  
  
```  
queue( alpha, beta )  
```  
  
 wenn es sich bei `queue` um keine Funktion handelt.  
  
 Dieser Fehler ist mit CAN0045 identisch.
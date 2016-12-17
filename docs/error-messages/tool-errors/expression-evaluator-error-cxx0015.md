---
title: "Ausdrucksauswertungsfehler CXX0015"
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
  - "CXX0015"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAN0015"
  - "CXX0015"
ms.assetid: 35efaf77-d578-48d8-bfc5-fdeb2a46a8b5
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Ausdrucksauswertungsfehler CXX0015
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ausdruck zu komplex \(Stapelüberlauf\)  
  
 Der eingegebene Ausdruck war zu komplex oder zu tief geschachtelt für den verfügbaren Speicher der C\-Ausdrucksauswertung.  
  
 Der Überlauf ist möglicherweise aufgrund zu vieler ausstehender Berechnungen aufgetreten.  
  
 Ordnen Sie den Ausdruck so an, dass jede Komponente des Ausdrucks dann ausgewertet werden kann, wenn sie auftritt, und nicht gewartet werden muss, bis andere Teile des Ausdrucks berechnet wurden.  
  
 Teilen Sie den Ausdruck in mehrere Befehle auf.  
  
 Dieser Fehler ist mit CAN0015 identisch.
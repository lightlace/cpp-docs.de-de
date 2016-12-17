---
title: "C-Laufzeitfehler R6017"
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
  - "R6017"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "R6017"
ms.assetid: df3ec5f5-6771-4648-ba06-0e26c6a1cc6a
caps.latest.revision: 7
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# C-Laufzeitfehler R6017
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

unerwarteter Multithread\-Sperrenfehler  
  
 Der Prozess hat beim Versuch, auf eine C\-Laufzeitfunktion für die Multithreadsperre einer Systemressource zuzugreifen, eine unerwartete Fehlermeldung empfangen.  
  
 Dieser Fehler tritt in der Regel auf, wenn das Programm unbeabsichtigt die Laufzeit\-Heapdaten ändert.  Er kann jedoch auch durch einen internen Fehler im Laufzeitcode oder durch das Betriebssystem verursacht werden.
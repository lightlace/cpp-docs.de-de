---
title: "C-Laufzeitfehler R6017 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "R6017"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "R6017"
ms.assetid: df3ec5f5-6771-4648-ba06-0e26c6a1cc6a
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# C-Laufzeitfehler R6017
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

unerwarteter Multithread\-Sperrenfehler  
  
 Der Prozess hat beim Versuch, auf eine C\-Laufzeitfunktion für die Multithreadsperre einer Systemressource zuzugreifen, eine unerwartete Fehlermeldung empfangen.  
  
 Dieser Fehler tritt in der Regel auf, wenn das Programm unbeabsichtigt die Laufzeit\-Heapdaten ändert.  Er kann jedoch auch durch einen internen Fehler im Laufzeitcode oder durch das Betriebssystem verursacht werden.
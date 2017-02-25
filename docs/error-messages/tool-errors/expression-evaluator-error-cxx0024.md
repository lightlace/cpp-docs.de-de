---
title: "Ausdrucksauswertungsfehler CXX0024 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "CXX0024"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAN0024"
  - "CXX0024"
ms.assetid: eca6adbd-8ff2-4f51-a1cc-a2e9d5d0a47d
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Ausdrucksauswertungsfehler CXX0024
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Operation erfordert l\-Wert  
  
 Ein Ausdruck, der nicht als l\-Wert ausgewertet werden kann, wurde für eine Operation, für die ein l\-Wert erforderlich ist, angegeben.  
  
 Bei einem l\-Wert handelt es sich um einen Ausdruck, durch den auf ein Speicherbereich verwiesen wird. Er wird als l\-Wert bezeichnet, da er auf der linken Seite einer Zuweisungsanweisung auftritt.  
  
 Beispielsweise stellt `buffer[count]` einen gültigen l\-Wert dar, da durch ihn auf einen bestimmten Speicherbereich gezeigt wird.  Der logische Vergleich `zed != 0` stellt keinen gültigen l\-Wert dar, da er zu TRUE oder FALSE und nicht zu einer Speicheradresse ausgewertet wird.  
  
 Dieser Fehler ist mit CAN0024 identisch.
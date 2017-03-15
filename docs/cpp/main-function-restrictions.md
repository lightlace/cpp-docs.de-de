---
title: "Einschr&#228;nkungen der main-Funktion | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Main"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "main-Funktion, Einschränkungen bei der Verwendung"
ms.assetid: 7b3df731-344b-44a8-850c-11cbcbfbfa83
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Einschr&#228;nkungen der main-Funktion
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Für die **main**\-Funktion gelten mehrere Einschränkungen, die auf andere C\+\+\-Funktionen nicht zutreffen.  Die **main**\-Funktion:  
  
-   Kann nicht überladen werden \(siehe [Überladen](../misc/overloading-cpp.md)\).  
  
-   Kann nicht als **inline** deklariert werden.  
  
-   Kann nicht als **statisch** deklariert werden.  
  
-   Ihre Adresse kann nicht übernommen werden.  
  
-   Kann nicht aufgerufen werden.  
  
## Siehe auch  
 [main: Programmstart](../cpp/main-program-startup.md)
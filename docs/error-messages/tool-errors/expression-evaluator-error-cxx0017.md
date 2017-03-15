---
title: "Ausdrucksauswertungsfehler CXX0017 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "CXX0017"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAN0017"
  - "CXX0017"
ms.assetid: af74db02-a64d-49ca-8363-3e044a107580
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Ausdrucksauswertungsfehler CXX0017
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Symbol konnte nicht gefunden werden  
  
 Das in dem Ausdruck angegebene Symbol konnte nicht gefunden werden.  
  
 Eine mögliche Ursache ist eine nicht übereinstimmende Groß\-\/Kleinschreibung des Symbolnamens.  Da C und C\+\+ Groß\-\/Kleinschreibung beachten, muss ein Symbolname genau so angegeben werden, wie er in der Quelle definiert wurde.  
  
 Dieser Fehler kann auftreten, wenn der Typ einer Variablen während des Debuggens geändert wird, um die Variable zu überwachen.  Ein neuer Name für einen Typ vom `typedef`\-Schlüsselwort wird deklariert, jedoch kein neuer Typ definiert.  Für die vom Debugger versuchte Typumwandlung ist der Name eines definierten Typs erforderlich.  
  
 Dieser Fehler ist mit CAN0017 identisch.  
  
### Beachten Sie die folgenden Vorschläge zur Problembehebung:  
  
1.  Stellen Sie sicher, dass das Symbol an der Stelle, an der es im Programm eingesetzt wird, bereits deklariert wurde.  
  
2.  Verwenden Sie einen Typnamen anstelle eines mit typedef definierten Namens, um Variablen im Debugger umzuwandeln.
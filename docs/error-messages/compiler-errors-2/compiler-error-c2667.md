---
title: "Compilerfehler C2667 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2667"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2667"
ms.assetid: 3c91d9d1-18fa-4e0d-a9ba-984d38980ca3
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerfehler C2667
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion': Keine der Anzahl Überladungen ergibt die beste Konvertierung  
  
 Ein Aufruf einer überladenen Funktion ist mehrdeutig und kann nicht aufgelöst werden.  
  
 Zur Anpassung der im Funktionsaufruf tatsächlich übergebenen Parameter an die Parameterliste einer der überladenen Funktionen ist es erforderlich, dass es unter sämtlichen Konvertierungen, die von allen anderen überladenen Funktionen benötigt werden, definitiv eine "bestmögliche" Konvertierung gibt.  
  
 Weitere Informationen zur teilweisen Anordnung von Funktionsvorlagen finden Sie im Knowledge Base\-Artikel Q240869.
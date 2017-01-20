---
title: "Ressourcencompiler: Fehler RC2001"
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
  - "RC2001"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC2001"
ms.assetid: 92bfb4c0-1879-4606-bb9f-ef7368707b4a
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Ressourcencompiler: Fehler RC2001
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Zeilenvorschub in Konstante  
  
 Eine Zeichenfolgenkonstante wurde in einer weiteren Zeile ohne umgekehrten Schrägstrich \(**\\**\) oder schließende und wieder öffnende doppelte Anführungszeichen \(**"**\) fortgesetzt.  
  
 Zum Umbrechen einer Zeichenfolgenkonstanten, die mehrere Zeilen der Quelldatei beinhaltet, stehen die beiden folgenden Möglichkeiten zur Verfügung:  
  
-   Beenden Sie die erste Zeile mit dem Zeilenfortsetzungszeichen, einem umgekehrten Schrägstrich.  
  
-   Schließen Sie die Zeichenfolge in der ersten Zeile mit einem doppelten Anführungszeichen, und öffnen Sie die Zeichenfolge in der nächsten Zeile bzw. den nächsten Zeilen mit einem weiteren Anführungszeichen.  
  
 Es genügt nicht, die erste Zeile der Zeichenfolgenkonstanten mit einer Escape\-Sequenz für das Einbetten einer Zeilenendemarke in eine Zeichenfolgenkonstante \(\\n\) zu beenden.
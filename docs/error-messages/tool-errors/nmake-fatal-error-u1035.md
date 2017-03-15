---
title: "NMAKE: Schwerwiegender Fehler U1035 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "U1035"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1035"
ms.assetid: 68f0cc59-007e-4109-ac30-7ac4ac447e6d
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# NMAKE: Schwerwiegender Fehler U1035
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Syntaxfehler: ":" oder "\=" Trennzeichen erwartet  
  
 Es wurde entweder ein Doppelpunkt \(**:**\) oder ein Gleichheitszeichen \(**\=**\) erwartet.  
  
### Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Einem Ziel folgte kein Doppelpunkt.  
  
2.  Einem Ziel mit einem Buchstaben folgte ein Doppelpunkt und kein Leerzeichen, z. B. **a:**.  Dies wurde von NMAKE als Laufwerksangabe interpretiert.  
  
3.  Auf eine Rückschlussregel folgte kein Doppelpunkt.  
  
4.  Auf eine Makrodefinition folgte kein Gleichheitszeichen.  
  
5.  Auf einen umgekehrten Schrägstrich \(**\\**\), der zum Fortsetzen eines Befehls in einer neuen Zeile verwendet wurde, folgte ein Zeichen.  
  
6.  Eine Zeichenfolge, die keiner der Syntaxregeln von NMAKE entspricht, ist aufgetreten.  
  
7.  Das Makefile wurde von einem Textverarbeitungsprogramm formatiert.
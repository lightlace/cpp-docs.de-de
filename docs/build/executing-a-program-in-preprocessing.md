---
title: "Ausf&#252;hren eines Programms im Pr&#228;prozessorlauf | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Programmausführung [C++]"
ms.assetid: 5ecf123a-20e5-40cd-b8d8-dd5a9fdd4b24
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Ausf&#252;hren eines Programms im Pr&#228;prozessorlauf
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Um den Exitcode eines Befehls während des Präprozessorlaufs zu verwenden, wird den Befehl mit den Argumenten in Klammern \(**\[ \]**\) eingegeben.  Die Makros werden erweitert, bevor der Befehl ausgeführt wird.  Die Spezifikation des Befehls wird von NMAKE durch den Exitcode, der in einem Ausdruck für die Steuerung des Präprozessorlaufs verwendet werden kann, ersetzt.  
  
## Siehe auch  
 [Ausdrücke für den Präprozessorlauf eines Makefiles](../build/expressions-in-makefile-preprocessing.md)
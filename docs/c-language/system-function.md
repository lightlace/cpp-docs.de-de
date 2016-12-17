---
title: "Systemfunktion"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Systemfunktion"
ms.assetid: 0786ccdc-20cd-4d96-b3d8-3230507c3066
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Systemfunktion
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 4.10.4.5** Der Inhalt und Ausführmodus der Zeichenfolge durch die **system**\-Funktion  
  
 Die **system**\-Funktion führt einen internen Betriebssystembefehl oder eine .EXE\-, .COM\- \(.CMD in Windows NT\) oder .BAT\-Datei aus einem C\-Programm und nicht aus der Befehlszeile aus.  
  
 Die Systemfunktion durchsucht den Befehlsinterpreter, der in der Regel CMD.EXE im Windows NT\-Betriebssystem oder COMMAND.COM in Windows ist.  Die Systemfunktion gibt die Argumentzeichenfolge anschließend an den Befehlsinterpreter weiter.  
  
 Weitere Informationen finden Sie unter [system, \_wsystem](../c-runtime-library/reference/system-wsystem.md).  
  
## Siehe auch  
 [Bibliotheksfunktionen](../c-language/library-functions.md)
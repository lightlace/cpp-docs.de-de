---
title: "exit-Funktion"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "Exit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "exit-Funktion"
ms.assetid: 26ce439f-81e2-431c-9ff8-a09a96f32127
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# exit-Funktion
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Funktion **exit**, welche in der Standardincludedatei STDLIB.H deklariert wird, beendet ein C\+\+\-Programm.  
  
 Der Wert, der als Argument für **exit** angegeben wird, wird für das Betriebssystem als Rückgabecode oder Exitcode des Programms zurückgegeben.  Gemäß der Konvention bedeutet ein Rückgabecode von Null, dass das Programm erfolgreich abgeschlossen wurde.  
  
> [!NOTE]
>  Sie können die Konstanten `EXIT_FAILURE` und `EXIT_SUCCESS` verwenden, die in STDLIB.H definiert sind, um den Erfolg oder den Fehler des Programms anzugeben.  
  
 Die Ausgabe einer `return`\-Anweisung aus der **main**\-Funktion entspricht dem Aufruf der **exit**\-Funktion mit dem Rückgabewert als das Argument.  
  
 Weitere Informationen finden Sie unter [exit](../c-runtime-library/reference/exit-exit-exit.md) in der *Laufzeitbibliotheksreferenz*.  
  
## Siehe auch  
 [Programmbeendigung](../cpp/program-termination.md)
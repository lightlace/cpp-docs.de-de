---
title: "Linkertoolfehler LNK2013"
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
  - "LNK2013"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2013"
ms.assetid: 21408e2d-3f56-4d1f-a031-00df70785ed4
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Linkertoolfehler LNK2013
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fixup\-Typ Fixup\-Überlauf.Ziel 'Symbolname' ist außerhalb des Bereichs  
  
 Der Linker kann die erforderliche Adresse bzw. den Offset in die angegebene Anweisung nicht finden, da die Entfernung zwischen Zielsymbol und Anweisung zu groß ist.  
  
 Sie beheben dieses Problem, indem Sie mehrere Anwendungen erstellen oder die [\/ORDER](../../build/reference/order-put-functions-in-order.md)\-Option verwenden, um den Abstand zwischen Anweisung und Ziel zu verringern.  
  
 Wenn der Symbolname ein benutzerdefiniertes \(und kein vom Compiler generiertes\) Symbol ist, können Sie auch versuchen, den Fehler mithilfe der folgenden Maßnahmen zu beheben:  
  
-   Ändern Sie die statische Funktion in eine nicht statische Funktion.  
  
-   Benennen Sie den Codeabschnitt mit der statischen Funktion um, sodass er dem Namen des Aufrufers entspricht.  
  
 Überprüfen Sie mit `DUMPBIN /SYMBOLS`, ob eine Funktion statisch ist.
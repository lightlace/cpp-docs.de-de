---
title: "4. Environment Variables"
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
ms.assetid: 4ec7ed81-e9ca-46a1-84f8-8f9ce4587346
caps.latest.revision: 4
caps.handback.revision: "4"
ms.author: "mblome"
manager: "ghogen"
---
# 4. Environment Variables
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dieses Kapitel werden die Umgebungsvariablen OpenMPs C und C\+\+ oder die entsprechenden API \(plattformspezifische Mechanismen\) dieses Steuerelement die parallele Ausführung des Codes:  Die Namen von Umgebungsvariablen muss ein Großbuchstabe sein.  Die Werte, die ihnen zugewiesen wurden, wird die Groß\-\/Kleinschreibung nicht beachtet und haben möglicherweise führende und nachfolgende Leerzeichen.  Änderungen an den Werten nach dem Programm hat begonnen werden ignoriert.  
  
 Die Umgebungsvariablen stehen zur Verfügung:  
  
-   **OMP\_SCHEDULE** legt die Ablaufzeit zeitplan Segmentgröße und den Typ fest.  
  
-   **OMP\_NUM\_THREADS** legt die Anzahl von Threads fest, die während der Ausführung verwendet werden soll.  
  
-   **OMP\_DYNAMIC** aktiviert oder deaktiviert dynamische Anpassung der Anzahl von Threads.  
  
-   **OMP\_NESTED** aktiviert oder deaktiviert geschachtelten Parallelität.  
  
 Die Beispiele in diesem Kapitel werden nur, wie diese Variablen können in der Umgebung Shells Unixs C \(csh\) festgelegt werden.  In Korn\-Shell und IN DOS\-Umgebung sind die Aktionen ähnlich wie folgt:  
  
 csh:  
 setenv „OMP\_SCHEDULE dynamisch“  
  
 KSH:  
 OMP\_SCHEDULE\= dynamisch“ Exportieren "  
  
 DOS:  
 legen Sie fest OMP\_SCHEDULE\=“ dynamisches "
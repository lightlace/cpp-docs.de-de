---
title: "Befehls-IDs | Microsoft Docs"
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
  - "Befehls-IDs"
  - "Befehls-IDs, MFC"
ms.assetid: e0171a2b-45b9-41fa-945d-ec2f7602ded0
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Befehls-IDs
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein Befehl wird vollständig durch die Befehls\-ID allein beschrieben \(codiert in der **WM\_COMMAND** Meldung\).  Diese ID wird dem Benutzeroberflächeobjekt zugeordnet, das den Befehl generiert.  In der Regel werden IDs für die Funktionalität des Benutzeroberflächeobjekts genannt, das sie zugewiesen werden.  
  
 Ein freier Raum alles Element im Menü Bearbeiten eine ID wie **ID\_EDIT\_CLEAR\_ALL** zugewiesen werden.  Die Klassenbibliothek definiert mehrere IDs, besonders für Befehle, die das Framework selbst behandelt, wie **ID\_EDIT\_CLEAR\_ALL** oder `ID_FILE_OPEN`.  Sie erstellen andere Befehls\-IDs sich.  
  
 Wenn Sie eigene Menüs im Visual C\+\+\-Menü\-Editor erstellen, wird empfohlen, der Namenskonvention der Klassenbibliothek zu folgen, wie von `ID_FILE_OPEN` veranschaulicht.  [Standardbefehle](../mfc/standard-commands.md) erläutert die Standardbefehle, die von der Klassenbibliothek definiert werden.  
  
## Siehe auch  
 [Benutzeroberflächenobjekte und Befehls\-IDs](../mfc/user-interface-objects-and-command-ids.md)
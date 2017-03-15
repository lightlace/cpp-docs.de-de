---
title: "When Do I Need to Call AtlAxWinTerm?"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "AtlAxWinTerm"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AtlAxWinTerm method"
ms.assetid: 0088d494-2d8d-45b4-b582-2af726bd6cbd
caps.latest.revision: 12
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# When Do I Need to Call AtlAxWinTerm?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[AtlAxWinTerm](../Topic/AtlAxWinTerm.md) hebt die **"AtlAxWin80"** Fensterklasse Registrierung auf.  Sie sollten diesen vorhandenen Host der Funktion schließlich aufrufen \(wenn Sie nicht mehr Hostfenster erstellen müssen, den\), Fenster zerstört wurden.  Wenn Sie diese Funktion aufrufen, wird die Fensterklasse automatisch Registrierung aufgehoben, wenn der Prozess beendet wird.  
  
## Siehe auch  
 [When Do I Need to Call AtlAxWinInit?](../atl/when-do-i-need-to-call-atlaxwininit-q.md)   
 [Fragen und Antworten zur Steuerelementkapselung](../atl/atl-control-containment-faq.md)
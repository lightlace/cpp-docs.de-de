---
title: "Benutzerdefinierte Handler"
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
  - "vc.mfc.handlers"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ON_MESSAGE-Makro"
  - "ON_REGISTERED_MESSAGE-Makro"
  - "Benutzerdefinierte Handler"
ms.assetid: 99478294-bef0-4ba7-a369-25a6abdcdb62
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Benutzerdefinierte Handler
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Einträge die folgende Zuordnung entsprechen den Funktionsprototypen.  
  
|Zuordnungseintrag|Funktionsprototyp|  
|-----------------------|-----------------------|  
|ON\_MESSAGE \( \<Meldung\>, \<memberFxn\> \)|afx\_msg LRESULT memberFxn \(WPARAM, LPARAM\);|  
|ON\_REGISTERED\_MESSAGE \( \<nMessageVariable\>, \<memberFxn\> \)|afx\_msg LRESULT memberFxn \(WPARAM, LPARAM\);|  
|ON\_THREAD\_MESSAGE \( \<Meldung\>, \<memberFxn\> \)|afx\_msg void memberFxn \(WPARAM, LPARAM\);|  
|ON\_REGISTERED\_THREAD\_MESSAGE \( \<nMessageVariable\>, \<memberFxn\> \)|afx\_msg void memberFxn \(WPARAM, LPARAM\);|  
  
## Siehe auch  
 [Meldungszuordnungen](../../mfc/reference/message-maps-mfc.md)   
 [Handler für WM\_\-Meldungen](../../mfc/reference/handlers-for-wm-messages.md)
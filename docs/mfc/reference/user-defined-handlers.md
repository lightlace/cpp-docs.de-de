---
title: "Benutzerdefinierte Handler | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
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
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
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
---
title: "Handler f&#252;r Benutzerschaltfl&#228;chen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ON_BN_HILITE"
  - "ON_BN_DOUBLECLICKED"
  - "ON_BN_CLICKED"
  - "ON_BN_PAINT"
  - "ON_BN_DISABLE"
  - "ON_BN_UNHILITE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ON_BN_CLICKED"
  - "ON_BN_DISABLE"
  - "ON_BN_DOUBLECLICKED"
  - "ON_BN_HILITE"
  - "ON_BN_PAINT"
  - "ON_BN_UNHILITE"
  - "Benutzerschaltflächen"
ms.assetid: 410ea968-478f-4806-b7b8-5d7c8dc2bf42
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# Handler f&#252;r Benutzerschaltfl&#228;chen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Einträge die folgende Zuordnung entsprechen den Funktionsprototypen.  
  
|Zuordnungseintrag|Funktionsprototyp|  
|-----------------------|-----------------------|  
|ON\_BN\_CLICKED \( \<ID\>, \<memberFxn\> \)|afx\_msg void memberFxn\( \);|  
|ON\_BN\_DISABLE \( \<ID\>, \<memberFxn\> \)|afx\_msg void memberFxn\( \);|  
|ON\_BN\_DOUBLECLICKED \( \<ID\>, \<memberFxn\> \)|afx\_msg void memberFxn\( \);|  
|ON\_BN\_HILITE \( \<ID\>, \<memberFxn\> \)|afx\_msg void memberFxn\( \);|  
|ON\_BN\_PAINT \( \<ID\>, \<memberFxn\> \)|afx\_msg void memberFxn\( \);|  
|ON\_BN\_UNHILITE \( \<ID\>, \<memberFxn\> \)|afx\_msg void memberFxn\( \);|  
  
## Siehe auch  
 [Meldungszuordnungen](../../mfc/reference/message-maps-mfc.md)
---
title: "Kombinationsfeldhandler"
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
  - "ON_CBN_KILLFOCUS"
  - "ON_CBN_ERRSPACE"
  - "ON_CBN_EDITCHANGE"
  - "ON_CBN_CLOSEUP"
  - "ON_CBN_DBLCLK"
  - "ON_CBN_EDITUPDATE"
  - "ON_CBN_DROPDOWN"
  - "ON_CBN_SELENDOK"
  - "ON_CBN_SELCHANGE"
  - "ON_CBN_SETFOCUS"
  - "ON_CBN_SELENDCANCEL"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Kombinationsfelder, Handler"
  - "ON_CBN_CLOSEUP"
  - "ON_CBN_DBLCLK"
  - "ON_CBN_DROPDOWN"
  - "ON_CBN_EDITCHANGE"
  - "ON_CBN_EDITCHANGE"
  - "ON_CBN_ERRSPACE"
  - "ON_CBN_KILLFOCUS"
  - "ON_CBN_SELCHANGE"
  - "ON_CBN_SELENDCANCEL"
  - "ON_CBN_SELENDOK"
  - "ON_CBN_SETFOCUS"
ms.assetid: 7f092412-01b7-4242-95ec-41ba506b9d71
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Kombinationsfeldhandler
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Einträge die folgende Zuordnung entsprechen den Funktionsprototypen.  
  
|Zuordnungseintrag|Funktionsprototyp|  
|-----------------------|-----------------------|  
|ON\_CBN\_CLOSEUP \( \<ID\>, \<memberFxn\> \)|afx\_msg void memberFxn\(\)|  
|ON\_CBN\_DBLCLK \( \<ID\>, \<memberFxn\> \)|afx\_msg void memberFxn\( \);|  
|ON\_CBN\_DROPDOWN \( \<ID\>, \<memberFxn\> \)|afx\_msg void memberFxn\( \);|  
|ON\_CBN\_EDITCHANGE \( \<ID\>, \<memberFxn\> \)|afx\_msg void memberFxn\( \);|  
|ON\_CBN\_EDITUPDATE \( \<ID\>, \<memberFxn\> \)|afx\_msg void memberFxn\( \);|  
|ON\_CBN\_ERRSPACE \( \<ID\>, \<memberFxn\> \)|afx\_msg void memberFxn\( \);|  
|ON\_CBN\_KILLFOCUS \( \<ID\>, \<memberFxn\> \)|afx\_msg void memberFxn\( \);|  
|ON\_CBN\_SELCHANGE \( \<ID\>, \<memberFxn\> \)|afx\_msg void memberFxn\( \);|  
|ON\_CBN\_SELENDCANCEL \( \<ID\>, \<memberFxn\> \)|afx\_msg void memberFxn\( \);|  
|ON\_CBN\_SELENDOK \( \<ID\>, \<memberFxn\> \)|afx\_msg void memberFxn\( \);|  
|ON\_CBN\_SETFOCUS \( \<ID\>, \<memberFxn\> \)|afx\_msg void memberFxn\( \);|  
  
## Siehe auch  
 [Meldungszuordnungen](../../mfc/reference/message-maps-mfc.md)
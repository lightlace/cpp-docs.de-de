---
title: "Einstiegspunkte f&#252;r Fensterprozeduren"
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
helpviewer_keywords: 
  - "Einstiegspunkte, Fensterprozeduren"
  - "MFC, Verwalten der Zustandsdaten"
  - "Zustandsverwaltung, Fensterprozeduren"
  - "Einstiegspunkte für Fensterprozeduren"
ms.assetid: a6b46a7f-6e42-45f2-9ae6-82e19fc57148
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Einstiegspunkte f&#252;r Fensterprozeduren
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

So MFC\-Fensterprozeduren schützen, statische Links eines Moduls mit einer besonderen Fensterprozedurimplementierung.  Die Bindung geschieht automatisch, wenn das Modul mit MFC verknüpft ist.  Diese Fensterprozedur verwendet das `AFX_MANAGE_STATE`\-Makro, um den effektiven Modulzustand ordnungsgemäß festzulegen, ruft er **AfxWndProc** auf, die wiederum zur `WindowProc`\-Memberfunktion entsprechenden `CWnd` abgeleiteten Objekts delegiert.  
  
## Siehe auch  
 [Verwalten der Statusdaten von MFC\-Modulen](../mfc/managing-the-state-data-of-mfc-modules.md)
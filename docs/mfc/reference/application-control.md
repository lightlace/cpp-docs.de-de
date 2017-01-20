---
title: "Anwendungssteuerelement"
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
  - "vc.mfc.macros"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Anwendungssteuerelement"
ms.assetid: c1f69f15-e0fe-4515-9f36-d63d31869deb
caps.latest.revision: 12
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Anwendungssteuerelement
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE benötigt erhebliches Steuerelement über Anwendungen und ihren Objekten.  Die OLE\-System\-DLLs müssen in der Lage sein zu starten und Anwendungen automatisch freigeben, koordinieren Sie die Produktion und Änderung von Objekten, z. B.  Die Funktionen in diesem Thema erfüllen diese Bedingungen.  Neben von der OLE\-System\-DLLs aufgerufen werden, müssen diese Funktionen über Anwendungen manchmal ebenfalls aufgerufen werden.  
  
### Anwendungssteuerung  
  
|||  
|-|-|  
|[AfxOleCanExitApp](../Topic/AfxOleCanExitApp.md)|Gibt an, ob die Anwendung beendet werden kann.|  
|[AfxOleGetMessageFilter](../Topic/AfxOleGetMessageFilter.md)|Ruft den aktuellen Meldungsfilter der Anwendung.|  
|[AfxOleGetUserCtrl](../Topic/AfxOleGetUserCtrl.md)|Ruft das aktuelle Benutzersteuerelementflag ab.|  
|[AfxOleSetUserCtrl](../Topic/AfxOleSetUserCtrl.md)|Setzt oder freie Räume das Benutzersteuerelementflag.|  
|[AfxOleLockApp](../Topic/AfxOleLockApp.md)|Inkrementiert die globale Anzahl des Framework der Anzahl von aktiven Objekten in einer Anwendung.|  
|[AfxOleUnlockApp](../Topic/AfxOleUnlockApp.md)|Dekrementiert die Anzahl des Framework der Anzahl von aktiven Objekten in einer Anwendung.|  
|[AfxOleRegisterServerClass](../Topic/AfxOleRegisterServerClass.md)|Registriert einen Server in der OLE\-Systemregistrierung.|  
|[AfxOleSetEditMenu](../Topic/AfxOleSetEditMenu.md)|Implementiert die Benutzeroberfläche für den Objektbefehl *Typname*.|  
  
## Siehe auch  
 [MFC\-Makros, globale Funktionen und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)
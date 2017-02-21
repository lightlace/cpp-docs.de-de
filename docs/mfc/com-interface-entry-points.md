---
title: "Einstiegspunkte f&#252;r COM-Schnittstellen | Microsoft Docs"
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
  - "COM-Schnittstellen, Einstiegspunkte"
  - "Einstiegspunkte, COM-Schnittstellen"
  - "MFC COM, Einstiegspunkte für COM-Schnittstellen"
  - "MFC, Verwalten der Zustandsdaten"
  - "OLE, Einstiegspunkte für Schnittstellen"
  - "Zustandsverwaltung, OLE/COM-Schnittstellen"
ms.assetid: 9e7421dc-0731-4748-9e1b-90acbaf26d77
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Einstiegspunkte f&#252;r COM-Schnittstellen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Für Memberfunktionen einer COM\-Schnittstelle, verwenden Sie das [METHOD\_PROLOGUE](../Topic/METHOD_PROLOGUE.md)\-Makro, um den ordnungsgemäßen globalen Zustand beizubehalten wenn Methoden aufgerufen einer exportierten Schnittstelle.  
  
 Normalerweise Memberfunktionen von Schnittstellen implementiert durch `CCmdTarget` abgeleitete Objekte bereits verwenden dieses Makro, um automatische Initialisierung des Zeigers `pThis` bereitzustellen.  Beispiel:  
  
 [!CODE [NVC_MFCConnectionPoints#5](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCConnectionPoints#5)]  
  
 Weitere Informationen finden Sie unter [Technischer Hinweis 38](../mfc/tn038-mfc-ole-iunknown-implementation.md) auf Implementierung MFC OLE\/ **IUnknown**.  
  
 Das `METHOD_PROLOGUE`\-Makro wird folgendermaßen definiert:  
  
 `#define METHOD_PROLOGUE(theClass, localClass) \`  
  
 `theClass* pThis = \`  
  
 `((theClass*)((BYTE*)this - offsetof(theClass, m_x##localClass))); \`  
  
 `AFX_MANAGE_STATE(pThis->m_pModuleState) \`  
  
 Der Teil des Makros, das bei der Verwaltung des globalen Zustand zu, ist:  
  
 `AFX_MANAGE_STATE( pThis->m_pModuleState )`  
  
 In diesem Ausdruck wird *m\_pModuleState*, wird angenommen Membervariable des enthaltenden Objekts sein.  Es wird durch die Basisklasse implementiert `CCmdTarget` und wird dem entsprechenden Wert von `COleObjectFactory` initialisiert, wenn das Objekt instanziiert wird.  
  
## Siehe auch  
 [Verwalten der Statusdaten von MFC\-Modulen](../mfc/managing-the-state-data-of-mfc-modules.md)
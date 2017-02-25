---
title: "Verbindungszuordnungen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros.maps"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Verbindungszuordnungen"
ms.assetid: 1f25a9bc-6d09-4614-99cf-dc38e8ddfa73
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# Verbindungszuordnungen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE\-Steuerelemente sind in der Lage, Schnittstellen andere Anwendungen verfügbar machen.  Diese Schnittstellen ermöglichen nur Zugriff von einem Container in dieses Steuerelement.  Wenn ein OLE\-Steuerelement auf externe Schnittstellen anderer OLE\-Objekte zugreifen möchte, muss ein Verbindungspunkt eingerichtet werden.  Dieser Verbindungspunkt ermöglicht es einem Steuerelement ausgehenden Zugriff auf externe Dispatchzuordnungen, wie Ereigniszuordnungen oder Benachrichtigungsfunktionen.  
  
 Die Microsoft Foundation Class\-Bibliothek stellt ein Programmiermodell, das Verbindungspunkte unterstützt.  In diesem Modell "Verbindungszuordnungen" werden verwendet, um Schnittstellen oder Verbindungspunkte für das OLE\-Steuerelement festzulegen.  Verbindungszuordnungen enthalten ein Makro für die einzelnen Verbindungspunkte.  Weitere Informationen über Verbindungszuordnungen, finden Sie unter [CConnectionPoint](../../mfc/reference/cconnectionpoint-class.md) die Klasse.  
  
 In der Regel unterstützt ein Steuerelement nur zwei Verbindungspunkte: ein für Ereignisse und eines für Eigenschaftenbenachrichtigungen.  Diese werden durch die `COleControl` \- Basisklasse implementiert und keine zusätzlichen durch den Steuerwriter benötigen.  Alle zusätzlichen Verbindungspunkte, die Sie in der Klasse implementieren möchten, müssen manuell hinzugefügt werden.  Um Verbindungszuordnungen Punkte und zu unterstützen, stellt MFC die folgenden Makros:  
  
### Verbindungszuordnungs\-Deklaration und Abgrenzung  
  
|||  
|-|-|  
|[BEGIN\_CONNECTION\_PART](../Topic/BEGIN_CONNECTION_PART.md)|Deklariert eine eingebettete Klasse, der einen zusätzlichen Verbindungspunkt implementiert \(muss in der Klassendeklaration verwendet werden\).|  
|[END\_CONNECTION\_PART](../Topic/END_CONNECTION_PART.md)|Beendet die Deklaration eines Verbindungspunktes \(muss in der Klassendeklaration verwendet werden\).|  
|[CONNECTION\_IID](../Topic/CONNECTION_IID.md)|Gibt die Schnittstellen\-ID des Verbindungspunkts des Steuerelements an.|  
|[DECLARE\_CONNECTION\_MAP](../Topic/DECLARE_CONNECTION_MAP.md)|Deklariert, dass eine Verbindungszuordnung in einer Klasse verwendet wird \(muss in der Klassendeklaration verwendet werden\).|  
|[BEGIN\_CONNECTION\_MAP](../Topic/BEGIN_CONNECTION_MAP.md)|Startet die Definition einer Verbindungszuordnung \(muss in die Klassenimplementierung verwendet werden\).|  
|[END\_CONNECTION\_MAP](../Topic/END_CONNECTION_MAP.md)|Beendet die Definition einer Verbindungszuordnung \(muss in die Klassenimplementierung verwendet werden\).|  
|[CONNECTION\_PART](../Topic/CONNECTION_PART.md)|Gibt ein Verbindungspunkt in der Verbindungszuordnung des Steuerelements an.|  
  
 Die folgenden Funktionen unterstützen eine Senke im Einrichten und eine Verbindung mithilfe der Verbindungspunkte trennen:  
  
### Initialisierung\/Beenden von Verbindungspunkten  
  
|||  
|-|-|  
|[AfxConnectionAdvise](../Topic/AfxConnectionAdvise.md)|Richtet eine Verbindung zwischen einer Quelle und eine Senke ein.|  
|[AfxConnectionUnadvise](../Topic/AfxConnectionUnadvise.md)|Teilt eine Verbindung zwischen einer Quelle und eine Senke.|  
  
## Siehe auch  
 [MFC\-Makros, globale Funktionen und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)
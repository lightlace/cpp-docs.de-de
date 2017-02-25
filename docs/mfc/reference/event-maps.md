---
title: "Ereigniszuordnungen | Microsoft Docs"
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
  - "Ereigniszuordnungen"
ms.assetid: 1ed53aee-bc53-43cd-834a-6fb935c0d29b
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# Ereigniszuordnungen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wenn ein Steuerelement seinen Container benachrichtigen möchte, dass Aktionen \(bestimmt vom Steuerelemententwickler\) geschehen ist \(z eine Tastatureingabe, Mausklick oder eine Änderung am Status des Steuerelements\) ruft sie eine Ereignisauslösungsfunktion auf.  Diese Funktion setzt den Steuerelementcontainer, dass einige wichtige Aktion beschreiben ist, indem das zusammengehörender Ereignis ausgelöst hat.  
  
 Die Microsoft Foundation Class\-Bibliothek stellt ein Programmiermodell, das für das Auslösen der Ereignisse optimiert ist.  In diesem Modell "Ereigniszuordnungen" werden verwendet, um festzulegen, die Funktionsfeuer das Ereignisse für ein bestimmtes Steuerelement.  Ereigniszuordnungen enthalten ein Makro für jedes Ereignis.  Beispielsweise könnte eine Ereigniszuordnung, die ein vordefiniertes Click\-Ereignis auslöst, wie folgt aus:  
  
 [!CODE [NVC_MFCAxCtl#16](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCAxCtl#16)]  
  
 Das **EVENT\_STOCK\_CLICK**\-Makro gibt an, dass das Steuerelement ein vordefiniertes Click\-Ereignis auslöst, jedes Mal, das es einem Mausklick erkennt.  Für Listen ausführlicheren anderer vordefinierter Ereignisse, finden Sie im Artikel [ActiveX\-Steuerelemente: Ereignisse](../../mfc/mfc-activex-controls-events.md).  Makros sind auch verfügbar, benutzerdefinierten Ereignissen anzugeben.  
  
 Obwohl Ereigniszuordnungsmakros wichtig sind, fügen Sie im Allgemeinen sie nicht direkt ein.  Dies liegt daran, dass das Eigenschaftenfenster Ereigniszuordnungseinträge automatisch in den Quelldateien erstellt, wenn Sie es verwenden, um Ereignisauslösungsfunktionen mit Ereignissen zu verknüpfen.  Immer wenn Sie einen Ereigniszuordnungseintrag bearbeiten oder hinzufügen möchten, können Sie das Eigenschaftenfenster verwenden.  
  
 Um Ereigniszuordnungen zu unterstützen, stellt MFC die folgenden Makros:  
  
### Ereigniszuordnungs\-Deklaration und Abgrenzung  
  
|||  
|-|-|  
|[DECLARE\_EVENT\_MAP](../Topic/DECLARE_EVENT_MAP.md)|Deklariert, dass eine Ereigniszuordnung in einer Klasse verwendet wird, um Ereignisse zu den Ereignisauslösungsfunktionen zuzuordnen \(muss in der Klassendeklaration verwendet werden\).|  
|[BEGIN\_EVENT\_MAP](../Topic/BEGIN_EVENT_MAP.md)|Startet die Definition eine Ereigniszuordnung \(muss in die Klassenimplementierung verwendet werden\).|  
|[END\_EVENT\_MAP](../Topic/END_EVENT_MAP.md)|Beendet die Definition eine Ereigniszuordnung \(muss in die Klassenimplementierung verwendet werden\).|  
  
### Ereignis\-Zuordnungs\-Makros  
  
|||  
|-|-|  
|[EVENT\_CUSTOM](../Topic/EVENT_CUSTOM.md)|Gibt an, welche Ereignisauslösungsfunktion das angegebene Ereignis auslöst.|  
|[EVENT\_CUSTOM\_ID](../Topic/EVENT_CUSTOM_ID.md)|Gibt an, welche Ereignisauslösungsfunktion das angegebene Ereignis auslöst, mit einer festgelegten Dispatch ID an|  
  
### Meldungs\-Zuordnungs\-Makros  
  
|||  
|-|-|  
|[ON\_OLEVERB](../Topic/ON_OLEVERB.md)|Gibt einen benutzerdefinierten Verb an, das vom OLE\-Steuerelement behandelt wird.|  
|[ON\_STDOLEVERB](../Topic/ON_STDOLEVERB.md)|Überschreibt eine Standardverbzuordnung des OLE\-Steuerelements.|  
  
## Siehe auch  
 [MFC\-Makros, globale Funktionen und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)
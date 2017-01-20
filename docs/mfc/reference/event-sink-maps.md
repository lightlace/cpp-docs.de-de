---
title: "Ereignissenkenzuordnungen"
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
  - "vc.mfc.macros.maps"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Ereignissenkenzuordnungen"
ms.assetid: a9757eb2-5f4a-45ec-a2cd-ce5eec85b16f
caps.latest.revision: 14
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Ereignissenkenzuordnungen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wenn ein eingebettetes OLE\-Steuerelement ein Ereignis ausgelöst wird, empfängt der Container des Steuerelements das Ereignis mithilfe eines Mechanismus, als "Ereignissenkenzuordnung," angegeben durch MFC.  Diese Ereignissenkenzuordnung legt Handlerfunktionen für jedes spezifische Ereignis sowie Parameter dieser Ereignisse.  Weitere Informationen über Ereignissenkenzuordnungen, finden Sie im Artikel [ActiveX\-Steuerelementcontainer](../../mfc/activex-control-containers.md).  
  
### Ereignissenkenzuordnungen  
  
|||  
|-|-|  
|[BEGIN\_EVENTSINK\_MAP](../Topic/BEGIN_EVENTSINK_MAP.md)|Startet die Definition einer Ereignissenkenzuordnung.|  
|[DECLARE\_EVENTSINK\_MAP](../Topic/DECLARE_EVENTSINK_MAP.md)|Deklariert eine Ereignissenkenzuordnung.|  
|[END\_EVENTSINK\_MAP](../Topic/END_EVENTSINK_MAP.md)|Beendet die Definition einer Ereignissenkenzuordnung.|  
|[ON\_EVENT](../Topic/ON_EVENT.md)|Definiert einen Ereignishandler für ein bestimmtes Ereignis.|  
|[ON\_EVENT\_RANGE](../Topic/ON_EVENT_RANGE.md)|Definiert einen Ereignishandler für ein bestimmtes Ereignis, das von einem Satz OLE\-Steuerelementen ausgelöst wird.|  
|[ON\_EVENT\_REFLECT](../Topic/ON_EVENT_REFLECT.md)|Empfangen der Ereignisse, die vom Steuerelement ausgelöst werden, bevor sie von den Steuerelementcontainer behandelt werden.|  
|[ON\_PROPNOTIFY](../Topic/ON_PROPNOTIFY.md)|Definiert einen Handler zum Behandeln von Eigenschaftenbenachrichtigungen von einem OLE\-Steuerelement.|  
|[ON\_PROPNOTIFY\_RANGE](../Topic/ON_PROPNOTIFY_RANGE.md)|Definiert einen Handler zum Behandeln von Eigenschaftenbenachrichtigungen aus einem Satz OLE\-Steuerelementen.|  
|[ON\_PROPNOTIFY\_REFLECT](../Topic/ON_PROPNOTIFY_REFLECT.md)|Empfangen der Eigenschaftenbenachrichtigungen, die das Steuerelement sendet, bevor sie von den Steuerelementcontainer behandelt werden.|  
  
## Siehe auch  
 [MFC\-Makros, globale Funktionen und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)
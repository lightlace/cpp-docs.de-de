---
title: "Meldungszuordnungsmakros (MFC)"
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
  - "vc.mfc.messages"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Demarkieren von Windows-Meldungen"
  - "Meldungszuordnungsmakros"
  - "Meldungszuordnungsbereiche"
  - "Meldungszuordnungsmakros"
  - "Meldungszuordnungen [C++], Deklaration und Demarkation"
  - "Meldungszuordnungen [C++], Makros"
  - "Bereiche, Meldungszuordnung"
  - "Windows-Nachrichten [C++], Deklaration"
ms.assetid: 531b15ce-32b5-4ca0-a849-bb519616c731
caps.latest.revision: 10
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Meldungszuordnungsmakros (MFC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Um Meldungszuordnungen zu unterstützen, stellt MFC die folgenden Makros:  
  
### Meldungszuordnungs\-Deklarations\- und Abgrenzungs\-Makros  
  
|||  
|-|-|  
|[DECLARE\_MESSAGE\_MAP](../Topic/DECLARE_MESSAGE_MAP.md)|Deklariert, dass eine Meldungszuordnung in einer Klasse verwendet wird, um Nachrichten auf Funktionen zuordnen \(muss in der Klassendeklaration verwendet werden\).|  
|[BEGIN\_MESSAGE\_MAP](../Topic/BEGIN_MESSAGE_MAP.md)|Startet die Definition eine Meldungszuordnung \(muss in die Klassenimplementierung verwendet werden\).|  
|[END\_MESSAGE\_MAP](../Topic/END_MESSAGE_MAP.md)|Beendet die Definition einer Meldungszuordnung \(muss in die Klassenimplementierung verwendet werden\).|  
  
### Meldung\-Zuordnungs\-Makros  
  
|||  
|-|-|  
|[ON\_COMMAND](../Topic/ON_COMMAND.md)|Gibt an, die bearbeitet eine angegebene Befehlsmeldung arbeiten.|  
|[ON\_CONTROL](../Topic/ON_CONTROL.md)|Gibt an, die bearbeitet eine angegebene Steuerelement\-Benachrichtigung arbeiten.|  
|[ON\_MESSAGE](../Topic/ON_MESSAGE.md)|Gibt an, die bearbeitet eine benutzerdefinierte Meldung arbeiten.|  
|[ON\_OLECMD](../Topic/ON_OLECMD.md)|Gibt an, die behandelt einen Menübefehl aus einem DocObject oder von seinem Container arbeiten.|  
|[ON\_REGISTERED\_MESSAGE](../Topic/ON_REGISTERED_MESSAGE.md)|Gibt an, die bearbeitet eine registrierte benutzerdefinierte Meldung arbeiten.|  
|[ON\_REGISTERED\_THREAD\_MESSAGE](../Topic/ON_REGISTERED_THREAD_MESSAGE.md)|Gibt an, die bearbeitet eine registrierte benutzerdefinierte Meldung funktionieren, wenn Sie eine `CWinThread`\-Klasse.|  
|[ON\_THREAD\_MESSAGE](../Topic/ON_THREAD_MESSAGE.md)|Gibt an, die bearbeitet eine benutzerdefinierte Meldung funktionieren, wenn Sie eine `CWinThread`\-Klasse.|  
|[ON\_UPDATE\_COMMAND\_UI](../Topic/ON_UPDATE_COMMAND_UI.md)|Gibt an, die bearbeitet eine angegebene Benutzeroberflächeupdate\-Befehlsmeldung arbeiten.|  
  
### Meldungszuordnungs\-Bereichs\-Makros  
  
|||  
|-|-|  
|[ON\_COMMAND\_RANGE](../Topic/ON_COMMAND_RANGE.md)|Gibt an, die behandelt den Bereich mit Befehls\-IDs arbeiten, die in den ersten zwei Parametern mit dem Makro angegeben werden.|  
|[ON\_UPDATE\_COMMAND\_UI\_RANGE](../Topic/ON_UPDATE_COMMAND_UI_RANGE.md)|Gibt an, welcher Aktualisierungshandler den Bereich mit Befehls\-IDs behandelt, die in den ersten zwei Parametern mit dem Makro angegeben werden.|  
|[ON\_CONTROL\_RANGE](../Topic/ON_CONTROL_RANGE.md)|Gibt an, die bearbeitet Benachrichtigungen vom Bereich mit Steuerelement\-IDs arbeiten, die im zweiten und dritten Parameter das Makro angegeben werden.  Der erste Parameter ist eine Steuerelement\-Benachrichtigung, wie **BN\_CLICKED**.|  
  
 Weitere Informationen über die Meldungszuordnungsdeklarations\-, Meldungszuordnungen finden und Abgrenzungsmakros und die MeldungZuordnungsmakros, [Meldungszuordnungstabellen](../../mfc/reference/message-maps-mfc.md) und [Nachrichtenverarbeitungs\- und Zuordnungs\-Themen](../../mfc/message-handling-and-mapping.md).  Weitere Informationen über Meldungszuordnungsbereiche, finden Sie unter [Handler für Meldungszuordnungs\-Bereiche](../../mfc/handlers-for-message-map-ranges.md).  
  
## Siehe auch  
 [Meldungszuordnungen](../../mfc/reference/message-maps-mfc.md)
---
title: "CJumpList Class"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "afxadv/CJumpList"
  - "CJumpList"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CJumpList class"
ms.assetid: d364d27e-f512-4b12-9872-c2a17c78ab1f
caps.latest.revision: 15
caps.handback.revision: "3"
ms.author: "mblome"
manager: "ghogen"
---
# CJumpList Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CJumpList` ist die Liste der Tastenkombinationen aufgedeckt, wenn Sie auf ein Symbol in der Taskleiste mit der rechten Maustaste auf.  
  
## Syntax  
  
```  
class CJumpList;  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CJumpList::CJumpList](../Topic/CJumpList::CJumpList.md)|Erstellt ein `CJumpList`\-Objekt.|  
|[CJumpList::~CJumpList](../Topic/CJumpList::~CJumpList.md)|Zerstört ein `CJumpList`\-Objekt.|  
  
|Name|Description|  
|----------|-----------------|  
|[CJumpList::AbortList](../Topic/CJumpList::AbortList.md)|Bricht eine ListeErstellung Transaktion ab, ohne zu bestätigen.|  
|[CJumpList::AddDestination](../Topic/CJumpList::AddDestination.md)|Überladen.  Fügt Ziel der Liste hinzu.|  
|[CJumpList::AddKnownCategory](../Topic/CJumpList::AddKnownCategory.md)|Fügt eine bekannte Kategorie der Liste an.|  
|[CJumpList::AddTask](../Topic/CJumpList::AddTask.md)|Überladen.  Fügt Elemente der kanonischen Aufgabenkategorie hinzu.|  
|[CJumpList::AddTasks](../Topic/CJumpList::AddTasks.md)|Fügt Elemente der kanonischen Aufgabenkategorie hinzu.|  
|[CJumpList::AddTaskSeparator](../Topic/CJumpList::AddTaskSeparator.md)|Fügt ein Trennzeichen zwischen Aufgaben hinzu.|  
|[CJumpList::ClearAll](../Topic/CJumpList::ClearAll.md)|Entfernt alle Aufgaben und Ziele, die der aktuellen Instanz von `CJumpList` bis jetzt hinzugefügt wurden.|  
|[CJumpList::ClearAllDestinations](../Topic/CJumpList::ClearAllDestinations.md)|Entfernt alle Ziele, die der aktuellen Instanz von `CJumpList` bis jetzt hinzugefügt wurden.|  
|[CJumpList::CommitList](../Topic/CJumpList::CommitList.md)|Beendet eine ListeErstellung Transaktion und führt die gemeldete Liste zum zugeordneten Speicher einen Commit \(die Registrierung in diesem Fall\).|  
|[CJumpList::GetDestinationList](../Topic/CJumpList::GetDestinationList.md)|Ruft einen Schnittstellenzeiger auf Zielliste ab.|  
|[CJumpList::GetMaxSlots](../Topic/CJumpList::GetMaxSlots.md)|Ruft die maximale Anzahl von Elementen, einschließlich Kategorienheader ab, die im aufrufenden Zielmenü der Anwendung anzeigen können.|  
|[CJumpList::GetRemovedItems](../Topic/CJumpList::GetRemovedItems.md)|EINGABETASTEarray Elemente, die entfernte Ziele darstellen.|  
|[CJumpList::InitializeList](../Topic/CJumpList::InitializeList.md)|Startet eine Transaktion ListeErstellung.|  
|[CJumpList::SetAppID](../Topic/CJumpList::SetAppID.md)|Legt die Anwendungs\-Benutzer\-Modell\-ID für die Liste fest, die erstellt wird.|  
  
## Vererbungshierarchie  
 [CJumpList](../../mfc/reference/cjumplist-class.md)  
  
## Anforderungen  
 **Header:**  afxadv.h  
  
## Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)
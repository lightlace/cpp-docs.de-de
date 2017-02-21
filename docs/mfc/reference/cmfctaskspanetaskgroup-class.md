---
title: "CMFCTasksPaneTaskGroup Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCTasksPaneTaskGroup"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCTasksPaneTaskGroup class"
ms.assetid: 2111640b-a46e-4b27-b033-29e88632b86a
caps.latest.revision: 33
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 35
---
# CMFCTasksPaneTaskGroup Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `CMFCTasksPaneTaskGroup`\-Klasse ist eine Hilfsprogrammklasse, die durch das [CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md)\-Steuerelement verwendet wird.  Objekte des Typs `CMFCTasksPaneTaskGroup` eine *Aufgabengruppe* darstellen.  Die Aufgabengruppe ist eine Liste von Elementen, die die Frameworkanzeigen in einem separaten Feld, das eine Schaltfläche zum Reduzieren verfügt.  Das Feld kann eine optionale Beschriftung \(Gruppennamen\) verfügen.  Wenn eine Gruppe reduziert ist, ist die Liste der Aufgaben nicht sichtbar.  
  
## Syntax  
  
```  
class CMFCTasksPaneTaskGroup : public CObject  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCTasksPaneTaskGroup::CMFCTasksPaneTaskGroup](../Topic/CMFCTasksPaneTaskGroup::CMFCTasksPaneTaskGroup.md)|Erstellt ein `CMFCTasksPaneTaskGroup`\-Objekt.|  
|`CMFCTasksPaneTaskGroup::~CMFCTasksPaneTaskGroup`|Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCTasksPaneTaskGroup::SetACCData](../Topic/CMFCTasksPaneTaskGroup::SetACCData.md)|Bestimmt die Barrierefreiheitsdaten für die aktuelle Aufgabengruppe.|  
  
### Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCTasksPaneTaskGroup::m\_bIsBottom](../Topic/CMFCTasksPaneTaskGroup::m_bIsBottom.md)|Bestimmt, ob die Aufgabengruppe am unteren Rand des Aufgabenbereichssteuerelements ausgerichtet ist.|  
|[CMFCTasksPaneTaskGroup::m\_bIsCollapsed](../Topic/CMFCTasksPaneTaskGroup::m_bIsCollapsed.md)|Bestimmt, ob die Aufgabengruppe reduziert wird.|  
|[CMFCTasksPaneTaskGroup::m\_bIsSpecial](../Topic/CMFCTasksPaneTaskGroup::m_bIsSpecial.md)|Bestimmt, ob die Aufgabengruppe *speziell* ist. Das Framework sind spezielle Beschriftungen in einer anderen Farbe an.|  
|[CMFCTasksPaneTaskGroup::m\_lstTasks](../Topic/CMFCTasksPaneTaskGroup::m_lstTasks.md)|Enthält die internen Liste von Aufgaben.|  
|[CMFCTasksPaneTaskGroup::m\_rect](../Topic/CMFCTasksPaneTaskGroup::m_rect.md)|Gibt das umschließende Rechteck der Gruppenbeschriftung an.|  
|[CMFCTasksPaneTaskGroup::m\_rectGroup](../Topic/CMFCTasksPaneTaskGroup::m_rectGroup.md)|Gibt das umschließende Rechteck der Gruppe an.|  
|[CMFCTasksPaneTaskGroup::m\_strName](../Topic/CMFCTasksPaneTaskGroup::m_strName.md)|Gibt den Namen der Gruppe an.|  
  
## Hinweise  
 Die folgende Abbildung zeigt eine erweiterte Aufgabengruppe an:  
  
 ![Aufgabengruppe, erweitert](../../mfc/reference/media/nexttaskgrpexpand.png "NextTaskGrpExpand")  
  
 Die folgende Abbildung zeigt eine reduzierte Aufgabengruppe an:  
  
 ![Reduzierte Aufgabengruppe](../../mfc/reference/media/nexttaskgrpcollapse.png "NextTaskGrpCollapse")  
  
 Die folgende Abbildung zeigt eine Aufgabengruppe ohne eine Beschriftung an:  
  
 ![Aufgabengruppe ohne Beschriftung](../../mfc/reference/media/nexttaskgrpnocapt.png "NextTaskGrpNoCapt")  
  
 Die folgende Abbildung zeigt zwei Aufgabengruppen an.  Die erste Aufgabengruppe wird als special markiert, indem das Flag auf `m_bIsSpecial``TRUE` festlegt, die zweite Aufgabengruppe nicht ausdrücklich ist.  Beachten Sie, wie die Beschriftung für die erste Aufgabengruppe dunkler ist, als die zweite Aufgabengruppe:  
  
 ![Spezielle Aufgabengruppe](../../mfc/reference/media/nexttaskgrpspecial.png "NextTaskGrpSpecial")  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md)  
  
## Anforderungen  
 **Header:** afxTasksPane.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCTasksPane Class](../../mfc/reference/cmfctaskspane-class.md)   
 [CMFCTasksPaneTask Class](../../mfc/reference/cmfctaskspanetask-class.md)   
 [CMFCOutlookBar\-Klasse](../../mfc/reference/cmfcoutlookbar-class.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)
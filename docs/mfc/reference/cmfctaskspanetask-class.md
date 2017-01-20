---
title: "CMFCTasksPaneTask Class"
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
  - "CMFCTasksPaneTask"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCTasksPaneTask class"
ms.assetid: c5a7513b-cd8f-4e2e-b16f-650e1fe30954
caps.latest.revision: 27
caps.handback.revision: "15"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCTasksPaneTask Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `CMFCTasksPaneTask`\-Klasse ist eine Hilfsprogrammklasse, die Aufgaben zum Aufgabenbereichssteuerelement \([CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md)\) darstellt.  Das Task\-Objekt stellt ein Element in der Aufgabengruppe dar \([CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md)\).  Jede Aufgabe kann einen Befehl verfügen, dem das Framework ausgeführt wird, wenn ein Benutzer auf der Aufgabe und einem Symbol klickt, das auf der linken Seite des Aufgabennamens angezeigt wird.  
  
## Syntax  
  
```  
class CMFCTasksPaneTask : public CObject  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCTasksPaneTask::CMFCTasksPaneTask](../Topic/CMFCTasksPaneTask::CMFCTasksPaneTask.md)|Erstellt und initialisiert ein `CMFCTasksPaneTask`\-Objekt.|  
|`CMFCTasksPaneTask::~CMFCTasksPaneTask`|Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCTasksPaneTask::SetACCData](../Topic/CMFCTasksPaneTask::SetACCData.md)|Bestimmt die Barrierefreiheitsdaten für die aktuelle Aufgabe.|  
  
### Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCTasksPaneTask::m\_bAutoDestroyWindow](../Topic/CMFCTasksPaneTask::m_bAutoDestroyWindow.md)|Bestimmt, ob das Aufgabenfenster automatisch zerstört wird.|  
|[CMFCTasksPaneTask::m\_bIsBold](../Topic/CMFCTasksPaneTask::m_bIsBold.md)|Bestimmt, ob das Framework eine tasks an fett formatiert.|  
|[CMFCTasksPaneTask::m\_dwUserData](../Topic/CMFCTasksPaneTask::m_dwUserData.md)|Enthält benutzerdefinierte Daten, die das Framework mit der Aufgabe zugeordnet wird.  Position auf Null, wenn die Aufgabe keine Daten zugeordnet sind.|  
|[CMFCTasksPaneTask::m\_hwndTask](../Topic/CMFCTasksPaneTask::m_hwndTask.md)|Ein Handle für Aufgabenfenster.|  
|[CMFCTasksPaneTask::m\_nIcon](../Topic/CMFCTasksPaneTask::m_nIcon.md)|Der Index des in der Bildliste Bilder, das das Framework neben der Aufgabe anzeigt.|  
|[CMFCTasksPaneTask::m\_nWindowHeight](../Topic/CMFCTasksPaneTask::m_nWindowHeight.md)|Die Höhe des Aufgabenfensters.  Wenn die Aufgabe kein Aufgabenfenster verfügt, ist dieser Wert Null.|  
|[CMFCTasksPaneTask::m\_pGroup](../Topic/CMFCTasksPaneTask::m_pGroup.md)|Ein Zeiger auf `CMFCTasksPaneTaskGroup`, dass diese Aufgabe gehört.|  
|[CMFCTasksPaneTask::m\_rect](../Topic/CMFCTasksPaneTask::m_rect.md)|Gibt das umschließende Rechteck der Aufgabe an.|  
|[CMFCTasksPaneTask::m\_strName](../Topic/CMFCTasksPaneTask::m_strName.md)|Der Name der Aufgabe.|  
|[CMFCTasksPaneTask::m\_uiCommandID](../Topic/CMFCTasksPaneTask::m_uiCommandID.md)|Gibt die Befehls\-ID des Befehls an, das vom Framework ausgeführt wird, wenn der Benutzer auf die Aufgabe klickt.  Wenn dieser Wert keine gültige Befehls\-ID ist, wird die Aufgabe als einfache Bezeichnung behandelt.|  
  
## Hinweise  
 Die folgende Abbildung zeigt eine Aufgabengruppe an, die drei Aufgaben enthält:  
  
 ![Aufgabengruppe, erweitert](../../mfc/reference/media/nexttaskgrpexpand.png "NextTaskGrpExpand")  
  
> [!NOTE]
>  Wenn eine Aufgabe keine gültige Befehls\-ID verfügt, wird sie als einfache Bezeichnung behandelt.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCTasksPaneTask](../../mfc/reference/cmfctaskspanetask-class.md)  
  
## Anforderungen  
 **Header:** afxTasksPane.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)
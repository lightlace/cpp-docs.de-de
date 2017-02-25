---
title: "CRectTracker Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CRectTracker"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRectTracker class"
  - "displaying items"
  - "resizing items"
ms.assetid: 99caa7f2-3c0d-4a42-bbee-e5d1d342d4ee
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CRectTracker Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ermöglicht ein in verschiedenen Weisen angezeigt, verschoben, und Größe geändert Element.  
  
## Syntax  
  
```  
  
class CRectTracker  
  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CRectTracker::CRectTracker](../Topic/CRectTracker::CRectTracker.md)|Erstellt ein `CRectTracker`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CRectTracker::AdjustRect](../Topic/CRectTracker::AdjustRect.md)|Aufgerufen, wenn das Rechteck angepasst wird.|  
|[CRectTracker::Draw](../Topic/CRectTracker::Draw.md)|Gibt das Rechteck.|  
|[CRectTracker::DrawTrackerRect](../Topic/CRectTracker::DrawTrackerRect.md)|Aufgerufen, wenn der Kontext eines `CRectTracker`\-Objekts gezeichnet wird.|  
|[CRectTracker::GetHandleMask](../Topic/CRectTracker::GetHandleMask.md)|Aufgerufen, um die Maske der Ziehpunkte `CRectTracker` eines Elements abzurufen.|  
|[CRectTracker::GetTrueRect](../Topic/CRectTracker::GetTrueRect.md)|EINGABETASTE Breite und Höhe des Rechtecks, einschließlich Ziehpunkte.|  
|[CRectTracker::HitTest](../Topic/CRectTracker::HitTest.md)|Gibt die aktuelle Position des Cursors zurück, der dem `CRectTracker`\-Objekt verknüpft ist.|  
|[CRectTracker::NormalizeHit](../Topic/CRectTracker::NormalizeHit.md)|Normalisiert einen Treffertestcode.|  
|[CRectTracker::OnChangedRect](../Topic/CRectTracker::OnChangedRect.md)|Aufgerufen, wenn das Rechteck Größe geändert wurde oder verschoben wurde.|  
|[CRectTracker::SetCursor](../Topic/CRectTracker::SetCursor.md)|Legt den Cursor, abhängig von seiner Position über dem Rechteck fest.|  
|[CRectTracker::Track](../Topic/CRectTracker::Track.md)|Ermöglicht es dem Benutzer, die das Rechteck zu bearbeiten.|  
|[CRectTracker::TrackRubberBand](../Topic/CRectTracker::TrackRubberBand.md)|Gesteht dem Benutzer auf "GummiBand" die Auswahl auf.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CRectTracker::m\_nHandleSize](../Topic/CRectTracker::m_nHandleSize.md)|Bestimmt Größe von Ziehpunkten.|  
|[CRectTracker::m\_nStyle](../Topic/CRectTracker::m_nStyle.md)|Aktuelle Stile des Protokollierers.|  
|[CRectTracker::m\_rect](../Topic/CRectTracker::m_rect.md)|Aktuelle Position \(in Pixel\) des Rechtecks.|  
|[CRectTracker::m\_sizeMin](../Topic/CRectTracker::m_sizeMin.md)|Bestimmt Rechteckbreite minimale und liegen.|  
  
## Hinweise  
 `CRectTracker` hat keine Basisklasse.  
  
 Obwohl die `CRectTracker`\-Klasse gezeichnet wird, um dem Benutzer zu ermöglichen, mit OLE\-Elementen zu interagieren, indem eine grafische Schnittstelle verwendet, wird seine Verwendung nicht zu OLE\-aktivierten Anwendungen beschränkt.  Es kann verwendet werden überall einer solchen Benutzeroberfläche ist erforderlich.  
  
 `CRectTracker` Rahmen können ausgefüllte oder gepunktete Zeilen sein.  Das Element kann einen schraffierten Rahmen angegeben werden oder mit einer Schraffur angeordnet sind, um unterschiedliche Zustände des Elements anzugeben.  Sie können acht Ziehpunkte entweder auf dem äußeren oder inneren des Elements anordnen.  \(Eine Erläuterung der Ziehpunkte, finden Sie unter [GetHandleMask](../Topic/CRectTracker::GetHandleMask.md).\) Schließlich `CRectTracker` ermöglicht Ihnen, die Ausrichtung eines Elements während der Größenanpassung zu ändern.  
  
 Um `CRectTracker` zu verwenden, erstellen Sie ein `CRectTracker`\-Objekt und geben Sie an die Zustände werden initialisiert anzeigen.  Sie können diese Schnittstelle dann verwenden, um das visuelle Benutzerfeedback auf dem aktuellen Status des OLE\-Elements zu geben, das mit dem `CRectTracker`\-Objekt zugeordnet ist.  
  
 Weitere Informationen zur Verwendung von `CRectTracker`, finden Sie im Artikel [Protokollierer](../../mfc/trackers.md).  
  
## Vererbungshierarchie  
 `CRectTracker`  
  
## Anforderungen  
 **Header:**  afxext.h  
  
## Siehe auch  
 [Die TRACKER\-Beispielanwendung MFC Sampling](../../top/visual-cpp-samples.md)   
 [MFC\-Beispiel DRAWCLI](../../top/visual-cpp-samples.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleResizeBar Class](../../mfc/reference/coleresizebar-class.md)   
 [CRect Class](../../atl-mfc-shared/reference/crect-class.md)   
 [CRectTracker::GetHandleMask](../Topic/CRectTracker::GetHandleMask.md)
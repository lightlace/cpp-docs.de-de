---
title: "Gummibandtechnik und Ziehpunkte | Microsoft Docs"
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
  - "CRectTracker-Klasse, Implementieren von Trackern"
  - "OLE-Objekte, Auswählen"
  - "Gummibandtechnik"
  - "Tracker"
  - "WM_LBUTTONDOWN"
ms.assetid: 0d0fa64c-6418-4baf-ab7f-2d16ca039230
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Gummibandtechnik und Ziehpunkte
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine weitere Funktion, die mit Protokollierern angegeben wird, ist die "GummiBand" Auswahl, die einen Benutzer zu den ausgewählten mehreren OLE\-Elementen können, indem Sie ein Größenanpassungsrechteck die ausgewählt werden, Elemente ziehen.  Wenn der Benutzer die linke Maustaste loslässt, werden Elemente innerhalb des Bereichs, den der Benutzer ausgewählt ist, ausgewählt und können vom Benutzer bearbeitet werden.  Ein Beispiel hierfür möglicherweise die Auswahl in einer anderer Containeranwendung.  
  
 Das Implementieren dieser Funktion erfordert einen zusätzlichen Code in `WM_LBUTTONDOWN`\-Handlerfunktion der Anwendung.  
  
 Im folgenden Codebeispiel wird GummiBand\-Auswahl und zusätzliche Funktionen.  
  
 [!CODE [NVC_MFCOClient#6](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCOClient#6)]  
  
 Wenn Sie umkehrbare Ausrichtung des Protokollierers während des Dehnlinien\-Verfahrens ermöglichen möchten, können Sie [CRectTracker::TrackRubberBand](../Topic/CRectTracker::TrackRubberBand.md) mit dem dritten Parameter aufrufen, die auf **TRUE** festgelegt wird.  Beachten Sie, dass das Warten der umkehrbaren Ausrichtung manchmal [CRectTracker::m\_rect](../Topic/CRectTracker::m_rect.md) bewirkt, werden rückgängig gemacht.  Dies kann durch einen Aufruf von [CRect::NormalizeRect](../Topic/CRect::NormalizeRect.md) behoben werden.  
  
 Weitere Informationen finden Sie unter [Container\-Client\-Elemente](../mfc/containers-client-items.md) und [Anpassen von Drag & Drop](../mfc/drag-and-drop-customizing.md).  
  
## Siehe auch  
 [Tracker: Implementieren von Trackern in einer OLE\-Anwendung](../mfc/trackers-implementing-trackers-in-your-ole-application.md)   
 [CRectTracker Class](../mfc/reference/crecttracker-class.md)
---
title: "Tracker | Microsoft Docs"
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
  - "Anwendungen [OLE], Tracker"
  - "CDC-Klasse, Tracker"
  - "CRectTracker-Klasse, Implementieren von Trackern"
  - "OLE-Anwendungen [C++], Tracker"
  - "OLE-Container, Tracker"
  - "OLE-Serveranwendungen, Tracker"
  - "Tracker"
  - "Nachverfolgen von OLE-Elementen"
ms.assetid: dcd09399-6637-4621-80e5-d12670429787
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Tracker
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die [CRectTracker](../mfc/reference/crecttracker-class.md)\-Klasse stellt eine Benutzeroberfläche zwischen rechteckigen Elemente in der Anwendung und der Benutzer, indem er eine Vielzahl der Anzeige bereitstellt, formatiert.  Diese Formate umfassen den reinen, oder die schraffiert gestrichelten Rahmen; eine Schraffur, die das Element enthält; und Ziehpunkte, die im äußeren oder das innerhalb von einem Rahmen ermittelt werden können.  Protokollierer sind in Verbindung mit OLE\-Elementen die d. h Objekten oft verwendet, die von `COleClientItem` abgeleitet werden.  Die Protokolliererrechtecke geben visuelle Hinweise auf den aktuellen Status des Elements.  
  
 Das [OCLIENT](../top/visual-cpp-samples.md) MFC\-OLE wird eine allgemeine Schnittstelle mithilfe der Protokollierer\- und OLE\-Clientelemente vom Bereich einer Containeranwendung.  Eine Beispiel der verschiedenen Formatvorlagen und der Fähigkeiten eines Protokollierers \- Objekts, finden Sie das Beispiel [Die TRACKER\-Beispielanwendung](../top/visual-cpp-samples.md) allgemeine MFC.  
  
 Weitere Informationen zum Implementieren von Protokollierern in der OLE\-Anwendung, finden Sie unter [Protokollierer: Implementieren von Protokollierern in der OLE\-Anwendung](../mfc/trackers-implementing-trackers-in-your-ole-application.md)  
  
## Siehe auch  
 [OLE](../mfc/ole-in-mfc.md)   
 [COleClientItem Class](../mfc/reference/coleclientitem-class.md)
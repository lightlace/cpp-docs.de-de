---
title: Rahmenstile | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- trackers [MFC]
- OLE applications [MFC], trackers
- applications [OLE], trackers
- tracking OLE items [MFC]
- OLE containers [MFC], trackers
- CDC class [MFC], trackers
- CRectTracker class [MFC], implementing trackers
- OLE server applications [MFC], trackers
ms.assetid: dcd09399-6637-4621-80e5-d12670429787
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 29e4d3c556a5f7b6b3aed5daa0285ea6c2c15447
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="trackers"></a>Tracker
Die [CRectTracker](../mfc/reference/crecttracker-class.md) Klasse bietet eine Benutzeroberfläche zwischen rechteckigen Elemente in Ihrer Anwendung und Ihre Benutzer mit einer Vielzahl von Formaten anzeigen. Diese Formate umfassen durchgehende, schraffierten oder gestrichelte Rahmen. eine Schraffur, die das Element behandelt; und Ziehpunkte, die sich außerhalb oder innerhalb eines Rahmens sein können. Rahmenstile werden häufig in Verbindung mit der OLE-Elementen verwendet, d. h. Objekte abgeleitet `COleClientItem`. Rechtecke Tracker geben visuellen Hinweise auf den aktuellen Status des Elements an.  
  
 Das MFC-OLE-Beispiel [OCLIENT](../visual-cpp-samples.md) zeigt eine allgemeine Schnittstelle mithilfe von Trackern und OLE-Clientelemente vom Standpunkt der Steuerelementcontainer-Anwendung. Eine Demonstration der verschiedenen Formaten und Fähigkeiten eines Objekts Tracker finden Sie in der allgemeinen MFC-Beispiel [TRACKER](../visual-cpp-samples.md).  
  
 Weitere Informationen zum Implementieren von Trackern in der OLE-Anwendung finden Sie unter [Tracker: Implementieren von Trackern in einer OLE-Anwendung](../mfc/trackers-implementing-trackers-in-your-ole-application.md)  
  
## <a name="see-also"></a>Siehe auch  
 [OLE](../mfc/ole-in-mfc.md)   
 [COleClientItem-Klasse](../mfc/reference/coleclientitem-class.md)

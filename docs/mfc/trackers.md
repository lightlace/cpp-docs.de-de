---
title: Rahmenstile | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6f0a0cc52e3a5150702af4acd293def38df758fd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="trackers"></a>Tracker
Die [CRectTracker](../mfc/reference/crecttracker-class.md) Klasse bietet eine Benutzeroberfläche zwischen rechteckigen Elemente in Ihrer Anwendung und Ihre Benutzer mit einer Vielzahl von Formaten anzeigen. Diese Formate umfassen durchgehende, schraffierten oder gestrichelte Rahmen. eine Schraffur, die das Element behandelt; und Ziehpunkte, die sich außerhalb oder innerhalb eines Rahmens sein können. Rahmenstile werden häufig in Verbindung mit der OLE-Elementen verwendet, d. h. Objekte abgeleitet `COleClientItem`. Rechtecke Tracker geben visuellen Hinweise auf den aktuellen Status des Elements an.  
  
 Das MFC-OLE-Beispiel [OCLIENT](../visual-cpp-samples.md) zeigt eine allgemeine Schnittstelle mithilfe von Trackern und OLE-Clientelemente vom Standpunkt der Steuerelementcontainer-Anwendung. Eine Demonstration der verschiedenen Formaten und Fähigkeiten eines Objekts Tracker finden Sie in der allgemeinen MFC-Beispiel [TRACKER](../visual-cpp-samples.md).  
  
 Weitere Informationen zum Implementieren von Trackern in der OLE-Anwendung finden Sie unter [Tracker: Implementieren von Trackern in einer OLE-Anwendung](../mfc/trackers-implementing-trackers-in-your-ole-application.md)  
  
## <a name="see-also"></a>Siehe auch  
 [OLE](../mfc/ole-in-mfc.md)   
 [COleClientItem-Klasse](../mfc/reference/coleclientitem-class.md)

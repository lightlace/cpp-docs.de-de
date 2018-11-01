---
title: Tracker
ms.date: 11/04/2016
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
ms.openlocfilehash: 74e70f989d3803b11f05150f9b55c6dfe79ed876
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50481951"
---
# <a name="trackers"></a>Tracker

Die [CRectTracker](../mfc/reference/crecttracker-class.md) Klasse bietet eine Benutzeroberfläche zwischen den rechteckigen Elementen in Ihrer Anwendung und Ihre Benutzer mit einer Vielzahl von Formatvorlagen anzeigen. Diese Formate sind durchgehende, schraffierten oder gestrichelte Rahmen: ein schraffierten Muster an, die das Element abdeckt. und Ziehpunkte, die sich außerhalb oder innerhalb eines Rahmens werden können. Tracker häufig in Verbindung mit der OLE-Elementen verwendet werden, d. h. abgeleitete Objekte aus `COleClientItem`. Rechtecke Tracker bieten visuelle Hinweise auf den aktuellen Status des Elements an.

Das MFC-OLE-Beispiel [OCLIENT](../visual-cpp-samples.md) wird veranschaulicht, eine gemeinsame Schnittstelle, die mithilfe von Trackern und OLE-Client-Elemente vom Standpunkt einer Container-Anwendung. Veranschaulicht die verschiedenen Formatvorlagen und Fähigkeiten eines Objekts Tracker finden Sie im allgemeinen MFC-Beispiel [TRACKER](../visual-cpp-samples.md).

Weitere Informationen zum Implementieren von Trackern in einer OLE-Anwendung, finden Sie unter [Tracker: Implementieren von Trackern in einer OLE-Anwendung](../mfc/trackers-implementing-trackers-in-your-ole-application.md)

## <a name="see-also"></a>Siehe auch

[OLE](../mfc/ole-in-mfc.md)<br/>
[COleClientItem-Klasse](../mfc/reference/coleclientitem-class.md)

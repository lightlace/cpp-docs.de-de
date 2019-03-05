---
title: OLE-bezogene Klassen
ms.date: 11/04/2016
f1_keywords:
- vc.classes.ole
helpviewer_keywords:
- ActiveX classes [MFC]
- OLE classes [MFC]
- OLE [MFC], classes
ms.assetid: 2135cf54-1d9d-4e0e-91b4-943b3440effa
ms.openlocfilehash: 7d58072d133b9348558804b848ecfda4497931e1
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57263766"
---
# <a name="ole-related-classes"></a>OLE-bezogene Klassen

Diese Klassen bieten eine Reihe von anderen Diensten, im Bereich von Ausnahmen in eine Datei ein- und Ausgabe.

[COleObjectFactory](../mfc/reference/coleobjectfactory-class.md)<br/>
Zum Erstellen von Elementen, die beim Anfordern von anderen Containern verwendet. Diese Klasse dient als Basisklasse für spezifische Typen von Factorys, einschließlich `COleTemplateServer`.

[COleMessageFilter](../mfc/reference/colemessagefilter-class.md)<br/>
Zum Verwalten von Parallelität mit OLE Lightweight Remote Prozedur aufrufen (LRPC) verwendet.

[COleStreamFile](../mfc/reference/colestreamfile-class.md)<br/>
Die COM verwendet `IStream` -Schnittstelle zur Bereitstellung `CFile` Zugriff auf Dateien zusammengesetzte. Diese Klasse (abgeleitet von `CFile`) ermöglicht die Serialisierung von MFC-OLE structured Storage verwenden.

[CRectTracker](../mfc/reference/crecttracker-class.md)<br/>
Wird verwendet, um verschieben, Ändern der Größe und Neuorientierung des direktes Elemente zu ermöglichen.

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../mfc/class-library-overview.md)

---
title: OLE-bezogene Klassen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.ole
dev_langs:
- C++
helpviewer_keywords:
- ActiveX classes [MFC]
- OLE classes [MFC]
- OLE [MFC], classes
ms.assetid: 2135cf54-1d9d-4e0e-91b4-943b3440effa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f43dadaa4aaefa677106710d1adbcdf0e60be59d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46411312"
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


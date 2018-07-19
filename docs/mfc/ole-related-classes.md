---
title: OLE-bezogene Klassen | Microsoft Docs
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
ms.openlocfilehash: baa4ec3de21ce91e0d8723ad0e4debb39a26b3cf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33348514"
---
# <a name="ole-related-classes"></a>OLE-bezogene Klassen
Diese Klassen bieten eine Reihe verschiedener Dienste, die im Bereich von Ausnahmen für die Eingabe und Ausgabe der Datei.  
  
 [COleObjectFactory](../mfc/reference/coleobjectfactory-class.md)  
 Dient zum Erstellen von Elementen, wenn es von anderen Containern angefordert. Diese Klasse dient als Basisklasse für spezifische Typen von Factorys, einschließlich `COleTemplateServer`.  
  
 [COleMessageFilter](../mfc/reference/colemessagefilter-class.md)  
 Zum Verwalten von Parallelität mit OLE Lightweight Remote Procedure Aufrufe (LRPC) verwendet.  
  
 [COleStreamFile](../mfc/reference/colestreamfile-class.md)  
 Die COM verwendet `IStream` Schnittstelle `CFile` Zugriff auf Dateien, zusammengesetzte. Diese Klasse (abgeleitet von `CFile`) ermöglicht die MFC-Serialisierung OLE structured Storage verwenden.  
  
 [CRectTracker](../mfc/reference/crecttracker-class.md)  
 Verwendet, um das Verschieben, ihre Größe ändern und Neuorientierung direktes Elemente ermöglichen.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../mfc/class-library-overview.md)


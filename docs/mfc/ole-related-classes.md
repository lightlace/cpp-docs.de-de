---
title: OLE-bezogene Klassen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.classes.ole
dev_langs: C++
helpviewer_keywords:
- ActiveX classes [MFC]
- OLE classes [MFC]
- OLE [MFC], classes
ms.assetid: 2135cf54-1d9d-4e0e-91b4-943b3440effa
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4cb40e237eb6197dfe7e0cf944f12d25ca0e28e4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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


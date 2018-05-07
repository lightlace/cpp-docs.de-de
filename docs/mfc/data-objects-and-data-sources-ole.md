---
title: Datenobjekte und Datenquellen (OLE) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- data objects [MFC], definition
- data transfer [MFC]
- OLE [MFC], data transfer
- data sources [MFC], definition
- data transfer [MFC], definition
- OLE [MFC], data objects
- OLE [MFC], data sources
ms.assetid: 8f68eed8-0ce8-4489-a4cc-f95554f89090
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 766148494c6b8693f8d9e65f27e157b58d8e8689
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="data-objects-and-data-sources-ole"></a>Datenobjekte und Datenquellen (OLE)
Beim Ausführen einer Datenübertragung, entweder über die Zwischenablage oder Drag & Drop, enthalten die Daten an eine Quelle und ein Ziel. Eine Anwendung gibt die Daten für das Kopieren und eine andere Anwendung akzeptiert das Element zum Einfügen. Jede Seite der Übertragung muss zum Durchführen verschiedener Vorgänge auf den gleichen Daten für die Übertragung erfolgreich ausgeführt werden kann. Die Microsoft Foundation Class (MFC)-Bibliothek bietet zwei Klassen, die beiden Seiten des diese Übertragung darstellen:  
  
-   Datenquellen (wie von implementiert `COleDataSource` Objekte) die Quellseite der Datenübertragung darstellen. Sie werden von der quellanwendung erstellt, wenn Daten in die Zwischenablage kopiert werden soll, oder wenn Daten für einen Drag-and-Drop-Vorgang bereitgestellt werden.  
  
-   Datenobjekte (wie von implementiert `COleDataObject` Objekte) die Zielseite der Datenübertragung darstellen. Sie werden erstellt, wenn die Zielanwendung enthält Daten, die gelöscht, hinein oder wenn es zum Einfügen aus der Zwischenablage eines Vorgangs angefordert wird.  
  
 Die folgenden Artikel wird erläutert, wie Datenobjekte und Datenquellen in Ihren Anwendungen verwenden. Diese Informationen gelten für Container und Server-Anwendungen, da beide nach aufgerufen werden können, kopieren und Einfügen von Daten.  
  
-   [Datenobjekte und Datenquellen: Erstellen und Zerstören](../mfc/data-objects-and-data-sources-creation-and-destruction.md)  
  
-   [Datenobjekte und Datenquellen: Bearbeitung](../mfc/data-objects-and-data-sources-manipulation.md)  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Drag & Drop](../mfc/drag-and-drop-ole.md)  
  
 [Zwischenablage](../mfc/clipboard.md)  
  
## <a name="see-also"></a>Siehe auch  
 [OLE](../mfc/ole-in-mfc.md)   
 [COleDataObject-Klasse](../mfc/reference/coledataobject-class.md)   
 [COleDataSource-Klasse](../mfc/reference/coledatasource-class.md)

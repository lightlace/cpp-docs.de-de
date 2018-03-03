---
title: Datenobjekte und Datenquellen (OLE) | Microsoft Docs
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
- data objects [MFC], definition
- data transfer [MFC]
- OLE [MFC], data transfer
- data sources [MFC], definition
- data transfer [MFC], definition
- OLE [MFC], data objects
- OLE [MFC], data sources
ms.assetid: 8f68eed8-0ce8-4489-a4cc-f95554f89090
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 04619ee7851d2e2d6ad569583dfbb2e619d37026
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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

---
title: Dateien in MFC | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- serialization [MFC], MFC files
- I/O [MFC], MFC classes
- files [MFC], MFC
- files [MFC], serialization
- binary access, binary file operations in MFC
- file I/O classes [MFC]
- I/O [MFC]
- persistence [MFC]
- MFC, file operations
- files [MFC], manipulating
- binary access [MFC]
ms.assetid: ae25e2c5-2859-4679-ab97-438824e93ce1
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4d2cd6344f11a9c32ade0fc3241225a8763c18b9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="files-in-mfc"></a>Dateien in MFC
In der Microsoft Foundation Class Library (MFC)-Klasse [CFile](../mfc/reference/cfile-class.md) normale Datei-e/a-Vorgänge abwickelt. Diese Artikelreihe erläutert, wie zu öffnen und schließen Sie Dateien als auch lesen und Schreiben von Daten zu diesen Dateien. Darüber hinaus werden die Status Dateioperationen erläutert. Eine Beschreibung, wie die Serialisierung objektbasierten Funktionen von MFC als eine alternative Möglichkeit zum Lesen und Schreiben von Daten in Dateien zu verwenden, finden Sie im Artikel [Serialisierung](../mfc/serialization-in-mfc.md).  
  
> [!NOTE]
>  Bei Verwendung von MFC **CDocument** -Objekten, das Framework wickelt einen großen Teil der Arbeit für die Serialisierung für Sie. Insbesondere das Framework erstellt und verwendet die `CFile` Objekt. Sie müssen nur für das Schreiben von Code in der Überschreibung der der `Serialize` Memberfunktion der Klasse **CDocument**.  
  
 Die `CFile` Klasse stellt eine Schnittstelle für allgemeine binäre Dateivorgänge. Die `CStdioFile` und `CMemFile` von abgeleiteten Klassen `CFile` und `CSharedFile` abgeleitete Klasse `CMemFile` spezialisierter "Dateidienste" angeben.  
  
 Weitere Informationen zu alternativen für MFC-Dateibehandlung finden Sie unter [Dateibehandlung](../c-runtime-library/file-handling.md) in der *Run-Time Library Reference*.  
  
 Informationen zu abgeleiteten `CFile` Klassen, finden Sie unter der [MFC-Hierarchiediagramm](../mfc/hierarchy-chart.md).  
  
## <a name="what-do-you-want-to-do"></a>Was möchten Sie tun  
 *CFile verwenden*  
  
-   [Öffnet eine Datei mit CFile](../mfc/opening-files.md)  
  
-   [Lesen Sie und Schreiben Sie eine Datei mit CFile](../mfc/reading-and-writing-files.md)  
  
-   [Schließen Sie eine Datei mit CFile](../mfc/closing-files.md)  
  
-   [Status der Access-Datei mit CFile](../mfc/accessing-file-status.md)  
  
 *Verwenden von MFC-Serialisierung (Objektpersistenz)*  
  
-   [Erstellen einer serialisierbaren Klasse](../mfc/serialization-making-a-serializable-class.md)  
  
-   [Serialisiert ein Objekt über ein CArchive-Objekt](../mfc/serialization-serializing-an-object.md)  
  
-   [Erstellen eines CArchive-Objekts](../mfc/two-ways-to-create-a-carchive-object.md)  
  
-   [Verwenden von CArchive <\< und >> Operatoren](../mfc/using-the-carchive-output-and-input-operators.md)  
  
-   [Speichern Sie und Laden Sie eines CObject und CObject abgeleitete Objekte per Archiv](../mfc/storing-and-loading-cobjects-via-an-archive.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Konzepte](../mfc/mfc-concepts.md)   
 [Allgemeine MFC-Themen](../mfc/general-mfc-topics.md)   
 [CArchive-Klasse](../mfc/reference/carchive-class.md)   
 [CObject-Klasse](../mfc/reference/cobject-class.md)

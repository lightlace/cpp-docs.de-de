---
title: Datei-e-A-Klassen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.classes.file
dev_langs:
- C++
helpviewer_keywords:
- disk file classes [MFC]
- stdio classes [MFC]
- OLE streams [MFC]
- I/O [MFC], MFC classes
- translated stream classes [MFC]
- file I/O classes [MFC]
- I/O [MFC], classes
- sockets classes [MFC]
- stream classes [MFC]
- memory file classes [MFC]
ms.assetid: 92821c3f-d9e1-47f6-98c9-3b632d86e811
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 454e64d67321282030126d2aab023e9f587c1cca
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="file-io-classes"></a>Klassen für Datei-E/A
Diese Klassen bieten eine Schnittstelle zu herkömmlichen Datenträgerdateien, in-Memory-Dateien, aktive Streams und Windows-Sockets. Alle Klassen abgeleitet `CFile` kann verwendet werden, mit einem `CArchive` -Objekt, die Serialisierungen durchführen.  
  
 Verwenden Sie die folgenden Klassen, insbesondere `CArchive` und `CFile`, wenn Sie eine eigene e/a-Verarbeitung schreiben. Sie müssen normalerweise nicht von diesen Klassen abgeleitet werden. Bei Verwendung von Anwendungsframeworks, standardmäßigen Implementierungen von der **öffnen** und **speichern** Befehle der **Datei** behandelt im Menü Datei-e/a (Klasse mit`CArchive`), sofern Sie Ihr Dokuments überschreiben `Serialize` Funktion geben Sie details zur wie ein Dokument mit dessen Inhalt serialisiert. Weitere Informationen zu den Dateiklassen und die Serialisierung finden Sie im Artikel [Dateien in MFC](../mfc/files-in-mfc.md) und im Artikel [Serialisierung](../mfc/serialization-in-mfc.md).  
  
 [CFile](../mfc/reference/cfile-class.md)  
 Stellt eine Schnittstelle auf binäre Datenträgerdateien bereit.  
  
 [CStdioFile](../mfc/reference/cstdiofile-class.md)  
 Bietet eine `CFile` Schnittstelle, um den gepufferten Datenstrom Datenträgerdateien, die in der Regel im Textmodus.  
  
 [CMemFile](../mfc/reference/cmemfile-class.md)  
 Bietet eine `CFile` Schnittstelle, um in-Memory-Datendateien.  
  
 [CSharedFile](../mfc/reference/csharedfile-class.md)  
 Bietet eine `CFile` Schnittstelle, um freigegebene in-Memory-Datendateien.  
  
 [COleStreamFile](../mfc/reference/colestreamfile-class.md)  
 Die COM verwendet `IStream` Schnittstelle `CFile` Zugriff auf Dateien, zusammengesetzte.  
  
 [CSocketFile](../mfc/reference/csocketfile-class.md)  
 Bietet eine `CFile` Schnittstelle, um einen Windows Socket.  
  
## <a name="related-classes"></a>Verwandte Klassen  
 [CArchive](../mfc/reference/carchive-class.md)  
 Arbeitet mit einem `CFile` Objekt permanenten Speicher für Objekte, die über die Serialisierung implementiert (finden Sie unter [Einfügeoperatoren](../mfc/reference/cobject-class.md#serialize)).  
  
 [CArchiveException](../mfc/reference/carchiveexception-class.md)  
 Eine Ausnahme Archiv.  
  
 [CFileException](../mfc/reference/cfileexception-class.md)  
 Eine Datei-orientierte-Ausnahme.  
  
 [CFileDialog](../mfc/reference/cfiledialog-class.md)  
 Stellt ein Standarddialogfeld zum Öffnen oder Speichern einer Datei an.  
  
 [CRecentFileList](../mfc/reference/crecentfilelist-class.md)  
 Verwaltet die zuletzt verwendeten Dateiliste (MRU).  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../mfc/class-library-overview.md)


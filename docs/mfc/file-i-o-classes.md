---
title: Datei-e / A-Klassen
ms.date: 11/04/2016
f1_keywords:
- vc.classes.file
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
ms.openlocfilehash: 914325ec56f0cae30c7293305496d65f358f2731
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405806"
---
# <a name="file-io-classes"></a>Klassen für Datei-E/A

Diese Klassen bieten eine Schnittstelle zu der herkömmlichen Datenträgerdateien, in-Memory-Dateien, aktive Streams und Windows-Sockets. Alle Klassen abgeleitet `CFile` kann verwendet werden, mit einem `CArchive` Objekt zur Serialisierung.

Verwenden Sie die folgenden Klassen, insbesondere `CArchive` und `CFile`, wenn Sie Ihre eigene e/a-Verarbeitung schreiben. Normalerweise müssen Sie nicht von diesen Klassen abgeleitet werden. Wenn die Anwendung, die standardimplementierungen der Verwendung von der **öffnen** und **speichern** von Befehlen auf der der **Datei** behandelt im Menü Datei-e/a (verwenden -Klasse`CArchive`), solange Sie außer Kraft des Dokuments setzen `Serialize` Funktion geben Sie details zur wie ein Dokument für seinen Inhalt serialisiert. Weitere Informationen zu den Dateiklassen und die Serialisierung finden Sie im Artikel [Dateien in MFC](../mfc/files-in-mfc.md) und im Artikel [Serialisierung](../mfc/serialization-in-mfc.md).

[CFile](../mfc/reference/cfile-class.md)<br/>
Stellt eine Datei-Schnittstelle für binäre Dateien.

[CStdioFile](../mfc/reference/cstdiofile-class.md)<br/>
Stellt eine `CFile` Schnittstelle gepufferten Stream auf Dateien auf Datenträgern, in der Regel im Textmodus.

[CMemFile](../mfc/reference/cmemfile-class.md)<br/>
Stellt eine `CFile` Schnittstelle für InMemory-Dateien.

[CSharedFile](../mfc/reference/csharedfile-class.md)<br/>
Stellt eine `CFile` Schnittstelle, um freigegebene in-Memory-Dateien.

[COleStreamFile](../mfc/reference/colestreamfile-class.md)<br/>
Die COM verwendet `IStream` -Schnittstelle zur Bereitstellung `CFile` Zugriff auf Dateien zusammengesetzte.

[CSocketFile](../mfc/reference/csocketfile-class.md)<br/>
Stellt eine `CFile` Schnittstelle, um einen Windows Socket.

## <a name="related-classes"></a>Verwandte Klassen

[CArchive](../mfc/reference/carchive-class.md)<br/>
Arbeitet mit einem `CFile` Objekt das Implementieren des permanenten Speicher für Objekte, die über die Serialisierung (finden Sie unter [CObject:: Serialize](../mfc/reference/cobject-class.md#serialize)).

[CArchiveException](../mfc/reference/carchiveexception-class.md)<br/>
Ausnahme "Archiv".

[CFileException](../mfc/reference/cfileexception-class.md)<br/>
Eine Ausnahme dateiorientierte.

[CFileDialog](../mfc/reference/cfiledialog-class.md)<br/>
Stellt ein Standarddialogfeld für öffnen oder Speichern einer Datei bereit.

[CRecentFileList](../mfc/reference/crecentfilelist-class.md)<br/>
Verwaltet die zuletzt verwendeten Dateiliste (MRU).

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../mfc/class-library-overview.md)

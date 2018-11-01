---
title: Dateien in MFC
ms.date: 11/04/2016
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
ms.openlocfilehash: 815239b0d4de1938a810153cb98f39b2642b6e2d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50459331"
---
# <a name="files-in-mfc"></a>Dateien in MFC

In der Microsoft Foundation Class-Bibliothek (MFC), Klasse [CFile](../mfc/reference/cfile-class.md) normale Datei-e/a-Vorgänge behandelt. In dieser Artikelreihe wird erläutert, wie zu öffnen und schließen Sie Dateien als auch lesen und Schreiben von Daten in diese Dateien werden. Darüber hinaus werden die Status der Dateivorgänge erläutert. Eine Beschreibung wie die Serialisierung objektbasierten-Funktionen von MFC als eine alternative Möglichkeit für das Lesen und Schreiben von Daten in Dateien verwendet, finden Sie im Artikel [Serialisierung](../mfc/serialization-in-mfc.md).

> [!NOTE]
>  Bei Verwendung von MFC `CDocument` Objekten, die das Framework ermöglicht ein Großteil der Arbeit für die Serialisierung für Sie. Insbesondere das Framework erstellt und verwendet die `CFile` Objekt. Sie müssen nur Code in der Überschreibung der Schreiben der `Serialize` Memberfunktion der Klasse `CDocument`.

Die `CFile` Klasse stellt eine Schnittstelle für allgemeine Zwecke binäre Dateivorgänge. Die `CStdioFile` und `CMemFile` von abgeleiteten Klassen `CFile` und `CSharedFile` abgeleitete Klasse `CMemFile` spezialisierteren "Dateidienste" angeben.

Weitere Informationen zu alternativen für die Behandlung von MFC-Datei, finden Sie unter [Dateibehandlung](../c-runtime-library/file-handling.md) in die *Run-Time Library Reference*.

Informationen zum abgeleiteten `CFile` finden Sie unter den [MFC-Hierarchiediagramm](../mfc/hierarchy-chart.md).

## <a name="what-do-you-want-to-do"></a>Was möchten Sie tun

*Verwenden von CFile*

- [Öffnen Sie eine Datei mit CFile](../mfc/opening-files.md)

- [Lesen Sie und Schreiben Sie eine Datei mit CFile](../mfc/reading-and-writing-files.md)

- [Schließen Sie eine Datei mit CFile](../mfc/closing-files.md)

- [Status der Access-Datei mit CFile](../mfc/accessing-file-status.md)

*Verwenden von MFC-Serialisierung (Objektpersistenz)*

- [Erstellen einer serialisierbaren Klasse](../mfc/serialization-making-a-serializable-class.md)

- [Serialisiert ein Objekt über ein CArchive-Objekt](../mfc/serialization-serializing-an-object.md)

- [Erstellen eines CArchive-Objekts](../mfc/two-ways-to-create-a-carchive-object.md)

- [Verwenden der CArchive <\< und >> Operatoren](../mfc/using-the-carchive-output-and-input-operators.md)

- [Store, und Laden eines CObject und CObject abgeleitete Objekte per Archiv](../mfc/storing-and-loading-cobjects-via-an-archive.md)

## <a name="see-also"></a>Siehe auch

[Konzepte](../mfc/mfc-concepts.md)<br/>
[Allgemeine MFC-Themen](../mfc/general-mfc-topics.md)<br/>
[CArchive-Klasse](../mfc/reference/carchive-class.md)<br/>
[CObject-Klasse](../mfc/reference/cobject-class.md)

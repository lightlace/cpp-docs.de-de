---
title: Umgehen des Serialisierungsmechanismus
ms.date: 11/04/2016
helpviewer_keywords:
- archive objects [MFC]
- bypassing serialization
- archives [MFC], serialization
- serialization [MFC], bypassing
- archives [MFC]
- serialization [MFC], role of framework
- serialization [MFC], overriding
ms.assetid: 48d4a279-b51c-4ba5-81cd-ed043312b582
ms.openlocfilehash: 1937098de30884be327c67a698dbb0023be248bb
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345203"
---
# <a name="bypassing-the-serialization-mechanism"></a>Umgehen des Serialisierungsmechanismus

Wie Sie gesehen haben, bietet das Framework eine Standardmethode zum Lesen und Schreiben von Daten in und aus Dateien. Durch ein Archivobjekt serialisieren, ist die Anforderungen von einem hervorragenden viele Anwendungen geeignet. Eine solche Anwendung liest eine Datei vollständig in den Arbeitsspeicher, ermöglicht dem Benutzer die Datei zu aktualisieren und anschließend die aktualisierte Version wieder auf den Datenträger geschrieben.

Allerdings werden einige Anwendungen verarbeiten Daten sehr unterschiedlich, und für diese Anwendungen-Serialisierung durch ein Archiv ist nicht geeignet. Beispiele sind Datenbankprogramme, Programme, die nur die Teile von großen Dateien bearbeiten, Programme, die nur-Text-Dateien zu schreiben und Programme, die Datendateien gemeinsam nutzen.

In diesen Fällen können Sie überschreiben die [Serialize](../mfc/reference/cobject-class.md#serialize) -Funktion in eine andere Weise für die Vermittlung von Dateiaktionen über eine [CFile](../mfc/reference/cfile-class.md) Objekt anstelle eines [CArchive](../mfc/reference/carchive-class.md) Objekt.

Sie können die `Open`, `Read`, `Write`, `Close`, und `Seek` Memberfunktionen der Klasse `CFile` um eine Datei zu öffnen, bewegen Sie den Dateizeiger (seek) zu einem bestimmten Zeitpunkt in der Datei ein Datensatz (eine angegebene Anzahl von Bytes lesen ) zu diesem Zeitpunkt kann der Benutzer, aktualisieren Sie den Eintrag, und klicken Sie dann erneut auf demselben Zeitpunkt zu suchen und den Datensatz zurück in die Datei zu schreiben. Das Framework wird die Datei für Sie geöffnet, und können Sie die `GetFile` Memberfunktion der Klasse `CArchive` einen Zeiger zum Abrufen der `CFile` Objekt. Sie können für die Verwendung von noch mehr ausgefeilte und flexible, überschreiben die [OnOpenDocument](../mfc/reference/cdocument-class.md#onopendocument) und [OnSaveDocument](../mfc/reference/cdocument-class.md#onsavedocument) Memberfunktionen der Klasse `CWinApp`. Weitere Informationen finden Sie in der Klasse [CFile](../mfc/reference/cfile-class.md) in die *MFC-Referenz*.

In diesem Fall Ihre `Serialize` Außerkraftsetzung nichts, es sei denn, Sie beispielsweise so, dass sie das Lesen und Schreiben eines Datei Headers an, um es auf dem neuesten Stand zu halten, wenn das Dokument geschlossen wird.

## <a name="see-also"></a>Siehe auch

[Verwenden von Dokumenten](../mfc/using-documents.md)

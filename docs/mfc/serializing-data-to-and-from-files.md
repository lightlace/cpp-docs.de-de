---
title: Serialisieren von Daten in und aus Dateien
ms.date: 11/04/2016
helpviewer_keywords:
- documents [MFC], serialization
- documents [MFC], saving
- saving documents
- deserialization [MFC]
- serialization [MFC], role of document
- serialization [MFC], role of data
- data [MFC]
- data [MFC], serializing
- document data [MFC]
ms.assetid: b42a0c68-4bc4-4012-9938-5433a26d2c24
ms.openlocfilehash: af3cde9445ae4b128e7e54a5f154db01b2eecd3b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62308066"
---
# <a name="serializing-data-to-and-from-files"></a>Serialisieren von Daten in und aus Dateien

Die grundlegende Idee von Persistenz ist, dass ein Objekt seinen aktuellen Status, angegeben durch die Werte der zugehörigen Membervariablen, in den permanenten Speicher schreiben kann. Später kann das Objekt neu erstellt werden, indem gelesen oder "deserialisiert," den Zustand des Objekts aus dem persistenten Speicher. Ein wichtiger Punkt hier ist, dass das Objekt selbst zum Lesen und Schreiben ihren eigenen Zustand verantwortlich ist. Daher muss er für eine Klasse beibehalten werden, die einfache Serialisierungsvorgänge implementieren.

Das Framework stellt eine Standardimplementierung zum Speichern von Dokumenten in Datenträgerdateien, die als Reaktion auf Speichern, und speichern als Befehle im Menü Datei und zum Laden von Dokumenten aus Dateien auf Datenträgern als Reaktion auf den Befehl öffnen. Sie können mit sehr geringem Aufwand eines Dokuments Möglichkeit zum Schreiben und Lesen von Daten in und aus einer Datei implementieren. Der wichtigste Aspekt besteht, Sie müssen, die Außerkraftsetzung ist die [Serialize](../mfc/reference/cobject-class.md#serialize) Member-Funktion in der Dokumentklasse.

Die MFS-Anwendungsassistenten platziert eine skeletal Überschreibung der `CDocument` Memberfunktion `Serialize` in der Dokumentklasse, die für Sie erstellt. Nachdem Sie die Membervariablen Ihrer Anwendung implementiert haben, können Sie in eingeben Ihrer `Serialize` außer Kraft setzen, mit Code, der die Daten in eine "Archiv-Object" in einer Datei verbundenen sendet. Ein [CArchive](../mfc/reference/carchive-class.md) -Objekt ähnelt der **"CIN"** und **"cout"** e/a-Objekte aus der C++-Iostream-Bibliothek. Allerdings `CArchive` schreibt und binäres Format, nicht formatierten Text liest.

## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren

- [Serialisierung](../mfc/serialization-in-mfc.md)

- [Die Aufgabe des Dokuments bei der Serialisierung](#_core_the_document.92.s_role_in_serialization)

- [Die Daten für die Rolle bei der Serialisierung](#_core_the_data.92.s_role_in_serialization)

- [Umgehen des Serialisierungsmechanismus](../mfc/bypassing-the-serialization-mechanism.md)

##  <a name="_core_the_document.92.s_role_in_serialization"></a> Die Aufgabe des Dokuments bei der Serialisierung

Das Framework reagiert automatisch auf das Menü Datei öffnen, speichern, und speichern Sie als Befehle, durch den Aufruf des Dokuments `Serialize` Memberfunktion, wenn er implementiert wird. Ein ID_FILE_OPEN-Befehl ruft beispielsweise eine Handlerfunktion im Anwendungsobjekt. Während dieses Vorgangs wird der Benutzer sieht und reagiert auf das Dialogfeld Datei öffnen, und das Framework Ruft den Dateinamen, die, den der Benutzer auswählt. Das Framework erstellt eine `CArchive` Objekt festgelegt werden, sich für das Laden von Daten in das Dokument und übergibt das Archiv in `Serialize`. Das Framework wurde die Datei bereits geöffnet. Der Code in Ihrem Dokuments die `Serialize` Memberfunktion liest die Daten im durch das Archiv, und rekonstruieren Datenobjekte aus, je nach Bedarf. Weitere Informationen zur Serialisierung finden Sie im Artikel [Serialisierung](../mfc/serialization-in-mfc.md).

##  <a name="_core_the_data.92.s_role_in_serialization"></a> Die Daten für die Rolle bei der Serialisierung

Im Allgemeinen sollten Daten vom Typ Klasse selbst serialisieren können. D. h. Wenn Sie ein Objekt in ein Archiv übergeben, sollte das Objekt selbst schreiben, in das Archiv und selbst aus dem Archiv lesen kennen. MFC bietet Unterstützung für die Serialisierbarkeit von Klassen auf diese Weise. Wenn Sie eine Klasse zum Definieren eines Datentyps entwerfen und Daten dieses Typs serialisiert werden soll, die für die Serialisierung entworfen Sie werden.

## <a name="see-also"></a>Siehe auch

[Verwenden von Dokumenten](../mfc/using-documents.md)

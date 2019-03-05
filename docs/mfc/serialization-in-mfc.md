---
title: Serialisierung in MFC
ms.date: 11/04/2016
helpviewer_keywords:
- collection classes [MFC], serialization
- bypassing serialization [MFC]
- MFC, serialization
- serialization [MFC], MFC
- serialization [MFC], bypassing
ms.assetid: fb596a18-4522-47e0-96e0-192732d24c12
ms.openlocfilehash: 5c7dec140635b6d83bdae936d1bb0cef144f825b
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57262141"
---
# <a name="serialization-in-mfc"></a>Serialisierung in MFC

In diesem Artikel erläutert der Serialisierungsmechanismus, angegeben in der Microsoft Foundation Class Library (MFC), Objekte zwischen beibehalten werden können Ihr Programm ausgeführt wird.

Serialisierung ist der Prozess der Schreib- und Lesezugriffe auf ein Objekt, oder über ein persistentes Speichermedium, z. B. eine Datenträgerdatei. Serialisierung ist ideal für Situationen, in denen es gewünscht wird, um den Status von strukturierten Daten (z. B. C++-Klassen oder Strukturen) während oder nach der Ausführung eines Programms beizubehalten. Mit den Serialisierungsinformationen von MFC bereitgestellten, ermöglicht dies geschieht in standard und konsistente Weise sind daher weniger den Benutzer aus Dateioperationen manuell ausführen müssen.

MFC bietet integrierte Unterstützung für die Serialisierung in der Klasse `CObject`. Daher alle Klassen abgeleitet `CObject` profitieren von `CObject`des Serialisierungsprotokoll.

Der Grundgedanke der Serialisierung ist, dass ein Objekt seinen aktuellen Status, angegeben in der Regel durch den Wert der zugehörigen Membervariablen, in den permanenten Speicher geschrieben werden sollten. Später kann das Objekt neu erstellt werden, indem gelesen bzw. deserialisiert, den Zustand des Objekts aus dem Speicher. Serialisierung handhabt alle Details zu Objektzeigern und Zirkuläre Verweise auf Objekte, die bei der Serialisierung eines Objekts verwendet werden. Ein wichtiger Punkt ist, dass das Objekt selbst zum Lesen und Schreiben ihren eigenen Zustand verantwortlich ist. Daher muss er für eine Klasse serialisierbar sein, die einfache Serialisierungsvorgänge implementieren. Wie in der Gruppe der Serialisierung von Artikeln dargestellt, ist es einfach, diese Funktionalität zu einer Klasse hinzuzufügen.

MFC verwendet, ein Objekt der `CArchive` Klasse als Vermittler zwischen dem Objekt serialisiert werden soll und das Speichermedium. Dieses Objekt ist immer mit verknüpft eine `CFile` Objekt, aus denen sie die erforderlichen Informationen für die Serialisierung, einschließlich des Dateinamens abruft, und gibt an, ob der angeforderte Vorgang ein Lese- oder Schreibvorgang ist. Das Objekt, das eine Serialisierung ausführt können die `CArchive` Objekt ohne Berücksichtigung der Art des Speichermediums.

Ein `CArchive` Objekt wird verwendet, überladene einfügen (**<\<**) und extrahieren (**>>**) Operatoren zum Ausführen von Schreib- und Lesevorgänge. Weitere Informationen finden Sie unter [speichern und Laden eines CObject per Archiv](../mfc/storing-and-loading-cobjects-via-an-archive.md) in diesem Artikel Serialisierung: Serialisieren eines Objekts an.

> [!NOTE]
>  Verwechseln Sie nicht die `CArchive` Klasse mit allgemeinen Iostream-Klassen, die für sind von formatiertem Text nur. Die `CArchive` Klasse ist für Binärformat serialisierten Objekte.

Wenn Sie möchten, können Sie die Serialisierung von MFC zum Erstellen eines eigenen Mechanismus zum persistenten Datenspeicher umgehen. Sie müssen die Memberfunktionen der Klasse überschreiben, die Serialisierung an des Benutzers zu initiieren. Finden Sie unter den Ausführungen im [technischen Hinweis 22](../mfc/tn022-standard-commands-implementation.md) ID_FILE_OPEN ID_FILE_SAVE und ID_FILE_SAVE_AS Standardbefehle.

In den folgenden Artikeln behandelt, die zwei Hauptaufgaben, die für die Serialisierung erforderlich:

- [Serialisierung: Erstellen einer serialisierbaren Klasse](../mfc/serialization-making-a-serializable-class.md)

- [Serialisierung: Serialisieren eines Objekts](../mfc/serialization-serializing-an-object.md)

Der Artikel [Serialisierung: Serialisierung im Vergleich zu Datenbank-e/a](../mfc/serialization-serialization-vs-database-input-output.md) wird beschrieben, bei der Serialisierung eine entsprechende Eingabe/Ausgabe-Methode in datenbankanwendungen ist.

## <a name="see-also"></a>Siehe auch

[Konzepte](../mfc/mfc-concepts.md)<br/>
[Allgemeine MFC-Themen](../mfc/general-mfc-topics.md)<br/>
[CArchive-Klasse](../mfc/reference/carchive-class.md)<br/>
[CObject-Klasse](../mfc/reference/cobject-class.md)<br/>
[CDocument-Klasse](../mfc/reference/cdocument-class.md)<br/>
[CFile-Klasse](../mfc/reference/cfile-class.md)

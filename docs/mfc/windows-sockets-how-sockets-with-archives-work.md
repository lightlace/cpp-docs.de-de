---
title: 'Windows Sockets: Wie Sockets mit Archiven arbeiten'
ms.date: 11/19/2018
helpviewer_keywords:
- Windows Sockets [MFC], synchronous
- sockets [MFC], synchronous operation
- sockets [MFC], with archives
- synchronous state socket
- Windows Sockets [MFC], with archives
- two-state socket object
ms.assetid: d8ae4039-391d-44f0-a19b-558817affcbb
ms.openlocfilehash: 3af94bc881276238f1a8d2dbeeee4dca1f173a4b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62389442"
---
# <a name="windows-sockets-how-sockets-with-archives-work"></a>Windows Sockets: Wie Sockets mit Archiven arbeiten

In diesem Artikel wird erläutert, wie eine [CSocket](../mfc/reference/csocket-class.md) Objekt eine [CSocketFile](../mfc/reference/csocketfile-class.md) -Objekt, und ein [CArchive](../mfc/reference/carchive-class.md) Objekt werden kombiniert, um vereinfachen das Senden und Empfangen von Daten über eine Windows Socket.

Der Artikel [Windows Sockets: Beispiel für Sockets mithilfe der Archive](../mfc/windows-sockets-example-of-sockets-using-archives.md) stellt die `PacketSerialize` Funktion. Das Archivobjekt in der `PacketSerialize` Beispiel funktioniert ähnlich wie ein Archivobjekt, das an einen übergebenen [Serialize](../mfc/reference/cobject-class.md#serialize) Funktion. Der wichtige Unterschied besteht darin, dass für Sockets, das Archiv, nicht auf einen Standard angefügt ist [CFile](../mfc/reference/cfile-class.md) Objekt (i. d. r. eine Datenträgerdatei zugeordneten) in einem `CSocketFile` Objekt. Anstatt eine Datenträgerdatei mit den `CSocketFile` -Objekt eine Verbindung herstellt, um eine `CSocket` Objekt.

Ein `CArchive` Objekt verwaltet einen Puffer. Wenn der Puffer eines Archivs das Speichern von (senden) voll ist, ein zugeordnetes `CFile` Objekt schreibt Inhalte des Puffers. Das Leeren der Puffer eines Archivs, angefügt an einen Socket entspricht zum Senden einer Nachricht. Wenn der Puffer eines Archivs laden (empfangen) voll ist, ist die `CFile` Objekt lesen beendet, bis der Puffer wieder verfügbar ist.

Klasse `CSocketFile` leitet sich von `CFile`, aber wird nicht unterstützt [CFile](../mfc/reference/cfile-class.md) Member-Funktionen wie z. B. die dateipositionierenden Funktionen (`Seek`, `GetLength`, `SetLength`und so weiter), das Sperren von Funktionen () `LockRange`, `UnlockRange`), oder die `GetPosition` Funktion. Alle der [CSocketFile](../mfc/reference/csocketfile-class.md) Objekt erforderlich ist, schreiben oder Lesen von Bytesequenzen in oder aus der zugeordneten `CSocket` Objekt. Da eine Datei nicht beteiligt ist, Vorgänge wie `Seek` und `GetPosition` nicht sinnvoll. `CSocketFile` stammt aus `CFile`, sodass sie alle diese Memberfunktionen normalerweise geerbt wird. Um dies zu den nicht unterstützten verhindern `CFile` Memberfunktionen überschrieben werden, `CSocketFile` Auslösen einer [CNotSupportedException](../mfc/reference/cnotsupportedexception-class.md).

Die `CSocketFile` Objekt ruft Funktionen des die `CSocket` Objekt zum Senden oder Empfangen von Daten.

Die folgende Abbildung zeigt die Beziehungen zwischen diesen Objekten auf beiden Seiten der Kommunikation.

![CArchive, CSocketFile und CSocket](../mfc/media/vc38ia1.gif "CArchive, CSocketFile und CSocket") <br/>
CArchive, CSocketFile und CSocket

Der Zweck dieser offensichtlichen Komplexität ist, Sie über die Notwendigkeit, die Details des Sockets selbst verwalten zu schützen. Sie erstellen den Socket, die Datei und des Archivs und klicken Sie dann zunächst senden oder empfangende von Daten in das Archiv einfügen oder extrahieren es aus dem Archiv. [CArchive](../mfc/reference/carchive-class.md), [CSocketFile](../mfc/reference/csocketfile-class.md), und [CSocket](../mfc/reference/csocket-class.md) verwalten Sie die Details im Hintergrund.

Ein `CSocket` Objekt ist tatsächlich ein zwei-Status-Objekt: manchmal asynchrone (mehr den gewöhnlichen Status) und manchmal synchrone. Im asynchronen Zustand kann ein Socket asynchrone Benachrichtigungen vom Framework empfangen. Während eines Vorgangs, z. B. empfangen oder Senden von Daten wird der Socket jedoch synchron. Dies bedeutet, dass der Socket keine weiteren asynchrone Benachrichtigungen gesendet werden, bis der synchrone Vorgang abgeschlossen ist. Da es Modus wechselt, beispielsweise etwa wie folgt möglich:

[!code-cpp[NVC_MFCSimpleSocket#2](../mfc/codesnippet/cpp/windows-sockets-how-sockets-with-archives-work_1.cpp)]

Wenn `CSocket` wurden nicht implementiert, wie ein zwei-Status-Objekt ist es eventuell möglich, um zusätzliche Benachrichtigungen für die gleiche Art von Ereignis zu empfangen, während Sie eine vorherige Benachrichtigung verarbeitet wurden. Angenommen, Sie erhalten möglicherweise eine `OnReceive` Benachrichtigung während der Verarbeitung einer `OnReceive`. Im obigen Codefragment, extrahieren `str` aus dem Archiv zu Rekursion führen. Durch den Wechsel der Zustände `CSocket` wird verhindert, dass Rekursion durch zusätzliche Benachrichtigungen zu verhindern. Als allgemeine Regel gilt keine Benachrichtigungen Benachrichtigungen.

> [!NOTE]
> Ein `CSocketFile` kann auch verwendet werden, als (begrenzt) Datei ohne eine `CArchive` Objekt. In der Standardeinstellung die `CSocketFile` des Konstruktors *bArchiveCompatible* Parameter **"true"**. Dies gibt an, dass das Objekt "Datei" für die Verwendung mit einem Archiv. Um das Objekt "Datei" ohne ein Archiv zu verwenden, übergeben **"false"** in die *bArchiveCompatible* Parameter.

In den Modus "Archive-Compatible" ein `CSocketFile` Objekt bietet eine bessere Leistung und reduziert die Gefahr von "Deadlock". Ein Deadlock tritt auf, wenn die sendenden und empfangenden Sockets sind aufeinander warten, oder warten auf eine gemeinsame Ressource. Diese Situation kann eintreten, wenn die `CArchive` Objekt hat die `CSocketFile` die Möglichkeit, dies der Fall ist mit, einem `CFile` Objekt. Mit `CFile`, das Archiv kann davon ausgehen, empfängt er weniger Bytes als angefordert, am Ende der Datei erreicht wurde. Mit `CSocketFile`, jedoch Daten basiert auf Nachrichten; der Puffer kann mehrere Nachrichten enthalten, erhalten also weniger als die Anzahl der angeforderten Bytes Ende der Datei nicht impliziert. Die Anwendung wird in diesem Fall nicht blockiert, wie sie mit `CFile`, und sie können fortfahren, Lesen von Nachrichten aus dem Puffer, bis der Puffer leer ist. Die [IsBufferEmpty](../mfc/reference/carchive-class.md#isbufferempty) -Funktion in `CArchive` eignet sich zum Überwachen des Status des Archivs Puffer in einem solchen Fall.

Weitere Informationen finden Sie unter [Windows Sockets: Verwenden von Sockets mit Archiven](../mfc/windows-sockets-using-sockets-with-archives.md)

## <a name="see-also"></a>Siehe auch

[Windows-Sockets in MFC](../mfc/windows-sockets-in-mfc.md)<br/>
[CObject:: Serialize](../mfc/reference/cobject-class.md#serialize)

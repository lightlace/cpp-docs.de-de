---
title: 'Windows Sockets: Wie Sockets mit Archiven arbeiten | Microsoft Docs'
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
- Windows Sockets [MFC], synchronous
- sockets [MFC], synchronous operation
- sockets [MFC], with archives
- synchronous state socket
- Windows Sockets [MFC], with archives
- two-state socket object
ms.assetid: d8ae4039-391d-44f0-a19b-558817affcbb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1b6ff5f07e3662e61a7ba6260bb90459f3aebd7d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="windows-sockets-how-sockets-with-archives-work"></a>Windows Sockets: Wie Sockets mit Archiven arbeiten
In diesem Artikel wird erläutert, wie eine [CSocket](../mfc/reference/csocket-class.md) -Objekt, eine [CSocketFile](../mfc/reference/csocketfile-class.md) -Objekt, und ein [CArchive](../mfc/reference/carchive-class.md) Objekt werden kombiniert, um vereinfachen das Senden und Empfangen von Daten über eine Windows Ein Sockettimeout aufgetreten.  
  
 Der Artikel [Windows Sockets: Beispiel für Sockets mithilfe Archive](../mfc/windows-sockets-example-of-sockets-using-archives.md) stellt die **PacketSerialize** Funktion. Das Archivobjekt in der **PacketSerialize** Beispiel funktioniert ähnlich wie ein Archivobjekt übergeben, um ein MFC [Serialize](../mfc/reference/cobject-class.md#serialize) Funktion. Der wesentliche Unterschied ist, dass für Sockets, das Archiv, nicht an einen Standard angefügt ist [CFile](../mfc/reference/cfile-class.md) Objekt (i. d. r. eine Datenträgerdatei zugeordnet) in einem `CSocketFile` Objekt. Anstatt das Herstellen einer Verbindung mit einer Datenträgerdatei der `CSocketFile` Objekt eine Verbindung mit einem `CSocket` Objekt.  
  
 Ein `CArchive` Objekt verwaltet einen Puffer. Wenn der Puffer eines speichern (senden) Archivs voll ist, ein zugehöriges `CFile` Objekt schreibt, die Inhalte des Puffers. Das Leeren des Puffers eines Archivs, angefügt an ein Socket entspricht dem Senden einer Nachricht zur Verfügung. Wenn der Puffer eines Archivs laden (empfangen) voll ist, ist die `CFile` Objekt beendet das Lesen, bis der Puffer wieder verfügbar ist.  
  
 Klasse `CSocketFile` leitet sich von `CFile`, jedoch nicht unterstützt [CFile](../mfc/reference/cfile-class.md) Memberfunktionen, z. B. die dateipositionierenden Funktionen (`Seek`, `GetLength`, `SetLength`usw.), () funktioniert das Sperren `LockRange`, `UnlockRange`), oder die `GetPosition` Funktion. Alle der [CSocketFile](../mfc/reference/csocketfile-class.md) Objekt erforderlich ist, schreiben oder Lesen von Bytefolgen zu oder von der zugeordneten `CSocket` Objekt. Da eine Datei nicht beteiligt ist, Vorgänge wie `Seek` und `GetPosition` nicht sinnvoll. `CSocketFile`stammt aus `CFile`, sodass sie alle diese Memberfunktionen normalerweise geerbt wird. Um dies zu den nicht unterstützten verhindern `CFile` Memberfunktionen werden außer Kraft gesetzt `CSocketFile` ausgelöst werden soll eine [CNotSupportedException](../mfc/reference/cnotsupportedexception-class.md).  
  
 Die `CSocketFile` Objekt ruft die Memberfunktionen von seiner `CSocket` Objekt zum Senden oder Empfangen von Daten.  
  
 Die folgende Abbildung zeigt die Beziehungen zwischen diesen Objekten auf beiden Seiten der Kommunikation.  
  
 ![CArchive, CSocketFile und CSocket](../mfc/media/vc38ia1.gif "vc38ia1")  
CArchive, CSocketFile und CSocket  
  
 Der Zweck dieser offensichtlichen Komplexität werden Sie geschützt werden, über die Notwendigkeit, die Details des Sockets zu verwalten. Sie erstellen, den Socket, die Datei und das Archiv, und klicken Sie dann senden oder empfangende von Daten beginnen, indem es in das Archiv einfügen oder extrahieren es aus dem Archiv. [CArchive](../mfc/reference/carchive-class.md), [CSocketFile](../mfc/reference/csocketfile-class.md), und [CSocket](../mfc/reference/csocket-class.md) verwalten Sie die Details im Hintergrund.  
  
 Ein `CSocket` Objekt ist tatsächlich ein zwei-Status-Objekt: in einigen Fällen asynchrone (den gewöhnlichen Status aufweist) und in einigen Fällen synchrone. Im asynchronen Zustand kann ein Socket asynchrone Benachrichtigungen von Framework empfangen. Während eines Vorgangs, z. B. empfangen oder Senden von Daten wird der Socket jedoch synchron. Dies bedeutet, dass der Socket keine weiteren asynchrone Benachrichtigungen gesendet werden, bis der Vorgang synchrone abgeschlossen wurde. Da es Modus wechselt, z. B. etwa wie die folgende Möglichkeiten:  
  
 [!code-cpp[NVC_MFCSimpleSocket#2](../mfc/codesnippet/cpp/windows-sockets-how-sockets-with-archives-work_1.cpp)]  
  
 Wenn `CSocket` nicht implementiert wurden als eine zwei-Status-Objekt, es kann möglich sein, zusätzliche Benachrichtigungen für die gleiche Art von Ereignis zu erhalten, während Sie eine vorherige Benachrichtigung verarbeitet wurden. Angenommen, Sie erhalten möglicherweise eine `OnReceive` Benachrichtigung während der Verarbeitung einer `OnReceive`. Im obigen Codefragment extrahieren `str` kann aus dem Archiv zu Rekursion führen. Durch den Wechsel Zustände `CSocket` wird verhindert, dass Rekursion durch Verhindern von automatisch neu gestartet. Als allgemeine Regel gilt keine Benachrichtigungen Benachrichtigungen.  
  
> [!NOTE]
>  Ein `CSocketFile` kann auch verwendet werden, als (begrenzt)-Datei ohne eine `CArchive` Objekt. Wird standardmäßig die `CSocketFile` des Konstruktors `bArchiveCompatible` Parameter ist **"true"**. Dies gibt an, dass das Objekt "Datei" für die Verwendung mit einem Archiv. Um das Objekt "Datei" ohne ein Archiv zu verwenden, übergeben **"false"** in der `bArchiveCompatible` Parameter.  
  
 Im Modus "Archiv Compatible" ein `CSocketFile` Objekt bietet eine bessere Leistung und reduziert die Gefahr eines "Deadlocks". Ein Deadlock tritt auf, wenn die sendenden und empfangenden Sockets warten auf einander, oder eine gemeinsame Ressource warten. Diese Situation kann auftreten, wenn die `CArchive` Objekt arbeitet mit der `CSocketFile` Weise mit einem `CFile` Objekt. Mit `CFile`, das Archiv kann davon ausgehen, dass weniger Bytes als angefordert Empfang, die das Ende der Datei erreicht wurde. Mit `CSocketFile`jedoch Daten nachrichtenbasiert; der Puffer kann mehrere Nachrichten enthalten, wird daher empfangen von weniger als die Anzahl der angeforderten Bytes Dateiende nicht impliziert. Die Anwendung wird in diesem Fall nicht blockiert, wie mit möglicherweise `CFile`, und sie können weiterhin Nachrichten aus dem Puffer zu lesen, bis der Puffer leer ist. Die [IsBufferEmpty](../mfc/reference/carchive-class.md#isbufferempty) -Funktion in `CArchive` eignet sich zum Überwachen des Status des Archivs Puffer in einem solchen Fall.  
  
 Weitere Informationen finden Sie unter [Windows Sockets: Verwenden von Sockets mit Archiven](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Windows-Sockets in MFC](../mfc/windows-sockets-in-mfc.md)   
 [Einfügeoperatoren](../mfc/reference/cobject-class.md#serialize)


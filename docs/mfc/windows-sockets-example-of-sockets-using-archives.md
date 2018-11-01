---
title: 'Windows Sockets: Beispiel für Sockets mithilfe der Archive'
ms.date: 11/04/2016
helpviewer_keywords:
- sockets [MFC], with archives
- examples [MFC], Windows Sockets
- Windows Sockets [MFC], with archives
ms.assetid: 2e3c9bb2-7e7b-4f28-8dc5-6cb7a484edac
ms.openlocfilehash: 285053c79b13ebea23aedc7dae52eabe85f55a12
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50436269"
---
# <a name="windows-sockets-example-of-sockets-using-archives"></a>Windows Sockets: Beispiel für Sockets mithilfe der Archive

Dieser Artikel enthält ein Beispiel der Verwendung der Klasse [CSocket](../mfc/reference/csocket-class.md). Das Beispiel setzt `CArchive` Objekte, die zum Serialisieren von Daten über einen Socket. Beachten Sie, dass es sich nicht um Dokumentserialisierung zu bzw. aus einer Datei handelt.

Im folgende Beispiel wird veranschaulicht, wie Sie das Archiv zum Senden und Empfangen von Daten über `CSocket` Objekte. Im Beispiel ist so konzipiert, dass zwei Instanzen der Anwendung (auf demselben Computer oder auf verschiedenen Computern im Netzwerk) Daten austauschen. Eine Instanz sendet Daten, die die andere Instanz empfängt und bestätigt. Entweder von Anwendung kann einen Austausch initiieren kann, und entweder als Server oder als Client auf die andere Anwendung. Die folgende Funktion ist in der Ansichtsklasse der Anwendung definiert:

[!code-cpp[NVC_MFCSimpleSocket#1](../mfc/codesnippet/cpp/windows-sockets-example-of-sockets-using-archives_1.cpp)]

Zu diesem Beispiel das wichtigste ist, dass die Struktur, die eine MFC-gleicht `Serialize` Funktion. Die `PacketSerialize` Memberfunktion besteht aus einer **Wenn** -Anweisung mit einer **else** Klausel. Die Funktion empfängt zwei [CArchive](../mfc/reference/carchive-class.md) Verweise als Parameter: *ArData* und *ArAck*. Wenn die *ArData* Archiv-Objekts wird festgelegt, für die Speicherung von (senden), die **Wenn** Branch ausgeführt wird; andernfalls, wenn *ArData* festgelegt ist für das Laden (empfangen) die Funktion nimmt die **else** Branch. Weitere Informationen über die Serialisierung in MFC finden Sie unter [Serialisierung](../mfc/how-to-make-a-type-safe-collection.md).

> [!NOTE]
>  Die *ArAck* Archivobjekt wird als das Gegenteil von *ArData*. Wenn *ArData* ist für das Senden von *ArAck* erhält, gilt das Gegenteil.

Zum Senden durchläuft die Beispielfunktion für eine angegebene Anzahl von Malen, jedes Mal generiert eine zufälligen Daten zu Demonstrationszwecken. Ihre Anwendung würde sich um echte Daten von einer Quelle, z. B. eine Datei abrufen. Die *ArData* Operator zum Einfügen des Archivs (**<<**) wird verwendet, um das Senden eines Datenstroms, der drei aufeinander folgenden Datenblöcke:

- Eine "Kopfzeile", der angibt, dass die Art der Daten (in diesem Fall den Wert des der *bValue* Variable und wie viele Kopien gesendet werden).

   Beide Elemente werden in diesem Beispiel nach dem Zufallsprinzip generiert.

- Die angegebene Anzahl von Kopien der Daten.

   Die innere **für** sendet eine Schleife *bValue* die angegebene Anzahl von Malen.

- Eine Zeichenfolge mit dem Namen *StrText* , die der Empfänger die Benutzer werden angezeigt.

Für den Empfang, die Funktion kann auf ähnliche Weise, außer dass mithilfe des Archivs Extraktionsoperator (**>>**) zum Abrufen von Daten aus dem Archiv. Die empfangende Anwendung die Daten empfängt, zeigt die endgültige Nachricht "Empfangen", und klicken Sie dann sendet eine Nachricht mit dem Text "Gesendet" zurück, die für die sendende Anwendung anzuzeigende überprüft wird.

In diesem Kommunikationsmodell das Wort "Empfangen", die Nachricht gesendet, der *StrText* Variable ist für die Anzeige am anderen Ende der Kommunikation, daher wird für den empfangenden Benutzer, dass eine bestimmte Anzahl von Datenpaketen wurden empfangen. Der Empfänger antwortet mit einer ähnlichen Zeichenfolge durchgeführt, die auf den ursprünglichen Absender Bildschirm "Gesendet", für die Anzeige besagt. Empfang der beiden Zeichenfolgen gibt an, dass erfolgreiche Kommunikation aufgetreten ist.

> [!CAUTION]
>  Wenn Sie eine MFC-Clientprogramm zur Kommunikation mit Servern mit eingerichteten (MFC-Fremd) schreiben, werden C++-Objekte über das Archiv nicht gesendet werden. Wenn der Server eine MFC-Anwendung, die die Arten von Objekten zu verstehen, die Sie senden möchten ist, ist es nicht empfangen und Deserialisieren Ihrer Objekte. Ein Beispiel in diesem Artikel [Windows Sockets: Bytereihenfolge](../mfc/windows-sockets-byte-ordering.md) zeigt eine Kommunikation dieses Typs.

Weitere Informationen finden Sie unter Windows Sockets-Spezifikation: **Htonl**, **Htons**, **Ntohl**, **Ntohs**. Darüber hinaus weitere Informationen finden Sie unter:

- [Windows-Sockets: Ableiten von Socket-Klassen](../mfc/windows-sockets-deriving-from-socket-classes.md)

- [Windows-Sockets: Wie Sockets mit Archiven arbeiten](../mfc/windows-sockets-how-sockets-with-archives-work.md)

- [Windows-Sockets: Hintergrund](../mfc/windows-sockets-background.md)

## <a name="see-also"></a>Siehe auch

[Windows-Sockets in MFC](../mfc/windows-sockets-in-mfc.md)<br/>
[CArchive::IsStoring](../mfc/reference/carchive-class.md#isstoring)<br/>
[CArchive::operator <<](../mfc/reference/carchive-class.md#operator_lt_lt)<br/>
[CArchive::operator >>](../mfc/reference/carchive-class.md#operator_lt_lt)<br/>
[CArchive::Flush](../mfc/reference/carchive-class.md#flush)<br/>
[CObject:: Serialize](../mfc/reference/cobject-class.md#serialize)


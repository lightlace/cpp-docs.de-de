---
title: 'Windows Sockets: Blockieren'
ms.date: 11/04/2016
helpviewer_keywords:
- Windows Sockets [MFC], stream sockets
- sockets [MFC], stream sockets
- stream sockets [MFC]
ms.assetid: 31faaa34-a995-493f-a30b-b8115293d619
ms.openlocfilehash: 298428bd5e81d11eb62907dfbac39acda24524f0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50560224"
---
# <a name="windows-sockets-stream-sockets"></a>Windows Sockets: Blockieren

Dieser Artikel beschreibt Streamsockets, eines der zwei Windows Socket-Typen. (Der andere Typ ist der [Datagrammsocket](../mfc/windows-sockets-datagram-sockets.md).)

Stream-Sockets Geben Sie für einen Datenfluss ohne datensatzbegrenzungen: ein Datenstrom von Bytes, die auch bidirektional sein kann (die Anwendung wird im Vollduplexmodus: es übertragen und kann über den Socket empfangen). Datenströme können zurückgegriffen werden, um sequenzierter, die nicht doppelten Daten zu übermitteln. ("Sequenziert" bedeutet, dass Pakete in der gesendeten Reihenfolge übermittelt werden. "Nicht dupliziert" bedeutet, dass Sie ein bestimmtes Paket nur einmal erhalten.) Der Empfang von definitiv und Datenströme eignen sich gut für die Verarbeitung großer Datenmengen.

Die Netzwerktransportschicht aufteilen oder Gruppieren von Daten in Pakete angemessene Größe. Die `CSocket` Klasse übernimmt das Packen und Entpacken Sie.

Streams basieren auf explizite Verbindungen: Socket ein anfordert, eine Verbindung mit der Socket B; B-Socket akzeptiert oder die Verbindung abgelehnt.

Ein Telefonanruf bietet eine gute Analogie für einen Stream. Unter normalen Umständen hört die empfangende Partei an, was Sie in der Reihenfolge sagen, dass Sie es, ohne Duplikate oder Verlust sagen. Stream-Sockets sind geeignet, z. B. für Implementierungen wie z. B. die FTP File Transfer Protocol (), die Übertragung ASCII- oder binäre Dateien beliebiger Größe erleichtert.

Stream-Sockets sind Datagrammsockets vorzuziehen, wenn Daten ankommen garantiert sein müssen und Daten sehr umfangreich sind. Weitere Informationen zu Streamsockets finden Sie unter der Windows Sockets-Spezifikation. Die Spezifikation ist im Windows SDK verfügbar.

Streamsockets kann besser als Anwendungen, die dafür ausgelegt, einen Datagrammsocket verwenden, für die Übertragung an alle empfangenden Sockets im Netzwerk, da sein

- Die broadcast-Modells unterliegt Netzwerkprobleme Flut (oder "Storm") ab.

- Das Client / Server-Modell, das anschließend übernommen ist effizienter.

- Das Stream-Modell bietet zuverlässige Datenübertragungen, in dem das Datagramm-Modell nicht der Fall ist.

- Das endgültige Modell nutzt die Möglichkeit für die Kommunikation zwischen Unicode und ANSI Socketanwendungen mit dieser Klasse, die CArchive CSocket-Klasse ist.

    > [!NOTE]
    >  Bei Verwendung der Klasse `CSocket`, müssen Sie einen Datenstrom verwenden. MFC-Assertion schlägt fehl, wenn Sie angeben, dass den Sockettyp als **SOCK_DGRAM**.

## <a name="see-also"></a>Siehe auch

[Windows-Sockets in MFC](../mfc/windows-sockets-in-mfc.md)<br/>
[Windows-Sockets: Hintergrund](../mfc/windows-sockets-background.md)


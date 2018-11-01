---
title: Vereinfachtes Erstellen von Internetclientanwendungen mit MFC
ms.date: 11/04/2016
helpviewer_keywords:
- Internet client applications [MFC], MFC
- Internet applications [MFC], MFC
- MFC, Internet applications
ms.assetid: 94437b3f-f15c-437d-b5fd-264a2efec9ab
ms.openlocfilehash: b288db54a020b0074766ee69debdb9f397d3bd03
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50573432"
---
# <a name="how-mfc-makes-it-easier-to-create-internet-client-applications"></a>Vereinfachtes Erstellen von Internetclientanwendungen mit MFC

Die Microsoft Foundation Classes kapseln die Win32-Internet (WinInet) Erweiterungsfunktionen in einer Weise, die für MFC-Programmierer vertrauten Kontext bereitstellt. MFC stellt drei Klassen von Internet-Datei ([CInternetFile](../mfc/reference/cinternetfile-class.md), [CHttpFile](../mfc/reference/chttpfile-class.md), und [CGopherFile](../mfc/reference/cgopherfile-class.md)) abgeleitet, die von der [CStdioFile](../mfc/reference/cstdiofile-class.md) Klasse . Nicht nur diese Klassen machen abrufen und Bearbeiten von Daten für das Internet Programmierer, die hätte `CStdioFile` für lokale Dateien, jedoch mit diesen Klassen Sie können lokale Dateien und Internet-Dateien in behandelt konsistent und transparent.

Die MFC-WinInet-Klassen bieten die gleiche Funktionalität wie `CStdioFile` für Daten, die über das Internet übertragen werden. Diese Klassen abstrahieren die Internetprotokolle für HTTP, FTP und Gopher in einer allgemeinen Anwendung Programmierschnittstelle, die einen schnellen und einfachen Pfad zum Herstellen der Internet-fähige Anwendungen bereitstellen. Z. B. Verbindungen mit einem FTP-Server weiterhin erfordert mehrere Schritte auf niedriger Ebene, aber als MFC-Entwickler, müssen Sie nur einen Aufruf an `CInternetSession::GetFTPConnection` um diese Verbindung zu erstellen.

Darüber hinaus bieten die MFC-WinInet-Klassen die folgenden Vorteile:

- Gepufferte e/a

- Typsichere Handles für Ihre Daten

- Standardparameter für viele Funktionen

- Ausnahmebehandlung für common Internet-Fehler

- Die automatische Bereinigung von geöffneten Handles und Verbindungen

## <a name="see-also"></a>Siehe auch

[Win32-Interneterweiterungen (WinInet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[Vereinfachtes Erstellen von Internetclientanwendungen mit WinInet](../mfc/how-wininet-makes-it-easier-to-create-internet-client-applications.md)


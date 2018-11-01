---
title: Schreiben einer Internetclientanwendung mithilfe von MFC-WinInet-Klassen
ms.date: 11/04/2016
helpviewer_keywords:
- Internet client applications [MFC]
- WinInet classes [MFC], programming
- Internet client applications [MFC], writing
- Internet applications [MFC], WinInet
- Internet applications [MFC], client applications
- MFC, Internet applications
ms.assetid: a2c4a40c-a94e-4b3e-9dbf-f8a8dc8e5428
ms.openlocfilehash: 041fa90b030edd9b5324c183b0153a8a062735da
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50494964"
---
# <a name="writing-an-internet-client-application-using-mfc-wininet-classes"></a>Schreiben einer Internetclientanwendung mithilfe von MFC-WinInet-Klassen

Jede Clientanwendung für Internet basiert auf der Internet-Sitzung. MFC implementiert internetsitzungen als Objekte der Klasse [CInternetSession](../mfc/reference/cinternetsession-class.md). Diese Klasse verwenden, können Sie eine Internet-Sitzung oder mehrere gleichzeitige Sitzungen erstellen.

Mit einem Server kommunizieren kann, müssen Sie eine [CInternetConnection](../mfc/reference/cinternetconnection-class.md) Objekt sowie einen `CInternetSession`. Sie erstellen eine `CInternetConnection` mit [CInternetSession:: GetFTPConnection](../mfc/reference/cinternetsession-class.md#getftpconnection), [CInternetSession:: GetHttpConnection](../mfc/reference/cinternetsession-class.md#gethttpconnection), oder [CInternetSession:: GetGopherConnection](../mfc/reference/cinternetsession-class.md#getgopherconnection). Jede dieser Aufrufe ist spezifisch für den Protokolltyp. Diese Aufrufe öffnen eine Datei auf dem Server für das Lesen oder Schreiben nicht. Wenn Sie Daten lesen oder schreiben möchten, müssen Sie die Datei als separaten Schritt öffnen.

Für die meisten Internet-Sitzungen die `CInternetSession` Objekt funktioniert Hand in Hand mit einem [CInternetFile](../mfc/reference/cinternetfile-class.md) Objekt:

- Bei einer internetsitzung müssen Sie eine Instanz von erstellen [CInternetSession](../mfc/reference/cinternetsession-class.md).

- Wenn es sich bei die Internet-Sitzung Daten liest oder schreibt, müssen Sie eine Instanz von erstellen `CInternetFile` (oder dessen Unterklassen, [CHttpFile](../mfc/reference/chttpfile-class.md) oder [CGopherFile](../mfc/reference/cgopherfile-class.md)). Die einfachste Möglichkeit zum Lesen von Daten aufgerufen wird [OpenURL](../mfc/reference/cinternetsession-class.md#openurl). Diese Funktion analysiert eine von Ihnen bereitgestellten Universal Resource Locator (URL), öffnet eine Verbindung mit dem Server, die durch die URL angegeben, und gibt eine schreibgeschützte `CInternetFile` Objekt. `CInternetSession::OpenURL` ist nicht spezifisch für ein Protokolltyp, der gleiche Aufruf für jeden Gopher, HTTP oder FTP-URL funktioniert. `CInternetSession::OpenURL` arbeitet auch mit lokalen Dateien (Rückgabe einer `CStdioFile` anstelle von einer `CInternetFile`).

- Wenn Ihre Internet-Sitzung nicht lesen oder Schreiben von Daten, führt jedoch andere Aufgaben, z. B. Löschen einer Datei in einem FTP-Verzeichnis, müssen Sie möglicherweise nicht zum Erstellen einer Instanz von `CInternetFile`.

Es gibt zwei Möglichkeiten zum Erstellen einer `CInternetFile` Objekt:

- Bei Verwendung von `CInternetSession::OpenURL` zum Herstellen der Serververbindung Ihrer, den Aufruf von `OpenURL` gibt eine `CStdioFile`.

- Wenn verwenden `CInternetSession::GetFtpConnection`, `GetGopherConnection`, oder `GetHttpConnection` um die Serververbindung herzustellen, müssen Sie aufrufen `CFtpConnection::OpenFile`, `CGopherConnection::OpenFile`, oder `CHttpConnection::OpenRequest`jeweils zurückzugebenden eine `CInternetFile`, `CGopherFile`, oder `CHttpFile`, bzw.

Die Schritte zum Implementieren einer Internetclientanwendung variieren, je nachdem, ob Sie basierend auf einem generischen Internetclient erstellen `OpenURL` oder einen protokollspezifischen-Client mithilfe eines der `GetConnection` Funktionen.

## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren

- [Wie schreibe ich eine Internet-Clientanwendung, die allgemein mit FTP, HTTP und Gopher funktioniert](../mfc/steps-in-a-typical-internet-client-application.md)

- [Wie schreibe ich eine FTP-Clientanwendung, die eine Datei geöffnet wird](../mfc/steps-in-a-typical-ftp-client-application.md)

- [Wie schreibe ich eine FTP-Clientanwendung, die eine Datei nicht geöffnet, aber führt eine Directory Operation, z. B. eine Datei löschen](../mfc/steps-in-a-typical-ftp-client-application-to-delete-a-file.md)

- [Wie schreibe ich eine Gopher-Clientanwendung](../mfc/steps-in-a-typical-gopher-client-application.md)

- [Wie schreibe ich eine HTTP-Client-Anwendung](../mfc/steps-in-a-typical-http-client-application.md)

## <a name="see-also"></a>Siehe auch

[Win32-Interneterweiterungen (WinInet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[MFC-Klassen für das Erstellen von Internetclientanwendungen](../mfc/mfc-classes-for-creating-internet-client-applications.md)<br/>
[Voraussetzungen für Internetclientklassen](../mfc/prerequisites-for-internet-client-classes.md)

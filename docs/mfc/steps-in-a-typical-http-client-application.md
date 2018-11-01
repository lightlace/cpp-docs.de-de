---
title: Schritte in einer typischen HTTP-Clientanwendung
ms.date: 11/04/2016
helpviewer_keywords:
- HTTP client applications [MFC]
- client applications [MFC], HTTP
- Internet applications [MFC], HTTP client applications
- applications [MFC], HTTP client
- Internet client applications [MFC], HTTP table
- WinInet classes [MFC], HTTP
ms.assetid: f86552e8-8acd-4b23-bdc5-0c3a247ebd74
ms.openlocfilehash: a73d220f4ab7f58960ccfe4b09f98f0cd0956406
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50630788"
---
# <a name="steps-in-a-typical-http-client-application"></a>Schritte in einer typischen HTTP-Clientanwendung

Die folgende Tabelle zeigt die Schritte aus, dass Sie in einer typischen HTTP-Client-Anwendung ausführen können:

|Ihr Ziel|Maßnahmen ergreifen|Effekte|
|---------------|----------------------|-------------|
|Beginnen Sie eine HTTP-Sitzung.|Erstellen Sie eine [CInternetSession](../mfc/reference/cinternetsession-class.md) Objekt.|WinInet initialisiert, und eine Verbindung mit dem Server her.|
|Verbinden Sie mit einem HTTP-Server.|Verwendung [CInternetSession:: GetHttpConnection](../mfc/reference/cinternetsession-class.md#gethttpconnection).|Gibt eine [CHttpConnection](../mfc/reference/chttpconnection-class.md) Objekt.|
|Öffnen Sie eine HTTP-Anforderung.|Verwendung [CHttpConnection:: OpenRequest](../mfc/reference/chttpconnection-class.md#openrequest).|Gibt eine [CHttpFile](../mfc/reference/chttpfile-class.md) Objekt.|
|Senden Sie eine HTTP-Anforderung.|Verwendung [CHttpFile:: AddRequestHeaders](../mfc/reference/chttpfile-class.md#addrequestheaders) und [CHttpFile:: SendRequest](../mfc/reference/chttpfile-class.md#sendrequest).|Sucht nach der Datei. Gibt FALSE zurück, wenn die Datei nicht gefunden wird.|
|Aus der Datei gelesen.|Verwendung [CHttpFile](../mfc/reference/chttpfile-class.md).|Liest die angegebene Anzahl von Bytes, die unter Verwendung eines Puffers, die, das Sie angeben.|
|Behandeln von Ausnahmen|Verwenden der [CInternetException](../mfc/reference/cinternetexception-class.md) Klasse.|Alle allgemeine Arten von Internet-Ausnahme behandelt werden.|
|Die HTTP-Sitzung zu beenden.|Löschen der [CInternetSession](../mfc/reference/cinternetsession-class.md) Objekt.|Automatisch bereinigt offenen Dateihandles und Verbindungen.|

## <a name="see-also"></a>Siehe auch

[Win32-Interneterweiterungen (WinInet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[Voraussetzungen für Internetclientklassen](../mfc/prerequisites-for-internet-client-classes.md)<br/>
[Schreiben einer Internetclientanwendung mithilfe von MFC-WinInet-Klassen](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)

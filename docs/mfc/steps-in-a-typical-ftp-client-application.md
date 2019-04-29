---
title: Schritte in einer typischen FTP-Clientanwendung
ms.date: 11/04/2016
helpviewer_keywords:
- Internet client applications [MFC], FTP table
- FTP (File Transfer Protocol)
- WinInet classes [MFC], FTP
- FTP (File Transfer Protocol) [MFC], client applications
- Internet applications [MFC], FTP client applications
ms.assetid: 70bed7b5-6040-40d1-bc77-702e63a698f2
ms.openlocfilehash: d08edf704e748767f3b566252ad328baf40b55ea
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62307015"
---
# <a name="steps-in-a-typical-ftp-client-application"></a>Schritte in einer typischen FTP-Clientanwendung

Eine typische Anwendung des FTP-Client erstellt eine [CInternetSession](../mfc/reference/cinternetsession-class.md) und ein [CFtpConnection](../mfc/reference/cftpconnection-class.md) Objekt. Beachten Sie, dass diese MFC-WinInet-Klassen nicht tatsächlich die Proxyeinstellungen des Typs steuert. IIS führt.

Die folgende Tabelle zeigt die Schritte, die Sie in einer typischen FTP-Client-Anwendung ausführen können.

|Ihr Ziel|Maßnahmen ergreifen|Effekte|
|---------------|----------------------|-------------|
|Beginnen Sie eine FTP-Sitzung.|Erstellen Sie eine [CInternetSession](../mfc/reference/cinternetsession-class.md) Objekt.|WinInet initialisiert, und eine Verbindung mit dem Server her.|
|Verbinden Sie mit einem FTP-Server.|Verwendung [CInternetSession:: GetFTPConnection](../mfc/reference/cinternetsession-class.md#getftpconnection).|Gibt eine [CFtpConnection](../mfc/reference/cftpconnection-class.md) Objekt.|
|Ändern Sie in eine neue FTP-Verzeichnis auf dem Server.|Verwendung [CFtpConnection:: SetCurrentDirectory](../mfc/reference/cftpconnection-class.md#setcurrentdirectory).|Ändert das Verzeichnis, das Sie zurzeit auf dem Server verbunden sind.|
|Suchen Sie die erste Datei im FTP-Verzeichnis.|Verwendung [CFtpFileFind:: FindFile](../mfc/reference/cftpfilefind-class.md#findfile).|Sucht nach der ersten Datei aus. Gibt FALSE zurück, wenn keine Dateien gefunden werden.|
|Suchen Sie die nächste Datei im FTP-Verzeichnis.|Verwendung [CFtpFileFind:: FindNextFile](../mfc/reference/cftpfilefind-class.md#findnextfile).|Sucht nach der nächsten Datei. Gibt FALSE zurück, wenn die Datei nicht gefunden wird.|
|Öffnen Sie die Datei gefundenen `FindFile` oder `FindNextFile` zum Lesen oder schreiben.|Verwendung [CFtpConnection:: OpenFile](../mfc/reference/cftpconnection-class.md#openfile), mit dem Namen der von zurückgegebene [FindFile](../mfc/reference/cftpfilefind-class.md#findfile) oder [FindNextFile](../mfc/reference/cftpfilefind-class.md#findnextfile).|Öffnet die Datei auf dem Server für das Lesen oder schreiben. Gibt eine [CInternetFile](../mfc/reference/cinternetfile-class.md) Objekt.|
|Lesen oder Schreiben in die Datei.|Verwendung [CInternetFile:: Read](../mfc/reference/cinternetfile-class.md#read) oder [CInternetFile:: Write](../mfc/reference/cinternetfile-class.md#write).|Liest oder schreibt die angegebene Anzahl von Bytes, die unter Verwendung eines Puffers, die, das Sie angeben.|
|Behandeln von Ausnahmen|Verwenden der [CInternetException](../mfc/reference/cinternetexception-class.md) Klasse.|Alle allgemeine Arten von Internet-Ausnahme behandelt werden.|
|Die FTP-Sitzung zu beenden.|Löschen der [CInternetSession](../mfc/reference/cinternetsession-class.md) Objekt.|Automatisch bereinigt offenen Dateihandles und Verbindungen.|

## <a name="see-also"></a>Siehe auch

[Win32-Interneterweiterungen (WinInet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[Voraussetzungen für Internetclientklassen](../mfc/prerequisites-for-internet-client-classes.md)<br/>
[Schreiben einer Internetclientanwendung mithilfe von MFC-WinInet-Klassen](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)

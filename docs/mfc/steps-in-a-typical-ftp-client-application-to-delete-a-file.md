---
title: Die Schritte in einer Typischen FTP-Clientanwendung zum Löschen einer Datei | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Internet client applications [MFC], FTP delete
- WinInet classes [MFC], FTP
- FTP (File Transfer Protocol) [MFC], client applications
- Internet applications [MFC], FTP client applications
ms.assetid: 2c347a96-c0a4-4827-98fe-668406e552bc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1d1db3418aa96fa779ac3341e12d90d66ba657c4
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46384532"
---
# <a name="steps-in-a-typical-ftp-client-application-to-delete-a-file"></a>Schritte zum Löschen einer Datei in einer typischen FTP-Clientanwendung

Die folgende Tabelle zeigt die Schritte, die Sie in einer typischen FTP-Client-Anwendung ausführen können, die eine Datei löscht.

|Ihr Ziel|Maßnahmen ergreifen|Effekte|
|---------------|----------------------|-------------|
|Beginnen Sie eine FTP-Sitzung.|Erstellen Sie eine [CInternetSession](../mfc/reference/cinternetsession-class.md) Objekt.|WinInet initialisiert, und eine Verbindung mit dem Server her.|
|Verbinden Sie mit einem FTP-Server.|Verwendung [CInternetSession:: GetFTPConnection](../mfc/reference/cinternetsession-class.md#getftpconnection).|Gibt eine [CFtpConnection](../mfc/reference/cftpconnection-class.md) Objekt.|
|Überprüfen Sie, dass Sie in das richtige Verzeichnis auf dem FTP-Server sind.|Verwendung [CFtpConnection:: GetCurrentDirectory](../mfc/reference/cftpconnection-class.md#getcurrentdirectory) oder [CFtpConnection::GetCurrentDirectoryAsURL](../mfc/reference/cftpconnection-class.md#getcurrentdirectoryasurl).|Gibt den Namen oder die URL des Verzeichnisses an, die Sie derzeit auf dem Server, abhängig von der ausgewählten Memberfunktion verbunden sind.|
|Ändern Sie in eine neue FTP-Verzeichnis auf dem Server.|Verwendung [CFtpConnection:: SetCurrentDirectory](../mfc/reference/cftpconnection-class.md#setcurrentdirectory).|Ändert das Verzeichnis, das Sie zurzeit auf dem Server verbunden sind.|
|Suchen Sie die erste Datei im FTP-Verzeichnis.|Verwendung [CFtpFileFind:: FindFile](../mfc/reference/cftpfilefind-class.md#findfile).|Sucht nach der ersten Datei aus. Gibt FALSE zurück, wenn keine Dateien gefunden werden.|
|Suchen Sie die nächste Datei im FTP-Verzeichnis.|Verwendung [CFtpFileFind:: FindNextFile](../mfc/reference/cftpfilefind-class.md#findnextfile).|Sucht nach der nächsten Datei. Gibt FALSE zurück, wenn die Datei nicht gefunden wird.|
|Löschen Sie die Datei gefundenen `FindFile` oder `FindNextFile`.|Verwendung [CFtpConnection:: Remove](../mfc/reference/cftpconnection-class.md#remove), mit dem Namen der von zurückgegebene `FindFile` oder `FindNextFile`.|Löscht die Datei auf dem Server für das Lesen oder schreiben.|
|Behandeln von Ausnahmen|Verwenden der [CInternetException](../mfc/reference/cinternetexception-class.md) Klasse.|Alle allgemeine Arten von Internet-Ausnahme behandelt werden.|
|Die FTP-Sitzung zu beenden.|Löschen der [CInternetSession](../mfc/reference/cinternetsession-class.md) Objekt.|Automatisch bereinigt offenen Dateihandles und Verbindungen.|

## <a name="see-also"></a>Siehe auch

[Win32-Interneterweiterungen (WinInet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[Voraussetzungen für Internetclientklassen](../mfc/prerequisites-for-internet-client-classes.md)<br/>
[Schreiben einer Internetclientanwendung mithilfe von MFC-WinInet-Klassen](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)

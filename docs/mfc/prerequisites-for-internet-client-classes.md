---
title: Voraussetzungen für Internetclientklassen
ms.date: 11/04/2016
helpviewer_keywords:
- Internet files [MFC], writing to
- Internet [MFC], connections
- FTP (File Transfer Protocol), MFC classes
- Gopher prerequisites [MFC]
- files [MFC], writing to
- classes [MFC], connections
- HTTP [MFC], prerequisites for Internet clients
- connections [MFC], classes for
- Internet client class prerequisites [MFC]
- files [MFC], reading
- URLs [MFC], Internet client applications
- prerequisites, Internet client classes [MFC]
- Gopher client applications [MFC]
ms.assetid: c51d1dfe-260c-4228-8100-e4efd90e9599
ms.openlocfilehash: 6246db7dfb2837f5d94fa51f8433b46722c43663
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57267744"
---
# <a name="prerequisites-for-internet-client-classes"></a>Voraussetzungen für Internetclientklassen

Einige Aktionen, die, die von einem Internetclient (z. B. Lesen einer Datei) über die erforderliche Aktionen (in diesem Fall eine Internetverbindung herstellen) verfügen. Die folgenden Tabellen enthalten die erforderlichen Komponenten für einige Clientaktionen.

### <a name="general-internet-url-ftp-gopher-or-http"></a>Allgemeine Internet-URL (FTP, Gopher oder HTTP)

|Aktion|Vorbereitungsmaßnahme|
|------------|------------------|
|Eine Verbindung herstellen.|Erstellen Sie eine [CInternetSession](../mfc/reference/cinternetsession-class.md) zu, um die Grundlage für eine Internetclientanwendung herzustellen.|
|Öffnen Sie eine URL ein.|Eine Verbindung herstellen. Rufen Sie [OpenURL](../mfc/reference/cinternetsession-class.md#openurl). Die `OpenURL` Funktion gibt eine schreibgeschützte-Objekt zurück.|
|Lesen von URL-Daten.|Öffnen Sie die URL ein. Rufen Sie [CInternetFile:: Read](../mfc/reference/cinternetfile-class.md#read).|
|Legen Sie eine Internetoption.|Eine Verbindung herstellen. Rufen Sie [CInternetSession:: SetOption](../mfc/reference/cinternetsession-class.md#setoption).|
|Legen Sie eine Funktion, die mit Statusinformationen aufgerufen werden.|Eine Verbindung herstellen. Rufen Sie [CInternetSession:: EnableStatusCallback](../mfc/reference/cinternetsession-class.md#enablestatuscallback). Außer Kraft setzen [CInternetSession:: OnStatusCallback](../mfc/reference/cinternetsession-class.md#onstatuscallback) Aufrufe zu behandeln.|

### <a name="ftp"></a>FTP

|Aktion|Vorbereitungsmaßnahme|
|------------|------------------|
|Herstellen einer FTP-Verbindungs an.|Erstellen Sie eine [CInternetSession](../mfc/reference/cinternetsession-class.md) als Grundlage für diese Internet-Clientanwendung. Rufen Sie [CInternetSession:: GetFTPConnection](../mfc/reference/cinternetsession-class.md#getftpconnection) zum Erstellen einer [CFtpConnection](../mfc/reference/cftpconnection-class.md) Objekt.|
|Suchen Sie nach der ersten Ressource.|Herstellen einer FTP-Verbindungs an. Erstellen Sie eine [CFtpFileFind](../mfc/reference/cftpfilefind-class.md) Objekt. Rufen Sie [CFtpFileFind:: FindFile](../mfc/reference/cftpfilefind-class.md#findfile).|
|Auflisten Sie aller verfügbaren Ressourcen.|Suchen Sie die erste Datei ein. Rufen Sie [CFtpFileFind:: FindNextFile](../mfc/reference/cftpfilefind-class.md#findnextfile) bis "false" zurückgegeben.|
|Öffnen Sie eine FTP-Datei.|Herstellen einer FTP-Verbindungs an. Rufen Sie [CFtpConnection:: OpenFile](../mfc/reference/cftpconnection-class.md#openfile) zum Erstellen und Öffnen einer [CInternetFile](../mfc/reference/cinternetfile-class.md) Objekt.|
|Lesen Sie eine FTP-Datei.|Öffnen Sie eine FTP-Datei mit Lesezugriff. Rufen Sie [CInternetFile:: Read](../mfc/reference/cinternetfile-class.md#read).|
|Schreiben Sie in eine FTP-Datei.|Öffnen Sie eine FTP-Datei mit Schreibzugriff. Rufen Sie [CInternetFile:: Write](../mfc/reference/cinternetfile-class.md#write).|
|Wechseln des Clients auf dem Server.|Herstellen einer FTP-Verbindungs an. Rufen Sie [CFtpConnection:: SetCurrentDirectory](../mfc/reference/cftpconnection-class.md#setcurrentdirectory).|
|Rufen Sie aktuelle Verzeichnis des Clients, auf dem Server.|Herstellen einer FTP-Verbindungs an. Rufen Sie [CFtpConnection:: GetCurrentDirectory](../mfc/reference/cftpconnection-class.md#getcurrentdirectory).|

### <a name="http"></a>HTTP

|Aktion|Vorbereitungsmaßnahme|
|------------|------------------|
|Richten Sie eine HTTP-Verbindung.|Erstellen Sie eine [CInternetSession](../mfc/reference/cinternetsession-class.md) als Grundlage für diese Internet-Clientanwendung. Rufen Sie [CInternetSession:: GetHttpConnection](../mfc/reference/cinternetsession-class.md#gethttpconnection) zum Erstellen einer [CHttpConnection](../mfc/reference/chttpconnection-class.md) Objekt.|
|Öffnen Sie eine HTTP-Datei.|Richten Sie eine HTTP-Verbindung. Rufen Sie [CHttpConnection:: OpenRequest](../mfc/reference/chttpconnection-class.md#openrequest) zum Erstellen einer [CHttpFile](../mfc/reference/chttpfile-class.md) Objekt. Rufen Sie [CHttpFile:: AddRequestHeaders](../mfc/reference/chttpfile-class.md#addrequestheaders). Rufen Sie [CHttpFile:: SendRequest](../mfc/reference/chttpfile-class.md#sendrequest).|
|Lesen Sie eine HTTP-Datei.|Öffnen Sie eine HTTP-Datei. Rufen Sie [CInternetFile:: Read](../mfc/reference/cinternetfile-class.md#read).|
|Abrufen von Informationen über eine HTTP-Anforderung.|Richten Sie eine HTTP-Verbindung. Rufen Sie [CHttpConnection:: OpenRequest](../mfc/reference/chttpconnection-class.md#openrequest) zum Erstellen einer [CHttpFile](../mfc/reference/chttpfile-class.md) Objekt. Call [CHttpFile::QueryInfo](../mfc/reference/chttpfile-class.md#queryinfo).|

### <a name="gopher"></a>Gopher

|Aktion|Vorbereitungsmaßnahme|
|------------|------------------|
|Eine Gopherverbindung herstellen.|Erstellen Sie eine [CInternetSession](../mfc/reference/cinternetsession-class.md) als Grundlage für diese Internet-Clientanwendung. Rufen Sie [CInternetSession:: GetGopherConnection](../mfc/reference/cinternetsession-class.md#getgopherconnection) zum Erstellen einer [CGopherConnection](../mfc/reference/cgopherconnection-class.md).|
|Suchen Sie die erste Datei im aktuellen Verzeichnis.|Eine Gopherverbindung herstellen. Erstellen Sie eine [CGopherFileFind](../mfc/reference/cgopherfilefind-class.md) Objekt. Rufen Sie [CGopherConnection:: CreateLocator](../mfc/reference/cgopherconnection-class.md#createlocator) zum Erstellen einer [CGopherLocator](../mfc/reference/cgopherlocator-class.md) Objekt. Übergeben Sie den Locator für [CGopherFileFind:: FindFile](../mfc/reference/cgopherfilefind-class.md#findfile). Rufen Sie [CGopherFileFind:: GetLocator](../mfc/reference/cgopherfilefind-class.md#getlocator) des Locators einer Datei zu erhalten, wenn Sie es später benötigen.|
|Auflisten Sie aller verfügbaren Dateien an.|Suchen Sie die erste Datei ein. Rufen Sie [CGopherFileFind:: FindNextFile](../mfc/reference/cgopherfilefind-class.md#findnextfile) bis "false" zurückgegeben.|
|Öffnen Sie eine Gopherdatei.|Eine Gopherverbindung herstellen. Erstellen Sie mit [CGopherConnection:: CreateLocator](../mfc/reference/cgopherconnection-class.md#createlocator) oder suchen Sie einen Locator mit [CGopherFileFind:: GetLocator](../mfc/reference/cgopherfilefind-class.md#getlocator). Rufen Sie [CGopherConnection:: OpenFile](../mfc/reference/cgopherconnection-class.md#openfile).|
|Lesen einer Gopherdatei an.|Öffnen Sie eine Gopherdatei. Verwendung [CGopherFile](../mfc/reference/cgopherfile-class.md).|

## <a name="see-also"></a>Siehe auch

[Win32-Interneterweiterungen (WinInet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[MFC-Klassen für das Erstellen von Internetclientanwendungen](../mfc/mfc-classes-for-creating-internet-client-applications.md)<br/>
[Schreiben einer Internetclientanwendung mithilfe von MFC-WinInet-Klassen](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)

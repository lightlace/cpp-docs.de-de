---
title: "Voraussetzungen für Internetclientklassen | Microsoft Docs"
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 77d73ef71854753ffd561053cc71509c7654d33b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="prerequisites-for-internet-client-classes"></a>Voraussetzungen für Internetclientklassen
Einige Aktionen, die von einem Internetclient (z. B. beim Lesen von einer Datei) verfügen über erforderliche Aktionen (in diesem Fall eine Internetverbindung herstellen). Die folgenden Tabellen enthalten die erforderlichen Komponenten für einige Clientaktionen.  
  
### <a name="general-internet-url-ftp-gopher-or-http"></a>Allgemeiner Internet-URL (FTP, Gopher oder HTTP)  
  
|Aktion|Vorbereitungsmaßnahme|  
|------------|------------------|  
|Stellen Sie eine Verbindung her.|Erstellen einer [CInternetSession](../mfc/reference/cinternetsession-class.md) die Basis einer Internetclientanwendung herstellen.|  
|Öffnen Sie eine URL ein.|Stellen Sie eine Verbindung her. Rufen Sie [OpenURL](../mfc/reference/cinternetsession-class.md#openurl). Die `OpenURL` Funktion gibt ein Ressourcenobjekt auf schreibgeschützt.|  
|Lesen von URL-Daten.|Öffnen Sie die URL ein. Rufen Sie [CInternetFile:: Read](../mfc/reference/cinternetfile-class.md#read).|  
|Festlegen Sie eine Internetoption.|Stellen Sie eine Verbindung her. Rufen Sie [CInternetSession:: SetOption](../mfc/reference/cinternetsession-class.md#setoption).|  
|Legen Sie eine Funktion, die mit Statusinformationen aufgerufen wird.|Stellen Sie eine Verbindung her. Rufen Sie [CInternetSession:: EnableStatusCallback](../mfc/reference/cinternetsession-class.md#enablestatuscallback). Überschreiben Sie [CInternetSession:: OnStatusCallback](../mfc/reference/cinternetsession-class.md#onstatuscallback) Aufrufe zu behandeln.|  
  
### <a name="ftp"></a>FTP  
  
|Aktion|Vorbereitungsmaßnahme|  
|------------|------------------|  
|Stellen Sie eine FTP-Verbindung her.|Erstellen einer [CInternetSession](../mfc/reference/cinternetsession-class.md) als Grundlage für diese Internetclientanwendung. Rufen Sie [CInternetSession:: GetFTPConnection](../mfc/reference/cinternetsession-class.md#getftpconnection) zum Erstellen einer [CFtpConnection](../mfc/reference/cftpconnection-class.md) Objekt.|  
|Suchen Sie die erste Ressource an.|Stellen Sie eine FTP-Verbindung her. Erstellen einer [CFtpFileFind](../mfc/reference/cftpfilefind-class.md) Objekt. Rufen Sie [CFtpFileFind:: FindFile](../mfc/reference/cftpfilefind-class.md#findfile).|  
|Auflisten Sie aller verfügbaren Ressourcen.|Suchen Sie die erste Datei ein. Rufen Sie [CFtpFileFind:: FindNextFile](../mfc/reference/cftpfilefind-class.md#findnextfile) bis "false" zurückgegeben.|  
|Öffnen Sie eine FTP-Datei.|Stellen Sie eine FTP-Verbindung her. Rufen Sie [CFtpConnection:: OpenFile](../mfc/reference/cftpconnection-class.md#openfile) zum Erstellen und Öffnen einer [CInternetFile](../mfc/reference/cinternetfile-class.md) Objekt.|  
|Eine FTP-Datei zu lesen.|Öffnen Sie eine FTP-Datei mit Lesezugriff. Rufen Sie [CInternetFile:: Read](../mfc/reference/cinternetfile-class.md#read).|  
|Schreiben Sie in eine FTP-Datei.|Öffnen Sie eine FTP-Datei mit Schreibzugriff. Rufen Sie [CInternetFile:: Write](../mfc/reference/cinternetfile-class.md#write).|  
|Ändern Sie das Clientverzeichnis auf dem Server.|Stellen Sie eine FTP-Verbindung her. Rufen Sie [CFtpConnection:: SetCurrentDirectory](../mfc/reference/cftpconnection-class.md#setcurrentdirectory).|  
|Rufen Sie aktuelle Clientverzeichnis auf dem Server.|Stellen Sie eine FTP-Verbindung her. Rufen Sie [CFtpConnection:: GetCurrentDirectory](../mfc/reference/cftpconnection-class.md#getcurrentdirectory).|  
  
### <a name="http"></a>HTTP  
  
|Aktion|Vorbereitungsmaßnahme|  
|------------|------------------|  
|Eine HTTP-Verbindung herstellen.|Erstellen einer [CInternetSession](../mfc/reference/cinternetsession-class.md) als Grundlage für diese Internetclientanwendung. Rufen Sie [CInternetSession:: GetHttpConnection](../mfc/reference/cinternetsession-class.md#gethttpconnection) zum Erstellen einer [CHttpConnection](../mfc/reference/chttpconnection-class.md) Objekt.|  
|Öffnen Sie eine HTTP-Datei.|Eine HTTP-Verbindung herstellen. Rufen Sie [CHttpConnection:: OpenRequest](../mfc/reference/chttpconnection-class.md#openrequest) zum Erstellen einer [CHttpFile](../mfc/reference/chttpfile-class.md) Objekt. Rufen Sie [CHttpFile:: AddRequestHeaders](../mfc/reference/chttpfile-class.md#addrequestheaders). Rufen Sie [CHttpFile:: SendRequest](../mfc/reference/chttpfile-class.md#sendrequest).|  
|Eine HTTP-Datei zu lesen.|Öffnen Sie eine HTTP-Datei. Rufen Sie [CInternetFile:: Read](../mfc/reference/cinternetfile-class.md#read).|  
|Abrufen von Informationen über eine HTTP-Anforderung.|Eine HTTP-Verbindung herstellen. Rufen Sie [CHttpConnection:: OpenRequest](../mfc/reference/chttpconnection-class.md#openrequest) zum Erstellen einer [CHttpFile](../mfc/reference/chttpfile-class.md) Objekt. Rufen Sie [CHttpFile::](../mfc/reference/chttpfile-class.md#queryinfo).|  
  
### <a name="gopher"></a>Gopher  
  
|Aktion|Vorbereitungsmaßnahme|  
|------------|------------------|  
|Erstellen einer Gopherverbindung.|Erstellen einer [CInternetSession](../mfc/reference/cinternetsession-class.md) als Grundlage für diese Internetclientanwendung. Rufen Sie [CInternetSession:: GetGopherConnection](../mfc/reference/cinternetsession-class.md#getgopherconnection) zum Erstellen einer [CGopherConnection](../mfc/reference/cgopherconnection-class.md).|  
|Suchen Sie die erste Datei im aktuellen Verzeichnis.|Erstellen einer Gopherverbindung. Erstellen einer [CGopherFileFind](../mfc/reference/cgopherfilefind-class.md) Objekt. Rufen Sie [CGopherConnection:: CreateLocator](../mfc/reference/cgopherconnection-class.md#createlocator) zum Erstellen einer [CGopherLocator](../mfc/reference/cgopherlocator-class.md) Objekt. Übergeben Sie den Serverlocatorpunkt auf [CGopherFileFind:: FindFile](../mfc/reference/cgopherfilefind-class.md#findfile). Rufen Sie [CGopherFileFind:: GetLocator](../mfc/reference/cgopherfilefind-class.md#getlocator) des Locators einer Datei abrufen, wenn Sie ihn später benötigen.|  
|Auflisten Sie aller verfügbaren Dateien an.|Suchen Sie die erste Datei ein. Rufen Sie [CGopherFileFind:: FindNextFile](../mfc/reference/cgopherfilefind-class.md#findnextfile) bis "false" zurückgegeben.|  
|Öffnen Sie eine Gopherdatei.|Erstellen einer Gopherverbindung. Erstellen Sie einen Gopher-Locator mit [CGopherConnection:: CreateLocator](../mfc/reference/cgopherconnection-class.md#createlocator) oder suchen Sie einen Locator mit [CGopherFileFind:: GetLocator](../mfc/reference/cgopherfilefind-class.md#getlocator). Rufen Sie [CGopherConnection:: OpenFile](../mfc/reference/cgopherconnection-class.md#openfile).|  
|Gopherdatei zu lesen.|Öffnen Sie eine Gopherdatei. Verwendung [CGopherFile](../mfc/reference/cgopherfile-class.md).|  
  
## <a name="see-also"></a>Siehe auch  
 [Win32-Interneterweiterungen (WinInet)](../mfc/win32-internet-extensions-wininet.md)   
 [Mfc_klassen zum Erstellen von Internetclientanwendungen](../mfc/mfc-classes-for-creating-internet-client-applications.md)   
 [Schreiben einer Internetclientanwendung mithilfe von MFC-WinInet-Klassen](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)

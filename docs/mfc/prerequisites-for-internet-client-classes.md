---
title: "Voraussetzungen f&#252;r Internetclientklassen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Klassen [C++], Verbindungen"
  - "Verbindungen [C++], Klassen für"
  - "Dateien [C++], Lesen"
  - "Dateien [C++], Schreiben in"
  - "FTP (File Transfer Protocol), MFC-Klassen"
  - "Gopher-Clientanwendungen"
  - "Gophter - erforderliche Komponenten"
  - "HTTP, Erforderliche Komponenten für Internetclients"
  - "Internet [C++], Verbindungen"
  - "Internetclientklassen, erforderliche Komponenten [C++]"
  - "Internetdateien [C++], Schreiben in"
  - "Voraussetzungen, Internetclientklassen"
  - "URLs [C++], Internetclientanwendungen"
ms.assetid: c51d1dfe-260c-4228-8100-e4efd90e9599
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Voraussetzungen f&#252;r Internetclientklassen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Einige Aktionen, die von einem Internet\-Client durchgeführte Aktion \(eine Datei lesen, beispielsweise\) haben erforderlichen Aktionen \(in diesem Fall, eine Internetverbindung Objekt\).  Die folgenden Tabellen werden die erforderlichen Komponenten für einige Clientaktionen auf.  
  
### Allgemeine Internet URL \(Gopher, FTP oder HTTP\)  
  
|Aktion|Vorbereitungsmaßnahme|  
|------------|---------------------------|  
|Stellen Sie eine Verbindung ein.|Erstellen Sie [CInternetSession](../mfc/reference/cinternetsession-class.md), um die Basisklasse einer Internet\-Clientanwendung einzurichten.|  
|Öffnen Sie eine URL.|Stellen Sie eine Verbindung ein.  Aufruf [CInternetSession::OpenURL](../Topic/CInternetSession::OpenURL.md).  Die `OpenURL`\-Funktion gibt einen schreibgeschützten Ressourcenobjekt zurück.|  
|Lesen\-URL\-Daten.|Öffnen Sie die URL.  Aufruf [CInternetFile::Read](../Topic/CInternetFile::Read.md).|  
|Legen Sie eine Internetoption fest.|Stellen Sie eine Verbindung ein.  Aufruf [CInternetSession::SetOption](../Topic/CInternetSession::SetOption.md).|  
|Legen Sie fest eine mit Statusinformationen aufgerufen werden Funktion.|Stellen Sie eine Verbindung ein.  Aufruf [CInternetSession::EnableStatusCallback](../Topic/CInternetSession::EnableStatusCallback.md).  Überschreibung [CInternetSession::OnStatusCallback](../Topic/CInternetSession::OnStatusCallback.md), um Aufrufe behandeln.|  
  
### FTP  
  
|Aktion|Vorbereitungsmaßnahme|  
|------------|---------------------------|  
|Richten Sie eine FTP\-Verbindung ein.|Erstellen Sie [CInternetSession](../mfc/reference/cinternetsession-class.md) als Basis dieser Internet\-Clientanwendung.  Aufruf [CInternetSession::GetFtpConnection](../Topic/CInternetSession::GetFtpConnection.md), um [CFtpConnection](../mfc/reference/cftpconnection-class.md) eines Objekts erstellen möchten.|  
|Suchen Sie die erste Ressource.|Richten Sie eine FTP\-Verbindung ein.  Erstellen Sie ein [CFtpFileFind](../mfc/reference/cftpfilefind-class.md)\-Objekt.  Aufruf [CFtpFileFind::FindFile](../Topic/CFtpFileFind::FindFile.md).|  
|Listen Sie alle verfügbaren Ressourcen auf.|Suchen Sie die erste Datei.  Aufruf [CFtpFileFind::FindNextFile](../Topic/CFtpFileFind::FindNextFile.md), bis er FALSE zurückgibt.|  
|Öffnen Sie eine FTP\-Datei.|Richten Sie eine FTP\-Verbindung ein.  Rufen Sie [CFtpConnection::OpenFile](../Topic/CFtpConnection::OpenFile.md) auf, um ein [CInternetFile](../mfc/reference/cinternetfile-class.md)\-Objekt zu erstellen und zu öffnen.|  
|Lesen Sie eine FTP\-Datei.|Öffnen Sie eine FTP\-Datei mit Lesezugriff.  Aufruf [CInternetFile::Read](../Topic/CInternetFile::Read.md).|  
|Schreiben in eine FTP\-Datei.|Öffnen Sie eine FTP\-Datei mit Schreibzugriff.  Aufruf [CInternetFile::Write](../Topic/CInternetFile::Write.md).|  
|Ändern Sie das Verzeichnis des Clients auf dem Server.|Richten Sie eine FTP\-Verbindung ein.  Aufruf [CFtpConnection::SetCurrentDirectory](../Topic/CFtpConnection::SetCurrentDirectory.md).|  
|Rufen Sie das aktuelle Verzeichnis des Clients auf dem Server abgerufen.|Richten Sie eine FTP\-Verbindung ein.  Aufruf [CFtpConnection::GetCurrentDirectory](../Topic/CFtpConnection::GetCurrentDirectory.md).|  
  
### HTTP  
  
|Aktion|Vorbereitungsmaßnahme|  
|------------|---------------------------|  
|Richten Sie eine HTTP\-Verbindung ein.|Erstellen Sie [CInternetSession](../mfc/reference/cinternetsession-class.md) als Basis dieser Internet\-Clientanwendung.  Aufruf [CInternetSession::GetHttpConnection](../Topic/CInternetSession::GetHttpConnection.md), um [CHttpConnection](../mfc/reference/chttpconnection-class.md) eines Objekts erstellen möchten.|  
|Öffnen Sie eine HTTP\-Datei.|Richten Sie eine HTTP\-Verbindung ein.  Aufruf [CHttpConnection::OpenRequest](../Topic/CHttpConnection::OpenRequest.md), um [CHttpFile](../mfc/reference/chttpfile-class.md) eines Objekts erstellen möchten.  Aufruf [CHttpFile::AddRequestHeaders](../Topic/CHttpFile::AddRequestHeaders.md).  Aufruf [CHttpFile::SendRequest](../Topic/CHttpFile::SendRequest.md).|  
|Lesen Sie eine HTTP\-Datei.|Öffnen Sie eine HTTP\-Datei.  Aufruf [CInternetFile::Read](../Topic/CInternetFile::Read.md).|  
|Rufen Sie Informationen zu einer HTTP\-Anforderung ab.|Richten Sie eine HTTP\-Verbindung ein.  Aufruf [CHttpConnection::OpenRequest](../Topic/CHttpConnection::OpenRequest.md), um [CHttpFile](../mfc/reference/chttpfile-class.md) eines Objekts erstellen möchten.  Aufruf [CHttpFile::QueryInfo](../Topic/CHttpFile::QueryInfo.md).|  
  
### Gopher  
  
|Aktion|Vorbereitungsmaßnahme|  
|------------|---------------------------|  
|Richten Sie eine Gopher\-Verbindung ein.|Erstellen Sie [CInternetSession](../mfc/reference/cinternetsession-class.md) als Basis dieser Internet\-Clientanwendung.  Aufruf von [CInternetSession::GetGopherConnection](../Topic/CInternetSession::GetGopherConnection.md), um [CGopherConnection](../mfc/reference/cgopherconnection-class.md).|  
|Suchen Sie die erste Datei im aktuellen Verzeichnis.|Richten Sie eine Gopher\-Verbindung ein.  Erstellen Sie ein [CGopherFileFind](../mfc/reference/cgopherfilefind-class.md)\-Objekt.  Aufruf [CGopherConnection::CreateLocator](../Topic/CGopherConnection::CreateLocator.md), um [CGopherLocator](../mfc/reference/cgopherlocator-class.md) eines Objekts erstellen möchten.  Führen Sie den Locator zu [CGopherFileFind::FindFile](../Topic/CGopherFileFind::FindFile.md).  Rufen Sie [CGopherFileFind::GetLocator](../Topic/CGopherFileFind::GetLocator.md) auf, um den Locator einer Datei abgerufen, wenn Sie später benötigen.|  
|Listen Sie alle verfügbaren Dateien auf.|Suchen Sie die erste Datei.  Aufruf [CGopherFileFind::FindNextFile](../Topic/CGopherFileFind::FindNextFile.md), bis er FALSE zurückgibt.|  
|Öffnen Sie eine Gopher\-Datei.|Richten Sie eine Gopher\-Verbindung ein.  Erstellen Sie einen Gopher\-Locator mit [CGopherConnection::CreateLocator](../Topic/CGopherConnection::CreateLocator.md) verwenden oder suchen Sie einen Locator mit [CGopherFileFind::GetLocator](../Topic/CGopherFileFind::GetLocator.md).  Aufruf [CGopherConnection::OpenFile](../Topic/CGopherConnection::OpenFile.md).|  
|Lesen Sie eine Gopher\-Datei.|Öffnen Sie eine Gopher\-Datei.  Verwenden Sie [CGopherFile](../mfc/reference/cgopherfile-class.md).|  
  
## Siehe auch  
 [Win32\-Interneterweiterungen \(WinInet\)](../mfc/win32-internet-extensions-wininet.md)   
 [MFC\-Klassen für das Erstellen von Internetclientanwendungen](../mfc/mfc-classes-for-creating-internet-client-applications.md)   
 [Schreiben einer Internetclientanwendung mithilfe von MFC\-WinInet\-Klassen](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
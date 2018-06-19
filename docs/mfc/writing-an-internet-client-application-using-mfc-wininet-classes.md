---
title: Schreiben einer Internetclientanwendung mithilfe von MFC-WinInet-Klassen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Internet client applications [MFC]
- WinInet classes [MFC], programming
- Internet client applications [MFC], writing
- Internet applications [MFC], WinInet
- Internet applications [MFC], client applications
- MFC, Internet applications
ms.assetid: a2c4a40c-a94e-4b3e-9dbf-f8a8dc8e5428
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 822b75ec71d79b6e40ec6b61a77239707c32ce39
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33384435"
---
# <a name="writing-an-internet-client-application-using-mfc-wininet-classes"></a>Schreiben einer Internetclientanwendung mithilfe von MFC-WinInet-Klassen
Die Basis für jede Internetclientanwendung ist die Internet-Sitzung. MFC implementiert internetsitzungen als Objekte der Klasse [CInternetSession](../mfc/reference/cinternetsession-class.md). Diese Klasse können Sie eine Internet-Sitzung oder mehrere gleichzeitige Sitzungen erstellen.  
  
 Um mit einem Server kommunizieren, müssen Sie eine [CInternetConnection](../mfc/reference/cinternetconnection-class.md) Objekt sowie ein `CInternetSession`. Sie erstellen eine `CInternetConnection` mit [CInternetSession:: GetFTPConnection](../mfc/reference/cinternetsession-class.md#getftpconnection), [CInternetSession:: GetHttpConnection](../mfc/reference/cinternetsession-class.md#gethttpconnection), oder [CInternetSession:: GetGopherConnection](../mfc/reference/cinternetsession-class.md#getgopherconnection). Jede dieser Aufrufe ist spezifisch für den Protokolltyp. Diese Aufrufe öffnen Sie eine Datei auf dem Server zum Lesen oder Schreiben nicht. Wenn Sie Daten lesen oder schreiben möchten, müssen Sie die Datei als separater Schritt öffnen.  
  
 Für die meisten internetsitzungen die `CInternetSession` Objekt funktioniert Hand in Hand mit einem [CInternetFile](../mfc/reference/cinternetfile-class.md) Objekt:  
  
-   Für eine Sitzung für Internet, erstellen Sie eine Instanz des [CInternetSession](../mfc/reference/cinternetsession-class.md).  
  
-   Wenn Ihre Internet-Sitzung Daten liest oder schreibt, müssen, erstellen Sie eine Instanz des `CInternetFile` (oder dessen Unterklassen vornehmen [CHttpFile](../mfc/reference/chttpfile-class.md) oder [CGopherFile](../mfc/reference/cgopherfile-class.md)). Die einfachste Möglichkeit zum Lesen von Daten besteht im Aufrufen [OpenURL](../mfc/reference/cinternetsession-class.md#openurl). Diese Funktion analysiert eine von Ihnen bereitgestellten Universal Resource Locator (URL), öffnet eine Verbindung mit dem Server, der die URL und gibt einen schreibgeschützten `CInternetFile` Objekt. `CInternetSession::OpenURL` ist nicht spezifisch für ein Protokoll-Typ – der gleiche Aufruf eignet sich für einen beliebigen FTP, HTTP oder Gopher-URL. `CInternetSession::OpenURL` funktioniert auch mit lokalen Dateien (Rückgabe einer `CStdioFile` anstelle von einer `CInternetFile`).  
  
-   Wenn Ihre Internet-Sitzung nicht lesen oder Schreiben von Daten, führt jedoch andere Aufgaben, z. B. Löschen einer Datei in einem FTP-Verzeichnis, müssen Sie möglicherweise nicht zum Erstellen einer Instanz von `CInternetFile`.  
  
 Es gibt zwei Möglichkeiten zum Erstellen einer `CInternetFile` Objekt:  
  
-   Bei Verwendung von `CInternetSession::OpenURL` zum Herstellen der Serververbindung, den Aufruf von `OpenURL` gibt eine `CStdioFile`.  
  
-   Wenn verwenden **CInternetSession:: GetFTPConnection**, `GetGopherConnection`, oder `GetHttpConnection` um die Serververbindung hergestellt haben, rufen Sie `CFtpConnection::OpenFile`, `CGopherConnection::OpenFile`, oder **CHttpConnection::**  bzw. zum Zurückgeben einer `CInternetFile`, `CGopherFile`, oder `CHttpFile`bzw.  
  
 Die Schritte bei der Implementierung einer Internetclientanwendung variieren, je nachdem, ob Sie eine generische Internetclient basierend auf Erstellen **OpenURL** oder mit einer der protokollspezifische-Clients die **GetConnection** Funktionen.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
  
-   [Wie schreibe ich eine Internetclientanwendung, die generisch mit FTP, HTTP und Gopher arbeitet](../mfc/steps-in-a-typical-internet-client-application.md)  
  
-   [Wie schreibe ich eine FTP-Clientanwendung, die eine Datei öffnet](../mfc/steps-in-a-typical-ftp-client-application.md)  
  
-   [Wie schreibe ich eine FTP-Clientanwendung, die eine Datei wird nicht geöffnet, jedoch führt eine Verzeichnisoperation, z. B. Löschen einer Datei](../mfc/steps-in-a-typical-ftp-client-application-to-delete-a-file.md)  
  
-   [Wie schreibe ich eine Gopher-Clientanwendung](../mfc/steps-in-a-typical-gopher-client-application.md)  
  
-   [Wie schreibe ich eine HTTP-Client-Anwendung](../mfc/steps-in-a-typical-http-client-application.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Win32-Interneterweiterungen (WinInet)](../mfc/win32-internet-extensions-wininet.md)   
 [Mfc_klassen zum Erstellen von Internetclientanwendungen](../mfc/mfc-classes-for-creating-internet-client-applications.md)   
 [Voraussetzungen für Internetclientklassen](../mfc/prerequisites-for-internet-client-classes.md)

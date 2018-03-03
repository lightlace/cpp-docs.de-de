---
title: Wie WinInet das Erstellen von Internetclientanwendungen erleichtert | Microsoft Docs
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
- Windows Sockets [MFC], vs. WinInet
- WinInet classes [MFC], vs. WinSock
- WinInet classes [MFC], Internet client applications
ms.assetid: dc0f9f47-3184-4e7a-8074-2c63e0359885
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9c79404f296df09afb177930897064b8455217d1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-wininet-makes-it-easier-to-create-internet-client-applications"></a>Vereinfachtes Erstellen von Internetclientanwendungen mit WinInet
Die Win32-Interneterweiterungen oder WinInet, bieten Zugriff auf allgemeine Internetprotokolle, einschließlich Gopher, FTP und HTTP. Mit WinInet können Sie Internetclientanwendungen auf einer höheren Ebene der Programmierung, ohne dass für den Umgang mit WinSock, TCP/IP oder den Details zu bestimmten Internetprotokolle schreiben. WinInet bietet einen konsistenten Satz von Funktionen für alle drei Protokolle, eine vertraute Oberfläche für die Win32-API. Diese Konsistenz werden Änderungen am Code vornehmen, wenn die zugrunde liegenden Protokoll (beispielsweise von FTP auf HTTP) ändert benötigten minimiert.  
  
 Visual C++ bietet zwei Möglichkeiten für die Verwendung von WinInet. Können Sie die Win32-Internet-Funktionen direkt aufrufen (siehe die OLE-Dokumentation im Windows SDK für Weitere Informationen) oder WinInet durch Verwenden der [MFC-WinInet-Klassen](../mfc/mfc-classes-for-creating-internet-client-applications.md).  
  
 **Sie können WinInet zu verwenden:**  
  
-   HTML-Seiten herunterladen.  
  
     HTTP ist ein Protokoll zum Übertragen von HTML-Seiten von einem Server an einem Clientbrowser verwendet.  
  
-   FTP-Anforderungen zum Hochladen oder Herunterladen von Dateien oder Abrufen von Verzeichnislisten gesendet werden.  
  
     Eine typische-Anforderung ist eine anonyme Anmeldung zum Herunterladen einer Datei.  
  
-   Verwenden des Gopher-Menüsystem für den Zugriff auf Ressourcen im Internet.  
  
     Menüelemente können mehrere Typen, z. B. anderen Menüs, eine indizierte Datenbank, die Sie durchsuchen können, eine Newsgroup oder eine Datei sein.  
  
 Für alle drei Protokolle eine Verbindung herstellen, stellen Sie Anforderungen an den Server und schließen Sie die Verbindung.  
  
 **Die MFC-WinInet-Klassen erleichtern:**  
  
-   Lesen Sie die Informationen über HTTP, FTP und Gopher-Server genauso einfach wie das Lesen von Dateien von einer Festplatte.  
  
-   Verwenden Sie HTTP, FTP und Gopher Protokolle ohne Programmierung direkt WinSock oder TCP/IP.  
  
     Entwickler, die die Win32-Internet-Funktionen verwenden, müssen nicht mit TCP/IP "oder" Windows-Sockets vertraut sein. Sie können weiterhin Programmieren auf Socketebene, WinSock und TCP/IP-Protokolle direkt, verwenden jedoch es ist auch einfacher, die MFC-WinInet-Klassen, um den Zugriff auf HTTP, FTP und Gopherprotokolle über das Internet zu verwenden. Für viele allgemeine Vorgänge müssen Entwickler nicht die Details eines bestimmten Protokolls kennen, die sie verwenden.  
  
 Viele Vorgänge, die von Ihrem Computer als Client auf anderen Computern im Internet ausgeführt werden können, können eine lange dauern. Die Geschwindigkeit von diesen Vorgängen wird in der Regel durch die Geschwindigkeit Ihrer Netzwerkverbindung beschränkt, aber sie können auch von anderem Netzwerkdatenverkehr und die Komplexität des Vorgangs beeinflusst werden. Herstellen einer Verbindung mit einem FTP-Remoteserver erfordert z. B. an, dass Ihre Computer uns zunächst nach dem Namen des Server her, um seine Adresse zu suchen. Die Anwendung wird dann versucht, für die Verbindung mit dem Server an dieser Adresse. Sobald die Verbindung geöffnet ist, werden Ihre Computer und dem Remoteserver initiiert eine Konversation mit dem File Transfer Protocol, bevor Sie die Verbindung tatsächlich zum Abrufen von Dateien verwenden können.  
  
## <a name="see-also"></a>Siehe auch  
 [Win32-Interneterweiterungen (WinInet)](../mfc/win32-internet-extensions-wininet.md)   
 [Vereinfachtes Erstellen von Internetclientanwendungen mit MFC](../mfc/how-mfc-makes-it-easier-to-create-internet-client-applications.md)


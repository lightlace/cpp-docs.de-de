---
title: Vereinfachtes Erstellen von Internetclientanwendungen mit WinInet
ms.date: 11/04/2016
helpviewer_keywords:
- Windows Sockets [MFC], vs. WinInet
- WinInet classes [MFC], vs. WinSock
- WinInet classes [MFC], Internet client applications
ms.assetid: dc0f9f47-3184-4e7a-8074-2c63e0359885
ms.openlocfilehash: 2bca338aa2a1b18e8c9ab41a887678767cf6c8c6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50636857"
---
# <a name="how-wininet-makes-it-easier-to-create-internet-client-applications"></a>Vereinfachtes Erstellen von Internetclientanwendungen mit WinInet

Die Win32-Interneterweiterungen oder WinInet, bieten Zugriff auf allgemeine Internetprotokolle, einschließlich Gopher, FTP und HTTP. Mit WinInet können Sie Internet-Clientanwendungen auf einer höheren Ebene der Programmierung, für den Umgang mit WinSock, TCP/IP oder die Details von bestimmten Internetprotokollen ohne schreiben. WinInet bietet einen konsistenten Satz von Funktionen für alle drei Protokolle, die eine vertraute Oberfläche für die Win32-API. Diese Konsistenz wird minimiert, Änderungen am Code vornehmen, wenn das zugrunde liegende Protokoll geändert wird (z. B. von FTP auf HTTP) benötigen.

Visual C++ bietet zwei Möglichkeiten, WinInet verwenden. Können Sie die Win32-Internet-Funktionen direkt aufrufen (siehe die OLE-Dokumentation im Windows SDK für Weitere Informationen) oder WinInet durch Verwenden der [MFC-WinInet-Klassen](../mfc/mfc-classes-for-creating-internet-client-applications.md).

**Sie können die WinInet zu verwenden:**

- Laden Sie die HTML-Seiten.

   HTTP ist ein Protokoll zum Übertragen von HTML-Seiten von einem Server an einem Clientbrowser verwendet.

- Senden Sie die FTP-Anforderungen zum Hochladen oder Herunterladen von Dateien oder Verzeichnislisten zu erhalten.

   Eine typische Anforderung ist eine anonyme Anmeldung zum Herunterladen einer Datei.

- Verwenden des Gopher-Menü-System für den Zugriff auf Ressourcen im Internet.

   Menüelemente können es sich um verschiedene Typen, einschließlich der anderen Menüs, eine indizierte Datenbank, die Sie durchsuchen können, eine Newsgroup oder eine Datei.

Für alle drei Protokolle Sie eine Verbindung herstellen, Anforderungen an den Server, und schließen Sie die Verbindung.

**Die MFC-WinInet-Klassen vereinfachen:**

- Lesen Sie die Informationen über HTTP, FTP und Gopher-Server so einfach wie das Lesen von Dateien von einer Festplatte.

- Verwenden Sie HTTP, FTP und Gopher Protokolle ohne direkten Programmieren auf WinSock oder TCP/IP.

   Entwickler, die die Win32-Internet-Funktionen verwenden, müssen nicht mit TCP/IP "oder" Windows-Sockets vertraut sein. Können Sie weiterhin Programmieren auf Socketebene, WinSock und TCP/IP-Protokolle direkt verwenden, aber es ist sogar noch einfacher mit den MFC-WinInet-Klassen, die Zugriff auf HTTP, FTP und Gopherprotokolle über das Internet. Für viele häufige Vorgänge müssen Entwickler nicht wissen, die Details der das bestimmte Protokoll, die sie verwenden.

Viele Vorgänge, die von Ihrem Computer als Client auf anderen Computern im Internet ausgeführt werden können sehr lange dauern. Die Geschwindigkeit von diesen Vorgängen wird in der Regel durch die Geschwindigkeit Ihrer Netzwerkverbindung beschränkt, aber sie können auch von Datenverkehr im Netzwerk und der Komplexität des Vorgangs beeinflusst werden. Herstellen einer Verbindung mit einem FTP-Remoteserver erfordert z. B. an, dass es sich bei Ihrem Computer zunächst den Namen des Servers zum Suchen der Adresse nachschlagen. Ihre Anwendung versucht, auf dem Server an dieser Adresse eine Verbindung herstellen. Nachdem die Verbindung geöffnet ist, initiiert Ihren Computer und RAS-Server eine Unterhaltung mit File Transfer Protocol, bevor Sie die Verbindung tatsächlich verwenden können, um Dateien abzurufen.

## <a name="see-also"></a>Siehe auch

[Win32-Interneterweiterungen (WinInet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[Vereinfachtes Erstellen von Internetclientanwendungen mit MFC](../mfc/how-mfc-makes-it-easier-to-create-internet-client-applications.md)


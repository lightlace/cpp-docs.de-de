---
title: "Vereinfachtes Erstellen von Internetclientanwendungen mit WinInet"
ms.custom: na
ms.date: "12/14/2016"
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
  - "Windows-Sockets [C++], kontra WinInet"
  - "WinInet-Klassen, Internetclientanwendungen"
  - "WinInet-Klassen, kontra WinSock"
ms.assetid: dc0f9f47-3184-4e7a-8074-2c63e0359885
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Vereinfachtes Erstellen von Internetclientanwendungen mit WinInet
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Win32\-Internet\-Erweiterungen oder WinInet\-Klassen, ermöglichen den Zugriff auf allgemeine Internetprotokollen, einschließlich Gopher, FTP und HTTP.  Verwenden WinInets können Sie Internet\-Clientanwendungen auf einer höheren Ebene der Programmierung schreiben, ohne zu müssen, Winsock\-Schnittstelle, TCP\/IP oder die Details bestimmter Internetprotokollen darzustellen.  WinInet\-Klassen stellt eine konsistente Gruppe von Funktionen für alle drei Protokolle, mit einer gewohnten Win32 API\-Schnittstelle.  Das wiederkehrende minimiert Codeänderungen, die Sie vornehmen müssen, wenn das zugrunde liegende Protokoll geändert wird \(beispielsweise, von FTP HTTP\).  
  
 Visual C\+\+ bietet zwei Möglichkeiten, damit Sie WinInet\-Klassen verwenden.  Sie können die Win32\-Internet\-Funktionen aufrufen direkt \(siehe die OLE\-Dokumentation in [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)] zu Informationen\), oder Sie können WinInet\-Klassen von [Klassen MFC\-WinInet\-Unterstützung](../mfc/mfc-classes-for-creating-internet-client-applications.md) verwenden.  
  
 **Sie können WinInet\-Klassen verwenden:**  
  
-   Download\-HTML\-Seiten.  
  
     HTTP ist ein Protokoll, das verwendet wird, um HTML\-Seiten von einem Server auf einen Clientbrowser zu übertragen.  
  
-   Senden Sie FTP\-Anforderungen, Dateien hochzuladen oder herunterzuladen oder Verzeichnislisten abzurufen.  
  
     Eine typische Anforderung ist eine anonyme Anmeldung, um eine Datei herunterladen.  
  
-   Verwenden Sie das Gophers Menüsystem des für den Zugriff auf Ressourcen im Internet.  
  
     Menüelemente können mehrere Typen, einschließlich andere Menüs, eine indizierte Datenbank, die Sie finden, eine Newsgroup oder eine Datei sein.  
  
 Für alle drei Protokolle legen Sie eine Verbindung ein, stellen Vorschläge zum Server und schließen die Verbindung.  
  
 **Die Klassen MFC\-WinInet\-Unterstützung ihnen einfach:**  
  
-   Lesen Sie Informationen von HTTP, von FTP und den Gopherservern ebenso problemlos, wie Lese\- einer Festplatte protokollieren.  
  
-   Verwenden Sie HTTP, FTP und Gopher\-Protokolle, ohne zu programmieren direkt zu Winsock\-Schnittstelle oder zu TCP\/IP.  
  
     Entwickler, die die Win32\-Internet\-Funktionen verwenden, müssen nicht mit TCP\/IP oder Windows Sockets vertraut zu sein.  Sie können auf der Socketebene, mit Winsocks und TCP\/IP noch programmieren protokolliert direkt, aber es ist einfacher, die Klassen MFC\-WinInet\-Unterstützung zu verwenden, dass HTTP, FTP und auf Gopher\-Protokolle über das Internet zugegriffen.  Für viele allgemeine Vorgänge müssen Entwickler nicht, um die Details des bestimmten Protokolls zu kennen, das sie verwenden.  
  
 Viele Vorgänge, die für den Computer als Client auf andere Computer im Internet ausgeführt werden können, lange dauern.  Die Geschwindigkeit dieser Vorgänge wird normalerweise von der Geschwindigkeit der Netzwerkverbindung beschränkt, jedoch können durch anderen Netzwerkverkehr und Komplexität des Vorgangs außerdem beeinflusst werden.  An einen remote FTP\-Server herstellen beispielsweise erfordert, dass der Computer zunächst oben den Namen dieses Servers werden, um seine Adresse zu suchen.  Die Anwendung versucht anschließend, an dem Server an diese Adresse herzustellen.  Nachdem die Verbindung geöffnet ist, initiiert der Computer und der Remoteserver eine Konversation mit dem File Transfer Protocol, bevor die Verbindung eigentlich verwenden können, um Dateien abzurufen.  
  
## Siehe auch  
 [Win32\-Interneterweiterungen \(WinInet\)](../mfc/win32-internet-extensions-wininet.md)   
 [Vereinfachtes Erstellen von Internetclientanwendungen mit MFC](../mfc/how-mfc-makes-it-easier-to-create-internet-client-applications.md)
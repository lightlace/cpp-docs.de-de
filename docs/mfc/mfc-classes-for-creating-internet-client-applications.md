---
title: "MFC-Klassen f&#252;r das Erstellen von Internetclientanwendungen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Klassen [C++], MFC"
  - "Internetanwendungen, MFC"
  - "Internetclientanwendungen, MFC"
  - "MFC, WinInet-Klassen"
  - "WinInet-Klassen, Klassen"
ms.assetid: 67d34117-9839-4f4b-8bb8-0e4a9471c606
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# MFC-Klassen f&#252;r das Erstellen von Internetclientanwendungen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC stellt die folgenden Klassen und globalen Funktionen zum Schreiben von Internet\-Clientanwendungen bereit.  Einzug gibt eine Klasse abgeleitet wird von der Klasse unindented darüber an.  `CGopherFile` und `CHttpFile` werden von `CInternetFile`, z. B  Diese Klassen und globalen Funktionen werden in AFXINET.H, außer `CFileFind` deklariert, das in AFX.H. deklariert wird.  
  
## Klassen  
  
-   [CInternetSession](../mfc/reference/cinternetsession-class.md)  
  
-   [CInternetConnection](../mfc/reference/cinternetconnection-class.md)  
  
    -   [CFtpConnection](../mfc/reference/cftpconnection-class.md)  
  
    -   [CGopherConnection](../mfc/reference/cgopherconnection-class.md)  
  
    -   [CHttpConnection](../mfc/reference/chttpconnection-class.md)  
  
-   [CInternetFile](../mfc/reference/cinternetfile-class.md)  
  
    -   [CGopherFile](../mfc/reference/cgopherfile-class.md)  
  
    -   [CHttpFile](../mfc/reference/chttpfile-class.md)  
  
-   [CFileFind](../mfc/reference/cfilefind-class.md)  
  
    -   [CFtpFileFind](../mfc/reference/cftpfilefind-class.md)  
  
    -   [CGopherFileFind](../mfc/reference/cgopherfilefind-class.md)  
  
-   [CGopherLocator](../mfc/reference/cgopherlocator-class.md)  
  
-   [CInternetException](../mfc/reference/cinternetexception-class.md)  
  
## Globale Funktionen  
  
-   [AfxParseURL](../Topic/AfxParseURL.md)  
  
-   [AfxGetInternetHandleType](../Topic/AfxGetInternetHandleType.md)  
  
-   [AfxThrowInternetException](../Topic/AfxThrowInternetException.md)  
  
## Siehe auch  
 [Win32\-Interneterweiterungen \(WinInet\)](../mfc/win32-internet-extensions-wininet.md)   
 [Voraussetzungen für Internetclientklassen](../mfc/prerequisites-for-internet-client-classes.md)   
 [Schreiben einer Internetclientanwendung mithilfe von MFC\-WinInet\-Klassen](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
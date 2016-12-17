---
title: "Windows Sockets: Ports und Socketadressen"
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
  - "Adressen [C++], Socket"
  - "Ports [C++]"
  - "Ports [C++], Definition"
  - "Sockets [C++], Adressen"
  - "Sockets [C++], Anschlüsse"
  - "Windows-Sockets [C++], Adressen"
  - "Windows-Sockets [C++], Anschlüsse"
ms.assetid: e050261a-9285-4f31-a1c5-6c8033af5b4a
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Windows Sockets: Ports und Socketadressen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In diesem Artikel werden die Begriffe "portieren" und "Objekt Sie sich z" mit Windows Sockets verwendet.  
  
##  <a name="_core_port"></a> Port  
 Ein Port identifiziert einen eindeutigen Prozess, für den ein Dienst bereitgestellt werden kann.  im vorhandenen Kontext wird ein Port mit einer Anwendung zugeordnet, die Windows Sockets unterstützt.  Die Idee ist, eine Windows Socket\-Anwendung eindeutig identifizieren, sodass Sie mehrere Windows Socket\-Anwendungsbetrieb auf einem Computer gleichzeitig.  
  
 Bestimmte Ports sind für gemeinsame Dienste, z FTP reserviert.  Sie sollten diese, Anschlüsse zu vermeiden, verwenden, sofern Sie diese Art des Diensts bereitstellen.  Die Windows Socket\-Spezifikation führt diese reservierten Ports aufgeführt.  Die Datei WINSOCK.H wird auch auf.  
  
 Wenn Sie die Windows Sockets zu ermöglichen, die DLL einen verwendbaren Port für Sie auswählen, führen Sie 0 als der Port.  MFC wird eine größere Dezimalzahl als 1.024 des Anschlusswerts aus.  Sie können den Port abrufen, den MFC auswählte, indem die [CAsyncSocket::GetSockName](../Topic/CAsyncSocket::GetSockName.md)\-Memberfunktion aufgerufen wurde.  
  
##  <a name="_core_socket_address"></a> Socket\-Adresse  
 Jedes Socketobjekt ist einer Internetprotokoll Adresse \(ip\)\- auf dem Netzwerk verknüpft.  In der Regel ist die Adresse ein Computername, wie "ftp.microsoft.com" oder eine durch Punkte getrennte Zahl, z "128.56.22.8".  
  
 Wenn Sie feststellen, um einen Socket zu erstellen, müssen Sie in der Regel nicht, um eigenen der Adresse angeben.  
  
> [!NOTE]
>  Es ist möglich, dass der Computer mehrere Netzwerkkarten \(oder die Anwendung konnte auf einen solchen Computer eines Tages ausgeführt werden\), jede wurde, die ein anderes Netzwerk darstellt.  In diesem Fall müssen Sie möglicherweise eine Adresse angeben, um anzugeben, die Netzwerkkarte der Socket verwendet.  Dies ist sicher, eine erweiterte Verwendung und ein beliebiges Portabilitätsproblem zu sein.  
  
 Weitere Informationen finden Sie unter:  
  
-   [Windows Sockets: Verwenden der Klasse CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows Sockets: Verwenden von Sockets mit Archiven](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Windows Sockets: Wie Sockets mit Archiven arbeiten](../mfc/windows-sockets-how-sockets-with-archives-work.md)  
  
-   [Windows Sockets: Streamsockets](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows Sockets: Datagrammsockets](../mfc/windows-sockets-datagram-sockets.md)  
  
## Siehe auch  
 [Windows\-Sockets in MFC](../mfc/windows-sockets-in-mfc.md)
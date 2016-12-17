---
title: "Windows-Sockets in MFC"
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
  - "MFC [C++], Windows-Sockets"
  - "Sockets [C++], MFC"
  - "Sockets [C++], Programmiermodelle"
  - "Windows-Sockets [C++], MFC-Unterstützung"
  - "Windows-Sockets [C++], Programmiermodelle"
  - "WINSOCK.DLL"
  - "WSOCK32.DLL"
ms.assetid: 1f3c476a-9c68-49fe-9a25-d22971a334d0
caps.latest.revision: 12
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Windows-Sockets in MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  MFC\-Unterstützungs\-WindowsSockets 1 unterstützt jedoch nicht [Windows Sockets 2](http://msdn.microsoft.com/library/windows/desktop/ms740673).  Die Windows Sockets 2 zuerst versandt mit Windows 98 und ist die Version, die mit Windows 2000 enthalten ist.  
  
 MFC stellt zwei Modelle für das Schreiben von Netzwerkkommunikationsprogrammen mit Windows Sockets, dargestellt in zwei MFC\-Klassen.  Dieser Artikel beschreibt diese Modelle und weitere Socketunterstützung der Details MFC.  Ein "Socket" ist ein Endpunkt der Kommunikation zu: ein Objekt, durch das die Anwendung andere Windows Socket\-Anwendungen über ein Netzwerk ist.  
  
 Informationen zu Windows Sockets, einschließlich einer Erklärung des Socketkonzepts, finden Sie unter [Windows Sockets: Hintergrund](../mfc/windows-sockets-background.md).  
  
##  <a name="_core_sockets_programming_models"></a> Socket\-Programmiermodelle  
 Die zwei MFC\-WindowsSocket\-Programmiermodelle werden von den folgenden Klassen unterstützt:  
  
-   `CAsyncSocket`  
  
     Diese Klasse kapselt die Windows Sockets API.  [CAsyncSocket](../mfc/reference/casyncsocket-class.md) ist für Programmierer, die Netzwerkprogrammierung kennen und Flexibilität der direkte Programmierung Sockets zur API möchten, jedoch keine auch die Vorteile von Rückruffunktionen für eine Benachrichtigung über Netzwerkereignissen.  Anders als Verpackungssockets in der objektorientierten Form für C\+\+, konvertiert die einzige zusätzliche Abstraktion, die diese Klasse angibt, bestimmte Socket\-verknüpfte Windows\-Meldungen in Rückrufe.  Weitere Informationen finden Sie unter [Windows Sockets: Socket\-Benachrichtigungen](../mfc/windows-sockets-socket-notifications.md).  
  
-   `CSocket`  
  
     Diese Klasse, abgeleitet von `CAsyncSocket`, stellt eine höhere Abstraktionsebene für Sockets durch ein Objekt MFC\- [CArchive](../mfc/reference/carchive-class.md).  Verwenden eines Sockets mit einem Archiv ähnelt groß mithilfe des Datei\-Serialisierungsprotokolls MFC.  Dies vereinfacht das `CAsyncSocket` als Modell verwenden.  [CSocket](../mfc/reference/csocket-class.md) erbt zahlreiche Memberfunktionen von `CAsyncSocket`, die Windows Socket\-APIs kapseln; Sie müssen einige dieser Funktionen verwendet und die Sockets verstehen, die allgemein programmieren.  `CSocket` verwaltet jedoch zahlreiche Aspekte der Kommunikation, dass Sie entweder mithilfe unformatierter API zu tun würden oder `CAsyncSocket`\- Klasse müssen.  Am wichtigsten ist, stellt `CSocket` das Blockieren mit \(Hintergrundverarbeitung von Windows\-Meldungen\), das dem Gleichlaufbetrieb von `CArchive` erforderlich ist.  
  
 Das Erstellen und Verwenden von `CSocket` und `CAsyncSocket`\-Objekten wird in [Windows Sockets: Verwenden der Archiven Sockets mit](../mfc/windows-sockets-using-sockets-with-archives.md) und [Windows Sockets: Verwenden der Klasse CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md) beschrieben.  
  
##  <a name="_core_mfc_socket_samples_and_windows_sockets_dlls"></a> Windows Socket\-DLLs  
 Die Microsoft Windows\-Betriebssysteme stellen die Windows Socket\-DynamicLink Librarys \(DLL\).  Visual C\+\+ stellt die entsprechenden Headerdateien und Bibliotheken und die Windows Socket\-Spezifikation.  
  
> [!NOTE]
>  Unter Windows NT und Windows 2000 ist Windows Socket\-Unterstützung für 16\-Bit\-Anwendungen auf Grundlage WINSOCK.DLL.  Für 32\-Bit\-Anwendungen lautet die Unterstützung in WSOCK32.DLL.  Die APIs, die bereitgestellt werden, sind identisch, nur die 32\-Bit\-Version verfügen über Parameter, die zu 32 Bits erweitert werden.  Bei Win32 Threadsicherheit wird angegeben.  
  
 Weitere Informationen über Windows Sockets, finden Sie unter:  
  
-   [Windows Sockets: Streamsockets](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows Sockets: Datagrammsockets](../mfc/windows-sockets-datagram-sockets.md)  
  
-   [Windows Sockets: Verwenden von Sockets mit Archiven](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Windows Sockets: Sequenz von Vorgängen](../mfc/windows-sockets-sequence-of-operations.md)  
  
-   [Windows Sockets: Beispiel für Sockets mithilfe der Archive](../mfc/windows-sockets-example-of-sockets-using-archives.md)  
  
-   [Windows Sockets: Wie Sockets mit Archiven arbeiten](../mfc/windows-sockets-how-sockets-with-archives-work.md)  
  
-   [Windows Sockets: Verwenden der Klasse CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows Sockets: Leiten von den Socket\-Klassen](../mfc/windows-sockets-deriving-from-socket-classes.md)  
  
-   [Windows Sockets: Socket\-Benachrichtigungen](../mfc/windows-sockets-socket-notifications.md)  
  
-   [Windows Sockets: Blockieren](../mfc/windows-sockets-blocking.md)  
  
-   [Windows Sockets: Bytereihenfolge](../mfc/windows-sockets-byte-ordering.md)  
  
-   [Windows Sockets: Konvertieren von Zeichenfolgen](../mfc/windows-sockets-converting-strings.md)  
  
-   [Windows Sockets: Anschlüsse und Socket\-Adressen](../mfc/windows-sockets-ports-and-socket-addresses.md)  
  
## Siehe auch  
 [Windows\-Sockets](../mfc/windows-sockets.md)
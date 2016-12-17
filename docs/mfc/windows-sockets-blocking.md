---
title: "Windows Sockets: Blocking"
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
  - "Blockierungsmodussockets"
  - "Sockets [C++], Verhalten auf verschiedenen Windows-Plattformen"
  - "Sockets [C++], Blockierungsmodus"
  - "Windows-Sockets [C++], Blockierungsmodus"
  - "Windows-Sockets [C++], Windows-Plattformen"
ms.assetid: 10aca9b1-bfba-41a8-9c55-ea8082181e63
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Windows Sockets: Blocking
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Artikel und zwei Begleitartikel beschreiben einige Probleme bei der Windows Socket\-Programmierung.  Dieser Artikel enthält die Blockierung.  Die anderen Probleme sind in den Artikeln behandelt: [Windows Sockets: Bytereihenfolge](../mfc/windows-sockets-byte-ordering.md) und [Windows Sockets: Konvertieren von Zeichenfolgen](../mfc/windows-sockets-converting-strings.md).  
  
 Wenn Sie von der [CAsyncSocket](../mfc/reference/casyncsocket-class.md) verwenden oder leiten, müssen Sie diese Probleme selbst verwalten.  Wenn Sie von der [CSocket](../mfc/reference/csocket-class.md) verwenden oder leiten, verwaltet MFC sie für Sie.  
  
## Blockieren  
 Ein Socket kann "im blockierenden Modus" oder "in nicht blockierenden Modus befinden." Die Features aus Sockets im Blockieren \(oder\) im synchronen Modus ändert nicht wieder, bis diese ihre Aktion durchführen können.  Dies wird Blockierung bezeichnet, da der Socket, dessen Funktion aufgerufen wurde, keine Aktionen durchführen kann blockiertes \- ist \- bis der Aufruf gibt.  Ein Aufruf der **Empfangen**\-Memberfunktion beispielsweise könnte eine beliebig lange Zeit, als er abzuschließen wartet auf die sendende Anwendung zu senden \(dieser befindet, wenn Sie `CSocket` verwenden, mit `CAsyncSocket` oder mit dem Blockieren\).  Wenn ein `CAsyncSocket`\-Objekt im nicht blockierenden Modus \(nicht bei Verwendung asynchron\), in der Aufruf sofort und im aktuellen Fehlercode, ist, der mit der [GetLastError](../Topic/CAsyncSocket::GetLastError.md)\-Memberfunktion, **WSAEWOULDBLOCK** ist abrufbar ist und angibt, dass der Aufruf ist es aufgrund des Modus sofort zurückgeben blockiert worden wäre. \(`CSocket` gibt nie **WSAEWOULDBLOCK** zurück.  Die Klasse verwaltet die Blockierung für Sie.\)  
  
 Das Verhalten von Sockets unterliegt unter einem 32\-Bit\- oder \(wie Windows 95 oder Windows 98\) als unter 16\-Bit\-Betriebssystemen unterschiedlich \(wie Windows 3.1\).  Anders als 16\-Bit\-Betriebssysteme verwenden das 32\-Bit\- und 64\-Bit\-Betriebssysteme die präemptives Multitasking und stellen Multithreading.  unter dem den 32\-Bit\- und 64\-Bit\-Betriebssystemen können Sie Ihre Sockets in separaten Arbeitsthreads ablegen.  Ein Socket in einem Thread blockieren kann, ohne andere Aktivitäten in der Anwendung zu beeinträchtigen und ohne Berechnungszeit im Blockieren zu verbringen.  Informationen zum Multithreadprogrammierung, finden Sie im Artikel [Multithreading](../parallel/multithreading-support-for-older-code-visual-cpp.md).  
  
> [!NOTE]
>  In Multithreadanwendungen können Sie die blockierenden Eigenschaften von `CSocket` verwenden, um den Entwurf des Programms zu vereinfachen, ohne die Reaktionszeit der Benutzeroberfläche zu beeinflussen.  Mithilfe Benutzerinteraktionen im Hauptthread und im `CSocket` behandeln, die in alternativen Threads verarbeiten, können Sie diese Operationen logischen trennen.  In einer Anwendung, die keine Multithreadkomponente ist, müssen diese beiden Aktivitäten als Thread arbeitet, die kombiniert behandelt werden normalerweise mithilfe `CAsyncSocket` bedeutet, sodass Sie Kommunikationsanforderungen bei Bedarf bearbeiten können, oder `CSocket::OnMessagePending`, Überschreiben, um Benutzeraktionen während der längeren synchronen Aktivität zu behandeln.  
  
 Der Rest dieser Erläuterung wird für Programmierer, die auf 16\-Bit\-Betriebssysteme ausgerichtet sind:  
  
 Normalerweise wenn Sie `CAsyncSocket` verwenden, sollten Sie die Verwendung von UMS\-Threads vermeiden und asynchron stattdessen funktionieren.  In den asynchronen Vorgänge an denen vom Punkt Sie einen **WSAEWOULDBLOCK** erhalten Fehlercode, nachdem Sie **Empfangen** beispielsweise aufgerufen haben warten Sie, bis die `OnReceive`\-Memberfunktion aufgerufen wurde, um Sie darauf hinzuweisen, dass Sie erneut lesen können.  Asynchrone Aufrufe werden durch das die Rückruf\-Benachrichtigungsfunktion des Sockets entsprechende, wie [OnReceive](../Topic/CAsyncSocket::OnReceive.md) ausgeführt.  
  
 Unter Windows werden als Aufrufe Blockierung ungültige Praxis.  Standardmäßig unterstützt asynchrone Aufrufe [CAsyncSocket](../mfc/reference/casyncsocket-class.md), und Sie müssen das Blockieren mit dem der Rückrufbenachrichtigungen verwalten.  Klasse [CSocket](../mfc/reference/csocket-class.md) sollte synchron.  Sie Windows\-Meldungen weiterleitet und verwaltet die Blockierung für Sie.  
  
 Weitere Informationen über die Blockierung, finden Sie in der Windows Socket\-Spezifikation.  Weitere Informationen über "on" \- Funktionen, finden Sie unter [Windows Sockets: Socket\-Benachrichtigungen](../mfc/windows-sockets-socket-notifications.md) und [Windows Sockets: Leiten von den Socket\-Klassen](../mfc/windows-sockets-deriving-from-socket-classes.md).  
  
 Weitere Informationen finden Sie unter:  
  
-   [Windows Sockets: Verwenden der Klasse CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows Sockets: Verwenden von Sockets mit Archiven](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Windows Sockets: Hintergrund](../mfc/windows-sockets-background.md)  
  
-   [Windows Sockets: Streamsockets](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows Sockets: Datagrammsockets](../mfc/windows-sockets-datagram-sockets.md)  
  
## Siehe auch  
 [Windows\-Sockets in MFC](../mfc/windows-sockets-in-mfc.md)   
 [CAsyncSocket::OnSend](../Topic/CAsyncSocket::OnSend.md)
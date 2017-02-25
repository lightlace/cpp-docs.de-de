---
title: "Windows Sockets: Socketbenachrichtigungen | Microsoft Docs"
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
  - "Benachrichtigungen, Socket"
  - "Sockets [C++], Benachrichtigungen"
  - "Windows-Sockets [C++], Benachrichtigungen"
ms.assetid: 87d5bf70-6e77-49a9-9a64-aaadee2ad018
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Windows Sockets: Socketbenachrichtigungen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Artikel beschreibt die Benachrichtigungsfunktionen in den Socketklassen.  Diese Memberfunktionen sind Rückruffunktionen, die vom Framework aufgerufen wird, um den Socketobjekts wichtiger Ereignisse zu benachrichtigen.  Die Benachrichtigungsfunktionen sind:  
  
-   [OnReceive](../Topic/CAsyncSocket::OnReceive.md): Benachrichtigt diesen Socket, dass Daten im Puffer gibt, sodass er erhält, indem Sie [Empfangen Sie](../Topic/CAsyncSocket::Receive.md) aufrufen.  
  
-   [OnSend](../Topic/CAsyncSocket::OnSend.md): Benachrichtigt diesen Socket, dass er Daten nun übermitteln kann, indem er die [Senden](../Topic/CAsyncSocket::Send.md) aufgerufen wird.  
  
-   [OnAccept](../Topic/CAsyncSocket::OnAccept.md): Benachrichtigt diesen lauschenden Socket, dass er während Aufforderungen zum Aufbau einer Verbindung aufnehmen kann, indem er die [Annehmen](../Topic/CAsyncSocket::Accept.md) aufgerufen wird.  
  
-   [OnConnect](../Topic/CAsyncSocket::OnConnect.md): Benachrichtigt diese Steckverbindung, dass sein Verbindungsversuch abgeschlossen wurde: kann erfolgreich oder möglicherweise im Fehler.  
  
-   [OnClose](../Topic/CAsyncSocket::OnClose.md): Benachrichtigt diesen Socket, dass der Socket, den er verbunden wird, geschlossen wurden.  
  
    > [!NOTE]
    >  Eine zusätzliche Benachrichtigungsfunktion ist [OnOutOfBandData](../Topic/CAsyncSocket::OnOutOfBandData.md).  Diese Benachrichtigung teilt dem empfangenden Socket mit, dass der die sendende Socket "nicht auf Band aufgenommenen" Daten hat, senden.  Out\-of\-Band\-Daten sind mit jedem Paar verbundenen Streamsockets logisch ein unabhängiges kanalgebundenes.  Der nicht auf Band aufgenommene Kanal wird normalerweise verwendet, um "dringende" Daten zu senden.  MFC unterstützt Out\-of\-Band\-Daten.  Mit fortgeschrittenen Benutzer, die mit der Klasse [CAsyncSocket](../mfc/reference/casyncsocket-class.md) arbeiten, müssen die nicht auf Band aufgenommenen Kanal verwenden, aber Benutzer der Klasse [CSocket](../mfc/reference/csocket-class.md) werden von der Verwendung abgeraten.  Einfacher ist, einen zweiten Socket zum Übergeben solcher Daten zu erstellen.  Weitere Informationen über Out\-of\-Band\-Daten, finden Sie in der Windows Socket\-Spezifikation, die in [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)] verfügbar ist.  
  
 Wenn von der Klasse `CAsyncSocket`, müssen Sie die für diese Netzwerkereignisse Benachrichtigungsfunktionen für der Anwendung überschrieben.  Wenn Sie eine Klasse von der `CSocket`\- Klasse abgeleitet werden, ist es Ihre Auswahl, ob die Benachrichtigungsfunktionen relevante überschreibt.  Sie können `CSocket` auch selbst verwenden, in diesem Fall die Benachrichtigungsfunktionen zu dem diese nichts übergeben.  
  
 Diese Funktionen sind überschreibbare Rückruffunktionen.  `CAsyncSocket` und `CSocket` konvertieren Meldungen an Benachrichtigungen, Sie müssen jedoch implementieren, z die Benachrichtigungsfunktionen reagieren, wenn Sie sie verwenden möchten.  Die Benachrichtigungsfunktionen werden, wenn das Socket von einem Ereignis relevante benachrichtigt wird, wie das Verfolgen von Daten gelesen wird, aufgerufen.  
  
 MFC ruft die Benachrichtigungsfunktionen auf, um Sie das Verhalten des Sockets anpassen zu lassen, wenn es benachrichtigt wird.  Beispielsweise könnten Sie **Empfangen** aus der `OnReceive` Benachrichtigungsfunktion auf, d h. auf benachrichtigt werden, dass er Daten gibt, zu lesen, rufen Sie **Empfangen** auf, um ihn zu lesen.  Dieser Ansatz ist nicht erforderlich, aber es ist ein gültiges Szenario.  Alternativ könnten Sie die Benachrichtigungsfunktion, um Status, drucken **ABLAUFVERFOLGUNG** Meldungen nachzuverfolgen, z. B.  
  
 Sie können diese Benachrichtigungen nutzen, indem Sie die in einer abgeleiteten Socketklasse Benachrichtigungsfunktionen überschreiben und eine Implementierung bereitstellen.  
  
 Während eines Vorgangs zum Empfangen oder Senden von Daten, wird ein `CSocket`\-Objekt synchronisiert.  Während des synchronen Zustands werden alle Benachrichtigungen, die für andere Sockets bedeutet werden, in die Warteschlange gestellt, wenn der aktuelle Socket auf die Benachrichtigung wartet, die er wünscht. \(Beispielweise, während **Empfangen** eines Aufrufs, will der Socket eine Benachrichtigung.\) Sobald der Socket den Gleichlaufbetrieb abschließt und erneut asynchron wird, können andere Sockets starten, die in der Warteschlange. Benachrichtigungen Empfangen von  
  
> [!NOTE]
>  In `CSocket` ist die `OnConnect` Benachrichtigungsfunktion nie aufgerufen.  Bei Verbindungen rufen Sie **Verbinden** auf, die zurückgegeben wird, wenn die Verbindung beendet ist \(entweder erfolgreich oder im Fehler\).  Wie Verbindungsbenachrichtigungen bearbeitet werden, ist ein MFC\-Implementierungsdetail.  
  
 Details zu jeder Benachrichtigungsfunktion, finden Sie die Funktion mit `CAsyncSocket`\-Klasse in der *MFC\-Referenz*.  So Quellcode und Informationen über MFC\-Beispiele, finden Sie unter [MFC\-Beispiele](../top/visual-cpp-samples.md).  
  
 Weitere Informationen finden Sie unter:  
  
-   [Windows Sockets: Verwenden der Klasse CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows Sockets: Leiten von den Socket\-Klassen](../mfc/windows-sockets-deriving-from-socket-classes.md)  
  
-   [Windows Sockets: Wie Sockets mit Archiven arbeiten](../mfc/windows-sockets-how-sockets-with-archives-work.md)  
  
-   [Windows Sockets: Blockieren](../mfc/windows-sockets-blocking.md)  
  
-   [Windows Sockets: Bytereihenfolge](../mfc/windows-sockets-byte-ordering.md)  
  
-   [Windows Sockets: Konvertieren von Zeichenfolgen](../mfc/windows-sockets-converting-strings.md)  
  
## Siehe auch  
 [Windows\-Sockets in MFC](../mfc/windows-sockets-in-mfc.md)
---
title: "Windows Sockets: Ableiten von Socket-Classen | Microsoft Docs"
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
  - "Abgeleitete Klassen, aus Socketklassen"
  - "Sockets [C++], Ableiten aus Socketklassen"
  - "Windows-Sockets [C++], Ableiten aus Socketklassen"
ms.assetid: 3a26e67a-e323-433b-9b05-eca018799801
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Windows Sockets: Ableiten von Socket-Classen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Artikel beschreibt einige der Funktionen, die Sie erhalten, indem Sie die eigene Klasse von einer der Socketklassen berechnen.  
  
 Sie können eigene Socketklassen in [CAsyncSocket](../mfc/reference/casyncsocket-class.md) oder von [CSocket](../mfc/reference/csocket-class.md) ableiten, um die eigene Funktionen hinzuzufügen.  Insbesondere können diese Klassen verschiedene virtuelle Memberfunktionen, die Sie überschreiben können.  Diese Funktionen enthalten [OnReceive](../Topic/CAsyncSocket::OnReceive.md), [OnSend](../Topic/CAsyncSocket::OnSend.md), [OnAccept](../Topic/CAsyncSocket::OnAccept.md), [OnConnect](../Topic/CAsyncSocket::OnConnect.md) und [OnClose](../Topic/CAsyncSocket::OnClose.md).  Sie können die Funktionen in der abgeleiteten Socketklasse überschreiben, um die entsprechenden Benachrichtigungen zu nutzen, die sie bereitstellen, wenn Netzwerkereignisse auftreten.  Das Framework ruft diese Benachrichtigungsrückruffunktionen auf, um Sie über wichtige Socketereignissen, wie dem Empfang der Daten zu benachrichtigen, die Sie lesen beginnen können.  Weitere Informationen über Benachrichtigungsfunktionen, finden Sie unter [Windows Sockets: Socket\-Benachrichtigungen](../mfc/windows-sockets-socket-notifications.md).  
  
 Außerdem stellt Klasse `CSocket` die [OnMessagePending](../Topic/CSocket::OnMessagePending.md)\-Memberfunktion \(ein erweitertes schreibbares\).  MFC ruft diese Funktion auf, wenn der Socket Windows\-basierte Meldungen weiterleitet.  Sie können `OnMessagePending` überschreiben, um nach bestimmten Meldungen von Windows zu finden und auf diese reagieren.  
  
 Die Standardversion von `OnMessagePending` des in der Klasse, die `CSocket`, für die Meldungswarteschlange `WM_PAINT` Meldungen während des Wartens auf einen blockierenden Aufruf, indem es überprüft.  Sie leitet Zeichenmeldungen weiter, um Anzeigenqualität zu verbessern.  Neben der Möglichkeit nützliches einige, wird dies veranschaulicht eine Möglichkeit, die u sich die Funktion überschrieben.  Ein weiteres Beispiel sollten Sie die Verwendung von `OnMessagePending` für die folgende Aufgabe.  Angenommen, Sie ein nicht modales Dialogfeld beim Warten auf eine Netzwerktransaktion anzuzeigen, indem es.  Das Dialogfeld enthält eine Schaltfläche Abbrechen, die der Benutzer verwenden kann, um zu Transaktionen abzubrechen, die zu lang dauert.  Ihre `OnMessagePending` Überschreibung pumpte möglicherweise die Meldungen, die an diesem nicht modalen Dialogfeld beziehen.  
  
 In der Überschreibung `OnMessagePending` geben Sie **TRUE** oder der Rückgabe aus einem Aufruf an die Basisklassenversion von `OnMessagePending` zurück.  Rufen Sie die Basisklassenversion aufgelistet, wenn die Arbeit ausführt, die Sie noch fertiges soll.  
  
 Weitere Informationen finden Sie unter:  
  
-   [Windows Sockets: Verwenden von Sockets mit Archiven](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Windows Sockets: Verwenden der Klasse CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows Sockets: Blockieren](../mfc/windows-sockets-blocking.md)  
  
-   [Windows Sockets: Bytereihenfolge](../mfc/windows-sockets-byte-ordering.md)  
  
-   [Windows Sockets: Konvertieren von Zeichenfolgen](../mfc/windows-sockets-converting-strings.md)  
  
## Siehe auch  
 [Windows\-Sockets in MFC](../mfc/windows-sockets-in-mfc.md)
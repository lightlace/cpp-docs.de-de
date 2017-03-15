---
title: "Windows Sockets: Blockieren | Microsoft Docs"
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
  - "Sockets [C++], Streamsockets"
  - "Streamsockets [C++]"
  - "Windows-Sockets [C++], Streamsockets"
ms.assetid: 31faaa34-a995-493f-a30b-b8115293d619
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Windows Sockets: Blockieren
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Artikel beschreibt Streamsockets, einen der beiden verfügbaren Windows Socket\-Typen. \(Die andere Art ist [Datagrammsocket](../mfc/windows-sockets-datagram-sockets.md).\)  
  
 Streamsockets stellen für einen Datenfluss ohne Rekordgrenzen bereit: ein Stream von Bytes, die bidirektional sein können \(die Anwendung, Vollduplex ist: er kann vom Socket senden und empfangen.\)  Streams können auf gebaut werden, um die sequenziell geordnete, unduplicated Daten bereitzustellen. \("Sequenziell Relevanz" bedeutet, dass in Pakete der gesendeten Bestellung geliefert werden. "Unduplicated" bedeutet, dass Sie ein bestimmtes Paket nur einmal. abrufen\) Eingang von Streammeldungen wird sichergestellt, und Streams sind zum Behandeln großer Datenmengen geeignet.  
  
 Die Netzwerktransportschicht Daten in Pakete angemessene Größe aufgliedern oder gruppiert werden.  Die `CSocket`\-Klasse behandelt Verpackung und das Entpacken für Sie.  
  
 Streams basieren auf explizite Verbindungen: Socket A fordert eine Verbindung zum Socket; B Socket B akzeptiert oder weist die Aufforderung zum Aufbau einer Verbindung zurück.  
  
 Ein Telefonanruf stellt eine gute Analogie für einen Stream bereit.  Unter normalen Umständen beendet die empfangende Seite, die Sie in der Reihenfolge, dass Sie bei jeder, ohne Duplikat oder Verlust.  Streamsockets sind beispielsweise für Implementierungen wie das File Transfer Protocol \(FTP\) geeignet, das behandelt, ASCII oder Binärdateien der beliebigen Größe zu übertragen.  
  
 Streamsockets entsprechen den Datagrammsockets vorzuziehen, wenn die Daten festgelegt werden müssen, um anzukommen und wenn Datengröße groß ist.  Weitere Informationen über Streamsockets, finden Sie in der Windows Socket\-Spezifikation.  Die Spezifikation ist unter [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)] verfügbar.  
  
 Verwenden der Streamsockets Anwendungen überlegen sein, die entworfen werden, um einen Datagrammsocket für das Übertragen allen kann das Empfangen, Sockets im Netzwerk verwenden da  
  
-   Das Übertragungsmodell unterliegt Problemen der Netzwerkflut \(oder "Sturms"\).  
  
-   Das client\-server Option, das anschließend angenommen wird, ist effizienter.  
  
-   Das Streammodell stellt zuverlässige Datenübertragung, in der das Datagrammmodell hingegen nicht.  
  
-   Das endgültige Modell nutzt die Möglichkeit, zwischen Unicode zu kommunizieren und ANSI\-Socket\-Anwendungen, die CArchive Klasse, bietet, um CSocket \- Klasse.  
  
    > [!NOTE]
    >  Wenn Sie die `CSocket`\- Klasse verwenden, müssen Sie einen Stream verwenden.  Eine MFC\-Assertion schlägt fehl, wenn Sie den Sockettyp als **SOCK\_DGRAM** angeben.  
  
## Siehe auch  
 [Windows\-Sockets in MFC](../mfc/windows-sockets-in-mfc.md)   
 [Windows Sockets: Hintergrund](../mfc/windows-sockets-background.md)
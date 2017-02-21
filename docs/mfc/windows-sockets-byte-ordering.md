---
title: "Windows Sockets: Bytereihenfolge | Microsoft Docs"
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
  - "Bytereihenfolgeprobleme bei der Socketprogrammierung"
  - "Sockets [C++], Bytereihenfolgenprobleme"
  - "Windows-Sockets [C++], Bytereihenfolgenprobleme"
ms.assetid: 8a787a65-f9f4-4002-a02f-ac25a5dace5d
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Windows Sockets: Bytereihenfolge
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Artikel und zwei Begleitartikel beschreiben einige Probleme bei der Windows Socket\-Programmierung.  Dieser Artikel enthüllt Bytereihenfolge ab.  Die anderen Probleme sind in den Artikeln behandelt: [Windows Sockets: Blockieren](../mfc/windows-sockets-blocking.md) und [Windows Sockets: Konvertieren von Zeichenfolgen](../mfc/windows-sockets-converting-strings.md).  
  
 Wenn Sie von der [CAsyncSocket](../mfc/reference/casyncsocket-class.md) verwenden oder leiten, müssen Sie diese Probleme selbst verwalten.  Wenn Sie von der [CSocket](../mfc/reference/csocket-class.md) verwenden oder leiten, verwaltet MFC sie für Sie.  
  
## Bytereihenfolge  
 Verschiedene Speichern der Computerarchitekturen manchmal mit unterschiedlichen Bytereihenfolgen.  Beispielsweise Computerspeicherdaten Intel\-basierte in umgekehrter Reihenfolge von Computern Macintoshs \(Motorola\).  Die Intel\-Bytereihenfolge, aufgerufen "aufweist," ist ebenfalls die Umkehrung der Netzwerkstandard" Big\-Endian\-" Reihenfolge.  Die folgende Tabelle erläutert diese Begriffe.  
  
### Groß\- und Little\-Endian\-Bytereihenfolge  
  
|Bytereihenfolge|Bedeutung|  
|---------------------|---------------|  
|Big\-Endian|Das höchstwertige Byte ist am linken Ende eines Wortes.|  
|Little\-Endian|Das höchstwertige Byte ist am rechten Ende eines Wortes.|  
  
 In der Regel müssen Sie sich nicht um Bytereihenfolgenkonvertierung für Daten kümmern, die Sie über das Netzwerk senden und empfangen, es gibt jedoch Situationen, in denen Sie Bytereihenfolgen konvertieren müssen.  
  
## Wenn Sie Bytereihenfolgen konvertieren müssen  
 Sie müssen Bytereihenfolgen in den folgenden Situationen konvertieren:  
  
-   Sie übergeben Informationen, die durch das Netzwerk interpretiert werden müssen, im Gegensatz zu den Daten, die Sie zu einem anderen Computer senden.  Beispielsweise können Sie Anschlüsse und Adressen, die das Netzwerk zu verstehen.  
  
-   Die Serveranwendung, mit der Sie kommunizieren, ist keine MFC\-Anwendung \(und haben Sie nicht Quellcode für ihn\).  In Aufrufen für Bytereihenfolgenkonvertierungen, wenn die zwei Computer nicht derselben Bytereihenfolge freigeben.  
  
## Wenn Sie nicht Bytereihenfolgen konvertieren müssen  
 Sie können die Arbeit zum Konvertieren von Bytereihenfolgen in den folgenden Situationen vermeiden:  
  
-   Die Computer an beiden Enden können damit einverstanden sein, Bytes nicht auszutauschen, und beide Computer verwenden dieselbe Bytereihenfolge.  
  
-   Der Server, den Sie mit kommunizieren, ist eine MFC\-Anwendung.  
  
-   Sie können Quellcode für den Server, den Sie mit kommunizieren, sodass Sie explizit feststellen, ob Sie Bytereihenfolgen konvertieren müssen oder nicht.  
  
-   Sie können den Server mit MFC portieren.  Dies ist recht einfach zu verwenden, und das Ergebnis ist normalerweise kleinerer, schnellerer Code.  
  
 gemeinsam mit [CAsyncSocket](../mfc/reference/casyncsocket-class.md), müssen Sie alle erforderlichen Bytereihenfolgenkonvertierungen selbst verwalten.  Windows Sockets standardisiert das "Big\-Endian\-" Bytereihenfolgenmodell und stellt Funktionen zum Konvertieren zwischen dieser Reihenfolge und andere bereit.  [CArchive](../mfc/reference/carchive-class.md) durch die Sie mit [CSocket](../mfc/reference/csocket-class.md) verwenden, verwendet die gegenüberliegende Little\-Endian \(""\) Reihenfolge, aber `CArchive` anzeigen um die Details von Bytereihenfolgenkonvertierungen für Sie.  Mit dieser Standardreihenfolge in Anwendungen verwenden, oder Windows Socket\-Bytereihenfolgenkonvertierungsfunktionen verwenden, können Sie den Code besser portierbar machen.  
  
 Das ideale Argument für die Verwendung von MFC\-Sockets ist, wenn Sie beide Enden der Kommunikation schreiben und dabei eine MFC\-Bibliothek an beiden Enden verwenden.  Wenn Sie schreiben, muss eine Anwendung, die Nicht\-MFC\-Anwendungen, wie Sie einen FTP\-Server, ist wahrscheinlich, ByteAuslagerung selbst verwalten, bevor Sie Daten zum Archivobjekt, mit Windows Socket\-Konvertierungsroutinen **ntohs**, **ntohl**, **htons** und **htonl** übergeben.  Ein Beispiel dieser Funktionen, die verwendet werden, beim, Kommunikation mit einer Nicht\-MFC\-Anwendung später in diesem Artikel.  
  
> [!NOTE]
>  Wenn das andere Ende der Kommunikation keine MFC\-Anwendung ist, müssen Sie C\+\+\-Objekte, auf einmal auch vermeiden, die von `CObject` in das Archiv abgeleitet werden, da der Empfänger nicht möglich ist, sie zu behandeln.  Siehe den Hinweis in [Windows Sockets: Verwenden der Archiven Sockets mit](../mfc/windows-sockets-using-sockets-with-archives.md).  
  
 Weitere Informationen über Bytereihenfolgen, finden Sie in der Windows Socket\-Spezifikation, die in [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)] verfügbar ist.  
  
## Ein Bytereihenfolgen\-Konvertierungs\-Beispiel  
 Das folgende Beispiel zeigt eine Serialisierungsfunktionen für ein `CSocket`\-Objekt, das ein " verwendet.  Es veranschaulicht auch mithilfe der Bytereihenfolgenkonvertierungsfunktionen in der Windows Sockets API.  
  
 In diesem Beispiel wird ein Szenario dar, in dem Sie einen Client schreiben, der mit einer Nicht\-MFC\-Serveranwendung kommuniziert, für die Sie keinen Zugriff auf den Quellcode haben.  In diesem Szenario müssen Sie davon ausgehen, dass der Nicht\-MFC\-Server Standardnetzwerk\-bytereihenfolge verwendet.  Im Gegensatz dazu verwendet die MFC\-Clientanwendung ein `CArchive`\-Objekt mit einem `CSocket`\-Objekt und `CArchive` Verwenden Sie Little\-Endian\-" Bytereihenfolge, die Invertierung des Netzwerkstandards.  
  
 Angenommen, der Nicht\-MFC\-Server, mit dem Sie planen, beteiligten Personen ein, eingerichtetes Protokoll für ein Meldungspaket wie die folgenden Funktionen:  
  
 [!CODE [NVC_MFCSimpleSocket#5](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCSimpleSocket#5)]  
  
 In MFC\-Begriffen würde dies ausgedrückt, wie folgt:  
  
 [!CODE [NVC_MFCSimpleSocket#6](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCSimpleSocket#6)]  
  
 In C\+\+ ist `struct` im Grunde dieselbe Aufgabe wie eine Klasse.  Die `Message`\-Struktur kann Memberfunktionen, wie die `Serialize`\-Memberfunktion aufweisen, die oben deklariert wird.  Die Memberfunktion `Serialize` könnte folgendermaßen aussehen:  
  
 [!CODE [NVC_MFCSimpleSocket#7](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCSimpleSocket#7)]  
  
 Aufrufe dieses Beispiels für Bytereihenfolgenkonvertierungen von Daten, da es einen klaren Konflikt zwischen der Bytereihenfolge der Nicht\-MFC\-Serveranwendung an einem Ende mit `CArchive`, das in der MFC\-Clientanwendung des anderen verwendet werden wird, beenden.  Das Beispiel veranschaulicht mehrere der Bytereihenfolgenkonvertierungsfunktionen dass Windows Socket\-Zubehör.  In der folgenden Tabelle werden die Funktionen.  
  
### Windows Socket\-Bytereihenfolgen\-Konvertierungsfunktionen  
  
|Funktion|Zweck|  
|--------------|-----------|  
|**ntohs**|Konvertieren einer 16\-Bit\-Menge von Netzwerk\-Bytereihenfolge zu Host\-Bytereihenfolge \(Big\-Endian in Little\-Endian\).|  
|**ntohl**|Konvertieren einer 32\-Bit\-Menge von Netzwerk\-Bytereihenfolge zu Host\-Bytereihenfolge \(Big\-Endian in Little\-Endian\).|  
|**Htons**|Konvertieren einer 16\-Bit\-Menge von Host\-Bytereihenfolge zu Netzwerk\-Bytereihenfolge Little\-Endian \(z Big\-Endian\).|  
|**Htonl**|Konvertieren einer 32\-Bit\-Menge von Host\-Bytereihenfolge zu Netzwerk\-Bytereihenfolge Little\-Endian \(z Big\-Endian\).|  
  
 Ein anderer Stelle dieses Beispiels ist, dass, wenn die Socket\-Anwendung am anderen Ende der Kommunikation eine Nicht\-MFC\-Anwendung ist, Sie in etwa, um Folgendes auszuführen vermeiden müssen:  
  
 `ar << pMsg;`  
  
 wobei `pMsg` ein Zeiger auf ein C\+\+\-Objekt ist, das von der `CObject`\- Klasse abgeleitet wird.  Dieses werden zusätzliche MFC\-Informationen, die mit Objekten zugeordnet und der Server erkennt sie nicht, wie sie war, wenn eine MFC\-Anwendung war.  
  
 Weitere Informationen finden Sie unter:  
  
-   [Windows Sockets: Verwenden der Klasse CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows Sockets: Hintergrund](../mfc/windows-sockets-background.md)  
  
-   [Windows Sockets: Streamsockets](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows Sockets: Datagrammsockets](../mfc/windows-sockets-datagram-sockets.md)  
  
## Siehe auch  
 [Windows\-Sockets in MFC](../mfc/windows-sockets-in-mfc.md)
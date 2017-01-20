---
title: "Windows Sockets: Verwenden der CAsyncSocket-Klasse"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "CAsyncSocket"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAsyncSocket-Klasse, Programmiermodell"
  - "SOCKET-Handle"
  - "Sockets [C++], Asynchroner Vorgang"
  - "Sockets [C++], Konvertieren zwischen Unicode und MBCS-Zeichenfolgen"
  - "Windows-Sockets [C++], Asynchron"
  - "Windows-Sockets [C++], Konvertieren von Unicode und MBCS-Zeichenfolgen"
ms.assetid: 825dae17-7c1b-4b86-8d6c-da7f1afb5d8d
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Windows Sockets: Verwenden der CAsyncSocket-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In diesem Artikel wird beschrieben, wie [CAsyncSocket](../mfc/reference/casyncsocket-class.md)\- Klasse verwendet.  Beachten Sie, dass diese Klasse die Windows Sockets API zu einem sehr wenig kapselt.  `CAsyncSocket` ist für Programmierer, die Netzwerkkommunikationen ausführlich kennen, jedoch keine die Hilfe der Rückrufe für eine Benachrichtigung über Netzwerkereignissen.  Auf Grundlage diese Annahme legt dieser Artikel nur grundlegende Anweisung fest.  Sie sollten `CAsyncSocket` zu verwenden, wahrscheinlich, sollten, wenn Sie die einfache der Windows Sockets des Beschäftigens mehrere Netzwerkprotokolle in einer MFC\-Anwendung möchten, möchten aber nicht Flexibilität opfern.  Sie sicher fühlten auch, dass Sie eine höhere Effizienz abrufen können, indem Sie direkt die Kommunikation sich programmieren, als Sie können mit den allgemeineren alternativen Modell der Klasse `CSocket`.  
  
 `CAsyncSocket` wird in der *MFC\-Referenz* dokumentiert.  Visual C\+\+ bietet auch die Windows Socket\-Spezifikation, in [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  Die Details werden Ihnen überlassen.  Visual C\+\+ bietet keine Beispielanwendung für `CAsyncSocket`.  
  
 Wenn Sie nicht über Netzwerkkommunikationen hoch sind und sich eine einfache Lösung möchten, Verwendungsklasse [CSocket](../mfc/reference/csocket-class.md) mit einem `CArchive`\-Objekt.  Weitere Informationen finden Sie unter [Windows Sockets: Verwenden der Archiven Sockets mit](../mfc/windows-sockets-using-sockets-with-archives.md).  
  
 Dieser Artikel werden ab:  
  
-   Ein `CAsyncSocket`\-Objekt erstellen und mit.  
  
-   [die Verantwortung mit CAsyncSocket](#_core_your_responsibilities_with_casyncsocket).  
  
##  <a name="_core_creating_and_using_a_casyncsocket_object"></a> Hinzufügen eines CAsyncSocket\-Objekt erstellen und mit  
  
#### So CAsyncSocket verwenden  
  
1.  Erstellen Sie ein [CAsyncSocket](../mfc/reference/casyncsocket-class.md)\-Objekt und verwenden Sie das Objekt, um das zugrunde liegende **SOCKET** Handle zu erstellen.  
  
     Erstellung eines Sockets folgt dem MFC\-Muster der zweistufigen Konstruktion.  
  
     Beispiel:  
  
     [!CODE [NVC_MFCSimpleSocket#3](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCSimpleSocket#3)]  
  
     \- oder \-  
  
     [!CODE [NVC_MFCSimpleSocket#4](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCSimpleSocket#4)]  
  
     Der erste oben stehenden Konstruktor erstellt ein `CAsyncSocket`\-Objekt auf dem Stapel.  Der zweite Konstruktor erstellt `CAsyncSocket` für den Heap.  Der erste [Erstellen](../Topic/CAsyncSocket::Create.md) Aufruf oben verwendet die Standardparameter, um einen Streamsocket zu erstellen.  Der zweite Aufruf **Erstellen** erstellt einen Datagrammsocket mit einem angegebenen Anschluss und eine Adresse. \(Sie können jede **Erstellen**\-Version mit jedem Bauverfahren verwenden.\)  
  
     Die Parameter an **Erstellen** sind:  
  
    -   Ein Port": " eine kurze ganze Zahl.  
  
         Für einen Serversocket müssen Sie einen Port angeben.  Für einen Clientsocket Übernehmen Sie in der Regel den Standardwert für diesen Parameter, der Windows Sockets einen Port auswählen können.  
  
    -   Ein Sockettyp: **SOCK\_STREAM** \(Standardwert\) oder **SOCK\_DGRAM**.  
  
    -   Ein Socket "Address," z "ftp.microsoft.com" oder "128.56.22.8".  
  
         Dies ist die Internetprotokoll \(ip\)\- Adresse im Netzwerk.  Erstellen Sie wahrscheinlich immer auf den Standardwert für diesen Parameter.  
  
     Die Begriffe "Port" und "Socketadresse" werden in [Windows Sockets: Anschlüsse und Socket\-Adressen](../mfc/windows-sockets-ports-and-socket-addresses.md) erläutert.  
  
2.  Wenn der Client ein Socket ist, schließen Sie das Socketobjekt zu einem Serversocket, mit [CAsyncSocket::Connect](../Topic/CAsyncSocket::Connect.md) an.  
  
     \- oder \-  
  
     Wenn der Socket ein Server ist, legen Sie den Socket fest, um Lauschen \(mit [CAsyncSocket::Listen](../Topic/CAsyncSocket::Listen.md)\) für zu starten herstellen Versuche von einem Client.  Bei Empfang einer Aufforderung zum Aufbau einer Verbindung, akzeptieren Sie sie mit dem [CAsyncSocket::Accept](../Topic/CAsyncSocket::Accept.md).  
  
     Nachdem Sie eine Verbindung akzeptiert haben, können Sie diese Aufgaben wie Kennwörter, Überprüfung durchführen.  
  
    > [!NOTE]
    >  Die **Annehmen**\-Memberfunktion übernimmt einen Verweis in einem neuen, leeren `CSocket`\-Objekt als Parameter.  Sie müssen dieses Objekt erstellen, bevor Sie **Annehmen** aufrufen.  Wenn dieses Socketobjekt den Bereich verlässt, wird die Verbindung.  Rufen Sie **Erstellen** nicht für dieses neue Socketobjekt auf.  Ein Beispiel finden Sie im Artikel [Windows Sockets: Sequenz von Vorgängen](../mfc/windows-sockets-sequence-of-operations.md).  
  
3.  Führen Sie Kommunikation mit anderen Sockets durch, indem Sie die Memberfunktionen `CAsyncSocket` des Objekts aufrufen, die die Windows Socket\-API\-Funktionen kapseln.  
  
     Siehe die Windows Sockets Spezifikation und [CAsyncSocket](../mfc/reference/casyncsocket-class.md) in der *MFC\-Referenz*.  
  
4.  Zerstören Sie das `CAsyncSocket`\-Objekt.  
  
     Wenn Sie das Socketobjekt auf dem Stapel erstellt haben, wird ihr Destruktor aufgerufen, wenn die enthaltende Funktion den Bereich verlässt.  Wenn Sie das Socketobjekt im Heap, mithilfe des Operators **neu** erstellt haben, sind Sie für die Anwendung des Operators **löschen**, um das Objekt zu zerstören zuständig.  
  
     Der Destruktor ruft die [Schließen](../Topic/CAsyncSocket::Close.md)\-Memberfunktion des Objekts auf, bevor das Objekt zerstört.  
  
 Ein Beispiel für diese Sequenz im Code \(tatsächlich für `CSocket`\-Objekt\), finden Sie unter [Windows Sockets: Sequenz von Vorgängen](../mfc/windows-sockets-sequence-of-operations.md).  
  
##  <a name="_core_your_responsibilities_with_casyncsocket"></a> die Verantwortung mit CAsyncSocket  
 Wenn Sie ein Objekt der Klasse [CAsyncSocket](../mfc/reference/casyncsocket-class.md) erstellen, enthält das Objekt ein Handle von **SOCKET** und stellt Vorgänge auf dieses Handle.  Wenn Sie `CAsyncSocket` verwenden, müssen Sie alle Probleme behandeln, die möglicherweise gegenüberstellten, wenn Sie entweder direkt die API verwenden.  Beispiel:  
  
-   Szenarien "Blockierung".  
  
-   Bytereihenfolgenunterschiede zwischen den sendenden empfangenden und Computern.  
  
-   Konvertieren zwischen Unicode und Zeichenfolgen Mehrbyte\-Zeichensätze \(MBCS\).  
  
 Definitionen dieser Begriffe sowie weitere Informationen, finden Sie unter [Windows Sockets: Blockieren](../mfc/windows-sockets-blocking.md), [Windows Sockets: Bytereihenfolge](../mfc/windows-sockets-byte-ordering.md), [Windows Sockets: Konvertieren von Zeichenfolgen](../mfc/windows-sockets-converting-strings.md).  
  
 Trotz dieser Probleme ist möglicherweise Klasse **CAsycnSocket** die richtige Wahl für Sie, wenn die Anwendung die ganze Flexibilität erfordert und steuern können Sie abrufen.  Wenn nicht, sollten Sie Klasse, stattdessen `CSocket` zu empfehlen.  `CSocket` blendet viele Details von Ihnen aus: Windows\-Meldungen weiterleitet es während des Blockierens von Aufrufen und gibt Ihnen Zugriff auf `CArchive`, der Bytereihenfolgenunterschiede und Zeichenfolgenkonvertierung für Sie verwaltet.  
  
 Weitere Informationen finden Sie unter:  
  
-   [Windows Sockets: Hintergrund](../mfc/windows-sockets-background.md)  
  
-   [Windows Sockets: Streamsockets](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows Sockets: Datagrammsockets](../mfc/windows-sockets-datagram-sockets.md)  
  
## Siehe auch  
 [Windows\-Sockets in MFC](../mfc/windows-sockets-in-mfc.md)
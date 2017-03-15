---
title: "Windows Sockets: Beispiel f&#252;r das Verwenden von Sockets mit Archiven | Microsoft Docs"
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
  - "Beispiele [MFC], Windows-Sockets"
  - "Sockets [C++], mit Archiven"
  - "Windows-Sockets [C++], mit Archiven"
ms.assetid: 2e3c9bb2-7e7b-4f28-8dc5-6cb7a484edac
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Windows Sockets: Beispiel f&#252;r das Verwenden von Sockets mit Archiven
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Artikel legt ein Beispiel der Anwendungsklasse [CSocket](../mfc/reference/csocket-class.md).  Das Beispiel setzt `CArchive`\-Objekte, um Daten über einen Socket zu serialisieren.  Beachten Sie, dass diese keine Dokumentserialisierung nach oder einer Datei.  
  
 Das folgende Beispiel veranschaulicht, wie Sie das Archiv verwenden, um Daten von `CSocket`\-Objekte zu senden und zu empfangen.  Das Beispiel ist damit zwei Instanzen der Daten der Anwendung \(auf demselben Computer oder auf unterschiedlichen Computern im Netzwerk\) vorgesehen.  Eine Instanz sendet Daten, die die weitere Instanz empfängt und bestätigt.  Jede Anwendung kann einem Austausch initiieren, und jede kann als Server oder Client als die andere Anwendung auftreten.  Die folgende Funktion wird in der Ansichtsklasse der Anwendung definiert:  
  
 [!CODE [NVC_MFCSimpleSocket#1](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCSimpleSocket#1)]  
  
 Die wichtigste Aufgabe über dieses Beispiel ist die Strukturähnlichkeiten, die von einem `Serialize` MFC Sie arbeiten.  Die **PacketSerialize**\-Memberfunktion besteht aus einer **if**\-Anweisung mit einer **else**\-Klausel.  Die Funktion erhält [CArchive](../mfc/reference/carchive-class.md) zwei Verweise als Parameter: `arData` und `arAck`.  Wenn das `arData` Archivobjekt zum Speichern \(Senden\) festgelegt ist, wird die **if** Verzweigung aus; andernfalls wenn `arData` für Laden \(Empfangen\) festgelegt wird verwendet die Funktion **else** Verzweigung.  Weitere Informationen zur Serialisierung in MFC, finden Sie unter [Serialisierung](../mfc/how-to-make-a-type-safe-collection.md).  
  
> [!NOTE]
>  Das `arAck` Archivobjekt wird angenommen, dass das Gegenteil von `arData`.  Wenn `arData` zum Senden ist, erhält `arAck`, und das Gegenteil gilt.  
  
 Für das Senden durchläuft die Beispielfunktion für eine angegebene Anzahl von Wiederholungen und jedes Mal generiert eine zufällige Daten für Demonstration, vorgesehen.  die Anwendung würde echte Daten aus einer beliebigen Quelle, wie einer Datei abrufen.  Der `arData` des Einfügungsoperator Archivs \(**\<\<**\) wird verwendet, um einen Stream aus drei aufeinander Blöcke von Daten zu senden:  
  
-   Eine "Kopfzeile" die die Art der Daten angibt \(in diesem Fall, der Wert der Variable `bValue` und viele Kopien bereitgestellt werden\).  
  
     Beide Elemente werden nach dem Zufallsprinzip für dieses Beispiel generiert.  
  
-   Die angegebene Anzahl von Kopien der Daten.  
  
     Die innere Schleife **für** sendet die `bValue` angegebene Anzahl Zeitangaben.  
  
-   Eine Zeichenfolge namens `strText`, die der Empfänger zu dessen Benutzer anzeigt.  
  
 Für das Empfangen funktioniert die Funktion ähnlich, allerdings wird der Extraktionsoperator des Archivs \(**\>\>**\) können Daten aus dem Archiv abzurufen.  Die empfangende Anwendung überprüft die Daten, die sie erhält, wird die "empfangene Meldung des endgültigen" an, und sendet dann eine Meldung zurück, die "übermittelt" besagt, sodass die sendende Anwendung angezeigt wird.  
  
 In diesem modelliert Kommunikation, das Wort, die Meldung ", die empfangen wird", die in der Variablen `strText` gesendet wird, ist für die Anzeige am anderen Ende der Kommunikation, sodass sie z empfangenden Benutzer an, dass verschiedene Pakete Daten empfangen wurden.  Der Empfänger antwortet mit einer ähnlichen Zeichenfolge, die "übermittelt" besagt, für die Anzeige auf dem ersten Bildschirm des Absenders.  Eingang beider Zeichenfolgen gibt an, dass eine erfolgreiche Kommunikation aufgetreten ist.  
  
> [!CAUTION]
>  Wenn Sie ein MFC\-Clientprogramm schreiben, um mit den festgelegten \(Nicht\-MFC\-\) Servern zu kommunizieren, senden Sie C\+\+\-Objekte nicht durch das Archiv.  Sofern, dass der Server eine MFC\-Anwendung, die den Arten von Objekten, versteht Sie senden möchten, ist unklar, die Objekte zum Empfangen und zu deserialisieren.  Ein Beispiel im Artikel [Windows Sockets: Bytereihenfolge](../mfc/windows-sockets-byte-ordering.md) zeigt eine Kommunikation dieses Typs dargestellt.  
  
 Weitere Informationen finden Sie Socket\-Spezifikation Windows: **htonl**, **htons**, **ntohl**, **ntohs**.  Außerdem weitere Informationen, finden Sie unter:  
  
-   [Windows Sockets: Leiten von den Socket\-Klassen](../mfc/windows-sockets-deriving-from-socket-classes.md)  
  
-   [Windows Sockets: Wie Sockets mit Archiven arbeiten](../mfc/windows-sockets-how-sockets-with-archives-work.md)  
  
-   [Windows Sockets: Hintergrund](../mfc/windows-sockets-background.md)  
  
## Siehe auch  
 [Windows\-Sockets in MFC](../mfc/windows-sockets-in-mfc.md)   
 [CArchive::IsStoring](../Topic/CArchive::IsStoring.md)   
 [CArchive::operator \<\<](../Topic/CArchive::operator%20%3C%3C.md)   
 [CArchive::operator \>\>](../Topic/CArchive::operator%20%3E%3E.md)   
 [CArchive::Flush](../Topic/CArchive::Flush.md)   
 [CObject::Serialize](../Topic/CObject::Serialize.md)
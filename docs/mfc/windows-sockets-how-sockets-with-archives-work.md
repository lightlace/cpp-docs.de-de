---
title: "Windows Sockets: Wie Sockets mit Archiven arbeiten | Microsoft Docs"
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
  - "Sockets [C++], Synchroner Vorgang"
  - "Sockets [C++], mit Archiven"
  - "Synchroner Statussocket"
  - "Socketobjekt mit zwei Zuständen"
  - "Windows-Sockets [C++], synchron"
  - "Windows-Sockets [C++], mit Archiven"
ms.assetid: d8ae4039-391d-44f0-a19b-558817affcbb
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Windows Sockets: Wie Sockets mit Archiven arbeiten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Artikel wird beschrieben, wie ein Objekt [CSocket](../mfc/reference/csocket-class.md), ein [CSocketFile](../mfc/reference/csocketfile-class.md) und ein [CArchive](../mfc/reference/carchive-class.md)\-Objekt Objekt kombiniert werden, um das Senden und Empfangen von Daten von einem Windows Socket zu vereinfachen.  
  
 Der Artikel [Windows Sockets: Beispiel aus Sockets mit Archive](../mfc/windows-sockets-example-of-sockets-using-archives.md) stellt die **PacketSerialize**\-Funktion dar.  Das Archivobjekt in den **PacketSerialize** Beispielsarbeiten ähnlich wie ein Archivobjekt an einer MFC\-Funktion [Serialisieren Sie](../Topic/CObject::Serialize.md).  Der Hauptunterschied ist der für Sockets, das Archiv wird angefügt nicht auf einen Standard\- [Die C\-Datei](../mfc/reference/cfile-class.md)\-Objekt \(in der Regel zugeordnet einer Datenträgerdatei\) jedoch auf ein `CSocketFile`\-Objekt.  Anstatt, anschließend mit einer Datenträgerdatei, schließt das `CSocketFile`\-Objekt an `CSocket` ein Objekt an.  
  
 Ein `CArchive`\-Objekt verwaltet einen Puffer.  Wenn der Puffer einer speichernden \(sendenden\) Archivs voll ist, schreibt ein zugeordnetes `CFile`\-Objekt den Inhalt des Puffers aus.  Die Puffer einer Archivs zu leeren, das an einen Socket angefügt wird, ist zum Senden einer Nachricht entsprechend.  Wenn der Puffer des Archivs des Ladens \(Empfangen\) ist voll, wird das Objekt auf `CFile` zu lesen, bis, der Puffer wieder verfügbar ist.  
  
 Klasse `CSocketFile` wird von `CFile` abgeleitet, aber nicht unterstützt [Die C\-Datei](../mfc/reference/cfile-class.md)\-Memberfunktionen wie der Positionierungstools Funktionen \(`Seek`, `GetLength`, `SetLength`, z.\), die Sperre funktioniert \(`LockRange`, `UnlockRange`\) oder die `GetPosition`\-Funktion.  Alle [CSocketFile](../mfc/reference/csocketfile-class.md)\-Objekt muss es allerdings zu schreiben, oder, Bytefolgen oder nach der zugeordneten `CSocket` zu lesen Objekts.  Da keine Datei aktiviert ist, sind Operationen wie `Seek` und `GetPosition` nicht sinnvoll.  `CSocketFile` wird von `CFile` berechnet, daher könnte es normalerweise alle dieser Memberfunktionen erben.  Um dies zu verhindern, werden die nicht unterstützten `CFile`\-Memberfunktionen in `CSocketFile` überschrieben um [CNotSupportedException](../mfc/reference/cnotsupportedexception-class.md) auslöst.  
  
 Die `CSocketFile`\-Objektaufrufsmemberfunktionen vom `CSocket`\-Objekt, um Daten zu senden oder zu empfangen.  
  
 Die folgende Abbildung zeigt die Beziehungen zwischen diesen Objekten auf beiden Seiten von der Kommunikation an.  
  
 ![CArchive, CSocketFile und CSocket](../mfc/media/vc38ia1.png "vc38IA1")  
CArchive, CSocketFile und CSocket  
  
 Der Zweck dieser naheliegenden Komplexität ist, von der Notwendigkeit Verwaltung der Details des Sockets sich abzuschirmen.  Sie stellen den Socket, die Datei und das Archiv erstellt und beginnen dann das Senden oder das Empfangen von Daten, indem Sie es im Archiv einfügen oder sie aus dem Archiv extrahieren.  [CArchive](../mfc/reference/carchive-class.md), [CSocketFile](../mfc/reference/csocketfile-class.md) und [CSocket](../mfc/reference/csocket-class.md) verwalten die Details im Hintergrund.  
  
 Ein `CSocket`\-Objekt ist eigentlich ein ZweiZustandsobjekt: manchmal asynchron \(der übliche Zustand\) und manchmal synchronisiert.  In seinem asynchronen Zustand kann ein Socket asynchrone Benachrichtigungen vom Framework erhalten.  Während eines Vorgangs zum Empfangen oder Senden von Daten wird der Socket synchron.  Dies bedeutet, dass der nicht Socket weitere asynchrone Benachrichtigungen empfängt, bis der Gleichlaufbetrieb abgeschlossen wurde.  Da Modi umschaltet, können Sie in etwa Folgendes beispielsweise folgendermaßen:  
  
 [!CODE [NVC_MFCSimpleSocket#2](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCSimpleSocket#2)]  
  
 Wenn `CSocket` nicht implementiert wurden, während ein ZweiZustandsobjekt, es möglich ist, zusätzliche Benachrichtigungen für die gleiche Art von Ereignissen zu empfangen, während Sie eine vorherige Benachrichtigungen verarbeiteten.  Beispielsweise könnten Sie eine `OnReceive` Benachrichtigung während der Verarbeitung von `OnReceive` ab.  im Codefragment oben, könnte das Extrahieren möglicherweise von `str` aus dem Archiv zu Rekursion.  Wenn Sie Zustände wechselt, verhindert `CSocket` Rekursion, indem zusätzliche Benachrichtigungen verhindert.  Die allgemeine Regel lautet keine Benachrichtigungen innerhalb der Benachrichtigungen.  
  
> [!NOTE]
>  `CSocketFile` kann bei \(eingeschränkte\) Datei eine ohne ein `CArchive`\-Objekt auch verwendet werden.  Standardmäßig ist der `CSocketFile` des `bArchiveCompatible`\-Parameter Konstruktors **TRUE**.  Dies gibt an, dass das Dateiobjekt zur Verwendung in einem Archiv ist.  Um das Dateiobjekt ohne ein Archiv zu verwenden, führen Sie für **FALSE** im Parameter `bArchiveCompatible`.  
  
 In seinem kompatiblen" Modus "des Archivs stellt ein `CSocketFile`\-Objekt bessere Leistung reduziert und die Gefahr eines Deadlocks "." Ein Deadlock tritt auf, wenn die sendenden und empfangenden Sockets aufeinander warten, auf oder, auf eine gemeinsam genutzte Ressource wartet.  Diese Situation kann eintreten, wenn das `CArchive`\-Objekt bearbeitet mit `CSocketFile`\-Methode, die sie mit einem `CFile`\-Objekt ausführt.  Mit `CFile` kann das Archiv annehmen, dass, wenn weniger Bytes als, empfängt es hat, ist das Dateiende erreicht wurde.  Mit `CSocketFile` sind jedoch Daten die abfragebasierte Meldung; Der Puffer kann mehrere Nachrichten, sodass das Empfangen weniger, als enthalten die Anzahl von Bytes angefordert nicht Dateiende bedeutet.  Die Anwendung blockiert nicht in diesem Fall, wie sie mit `CFile` kann, und sie Lesenmeldungen aus dem Puffer fortfahren kann, bis der Puffer leer ist.  Die [IsBufferEmpty](../Topic/CArchive::IsBufferEmpty.md)\-Funktion in `CArchive` ist für den Zustand des Puffers des Archivs in einem solchen Fall überwachen nützlich.  
  
 Weitere Informationen finden Sie unter [Windows Sockets: Verwenden der Archiven Sockets mit](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
## Siehe auch  
 [Windows\-Sockets in MFC](../mfc/windows-sockets-in-mfc.md)   
 [CObject::Serialize](../Topic/CObject::Serialize.md)
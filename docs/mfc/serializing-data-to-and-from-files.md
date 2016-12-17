---
title: "Serialisieren von Daten in und aus Dateien"
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
  - "Daten [MFC]"
  - "Daten [MFC], Serialisieren"
  - "Deserialisierung [C++]"
  - "Dokumentdaten [C++]"
  - "Dokumente [C++], Speichern"
  - "Dokumente [C++], Serialisierung"
  - "Speichern von Dokumenten"
  - "Serialisierung [C++], Rolle der Daten"
  - "Serialisierung [C++], Rolle des Dokuments"
ms.assetid: b42a0c68-4bc4-4012-9938-5433a26d2c24
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Serialisieren von Daten in und aus Dateien
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Grundidee der Dauerhaftigkeit ist, dass ein Objekt in der Lage sein sollte, den aktuellen Zustand zu schreiben, der die Werte ihrer Membervariablen, permanenten Speicher.  Später kann das Objekt neu erstellt werden, indem liest, "," oder der Zustand im permanentem Speicher deserialisiert.  A\-TASTEen\-Punkt hier darin, dass das Objekt selbst für das Lesen und Schreiben von eigenen Zustand zuständig ist.  Somit für eine Klasse ist dauerhaft, muss er die grundlegenden Serialisierungsvorgänge implementieren.  
  
 Das Framework stellt eine Standardimplementierung zum Speichern von Dokumenten auf Datenträgerdateien als Reaktion auf den Speicherungs\- und speichern als Befehle im Menü Datei und zum Laden von Dokumenten von Datenträgerdateien auf den geöffneten Befehl verfügbar.  Mit relativ wenige Aufgaben können Sie die Möglichkeit eines Dokuments implementieren, die von Daten für eine Datei zu schreiben und zu lesen.  Die Hauptsache, die Sie ausführen müssen, ist, die unter [Serialisieren Sie](../Topic/CObject::Serialize.md) in der Memberfunktion Dokumentklasse zu überschreiben.  
  
 Der MFC\-Anwendungs\-Assistent platziert eine skelettartige Überschreibung der **CDocument**\-Memberfunktion `Serialize` in der Dokumentklasse, die sie für Sie erstellt.  Nachdem Sie die Membervariablen der Anwendung implementiert haben, können Sie Ihre `Serialize` Überschreibung mit Code füllen, der die Daten in einen "Archivobjekt sendet", das an einer Datei besteht.  Ein [CArchive](../mfc/reference/carchive-class.md)\-Objekt ist an `cin` und `cout` Eingabe\/Ausgabe\-Objekten von der C\+\+\-iostream Bibliothek ähnlich.  `CArchive` schreibt jedoch und liest Binärformat, nicht formatierten Text.  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Serialisierung](../mfc/serialization-in-mfc.md)  
  
-   [Die Rolle des Dokuments in der Serialisierung](#_core_the_document.92.s_role_in_serialization)  
  
-   [Die Rolle der Daten in der Serialisierung](#_core_the_data.92.s_role_in_serialization)  
  
-   [Umgehen des Serialisierungsmechanismus](../mfc/bypassing-the-serialization-mechanism.md)  
  
##  <a name="_core_the_document.92.s_role_in_serialization"></a> Die Rolle des Dokuments in der Serialisierung  
 Das Framework reagiert automatisch auf das Menü Datei, die geöffnet werden, speichern und speichern als Befehle, indem die `Serialize`\-Memberfunktion des Dokuments aufgerufen wird, wenn es implementiert wird.  Ein `ID_FILE_OPEN` Befehl beispielsweise ruft eine Handlerfunktion im Anwendungsobjekt auf.  Während dieses Prozesses werden der Benutzer und auf das Dialogfeld Datei öffnen und Framework ruft den Dateinamen, den der Benutzer auswählt.  Das Framework erstellt ein `CArchive`\-Objektsetup zum Laden von Daten in das Dokument und führt das Archiv in `Serialize`.  Das Framework hat bereits die Datei geöffnet.  Der Code in `Serialize`\-Memberfunktion des Dokuments liest die Daten in das Archiv durch und ggf. rekonstruiert Datenobjekte.  Weitere Informationen zur Serialisierung, finden Sie im Artikel [Serialisierung](../mfc/serialization-in-mfc.md).  
  
##  <a name="_core_the_data.92.s_role_in_serialization"></a> Die Rolle der Daten in der Serialisierung  
 Im Allgemeinen sollten Klassentypdaten in der Lage sein, sich zu serialisieren.  Das bedeutet, dass, wenn Sie ein Objekt in einem Archiv übergeben, sollte das Objekt wie das Archiv und können, der aus dem Archiv lesen schreibt.  MFC unterstützt serialisierbar Klassen auf diese Weise ausführen.  Wenn Sie eine Klasse entwerfen, um einen Datentyp definieren und beabsichtigen, Daten dieses Typs zu serialisieren, entwerfen Sie für die Serialisierung.  
  
## Siehe auch  
 [Verwenden von Dokumenten](../mfc/using-documents.md)
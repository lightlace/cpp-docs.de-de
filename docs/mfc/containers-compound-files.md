---
title: "Container: Verbunddateien"
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
  - "Zugriffsmodi für Dateien [C++]"
  - "Verbunddokumente"
  - "Verbunddateien"
  - "Container [C++], Verbunddateien"
  - "Dokumente [C++], Verbund"
  - "Dokumente [C++], OLE"
  - "Dateien [C++], Verbund"
  - "OLE-Container, Verbunddateien"
  - "OLE-Dokumente, Verbunddateien"
  - "Leistung [C++], Verbunddateien"
  - "Standardisierte Dateistruktur (Verbunddateien)"
ms.assetid: 8b83cb3e-76c8-4bbe-ba16-737092b36f49
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Container: Verbunddateien
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In diesem Artikel werden die Komponenten und Implementierung von Verbunddateien sowie Vorteile und Nachteile der Verwendung von Verbunddateien in den OLE\-Anwendungen.  
  
 Verbunddateien sind ein wesentlicher Bestandteil OLE.  Sie werden verwendet, um Datenübertragungs\- und OLE\-Dokumentspeicher zu erleichtern.  Verbunddateien sind eine Implementierung des aktiven strukturierten Speichermodells.  Die konsistente Schnittstellen sind diese Stützserialisierung zu einem Speicher, einen Stream oder ein Dateiobjekt.  Verbunddateien werden in der Microsoft Foundation Class\-Bibliothek durch Klassen `COleStreamFile` und `COleDocument` unterstützt.  
  
> [!NOTE]
>  Verwenden einer Verbunddatei bedeutet nicht, dass die Informationen von einem OLE\-Dokument oder einem Verbunddokument stammen.  Verbunddateien sind nur eine der Methoden, Verbunddokumente, OLE\-Dokumente und andere Daten zu speichern.  
  
##  <a name="_core_components_of_a_compound_file"></a> Komponenten einer Verbunddatei  
 Die OLE\-Implementierung von Verbunddateien verwendet drei Objekttypen: Streamobjekte, Speicherobjekte und `ILockBytes`\-Objekte.  Diese Objekte sind zu den Komponenten eines Standarddateisystems folgendermaßen aus:  
  
-   Streamobjekte, wie Dateien, Daten aus anderen Typen.  
  
-   Speicherobjekte, wie Verzeichnisse, können andere Speicher und Streamobjekte enthalten.  
  
-   **LockBytes**\-Objekte stellen die Schnittstelle zwischen mit dessen und der physischen Hardware dar.  Bestimmen Sie, wie die Bytes zu tatsächlichen, worauf Speichergerät **LockBytes** das Objekt zugreift, z eine Festplatte oder ein Bereich des globalen Speicher geschrieben werden.  Weitere Informationen zu **LockBytes** und die Objekte `ILockBytes`\-Schnittstelle, finden Sie die *OLE\-Programmierreferenz*.  
  
##  <a name="_core_advantages_and_disadvantages_of_compound_files"></a> Vorteile und Nachteile von Verbunddateien  
 Verbunddateien bieten der Vorteile, die mit früheren Methoden der Aktenspeicherung nicht verfügbar sind.  Dazu zählen:  
  
-   Inkrementelles Dateizugreifen.  
  
-   Dateizugriffszugriffsarten.  
  
-   Standardisierung der Dateistruktur.  
  
 Mögliche Nachteile von Verbunddateien \- groß und Leistungsprobleme in Bezug auf Speicherung auf Disketten \- sollten beim Entscheiden berücksichtigt werden, ob sie in der Anwendung verwendet.  
  
###  <a name="_core_incremental_access_to_files"></a> Inkrementeller Dateizugriff  
 Inkrementeller Dateizugriff ist ein automatischer Vorteil von Verbunddateien.  Da eine Verbunddatei als "Dateisystem innerhalb einer Datei angezeigt werden kann," können auf einzelne Objekttypen, als Stream oder gespeichert, ohne dass erforderlich zugegriffen werden, die die vollständige Datei zu laden.  Dies kann die Zeit deutlich verringern, eine Anwendung auf die neuen Objekte für die Bearbeitung durch den Benutzer zugreifen muss.  Im inkrementellen Aktualisieren, auf dem Konzept, ähnliche bietet Vorteile.  Anstatt, die gesamte Datei einfach zu speichern, damit die Änderungen, die an ein Objekt zu speichern vorgenommen werden, wird nur das Stream\- oder OLE Speicherobjekt, das vom Benutzer bearbeitet wird.  
  
###  <a name="_core_file_access_modes"></a> Dateizugriffs\-Zugriffsarten  
 abhängen, zu bestimmen, ob sich Änderungen an den Objekten in einer Verbunddatei Datenträger übergeben werden, ist ein weiterer Vorteil von Verbunddateien.  Der Modus, in dem auf Dateien zugreifen, entweder abgewickelt, oder bestimmt verweisen, wenn Änderungen erhält.  
  
-   Transaktiver Modus verwendet einen Zweiphasencommitvorgang, um Änderungen an den Objekten in einer Verbunddatei vorzunehmen, und es werden die alten und neuen verfügbaren Kopien des Dokuments, bis der Benutzer entweder zu, die Änderungen zu speichern beschließt oder rückgängig zu machen.  
  
-   Direktbetrieb enthält Änderungen am Dokument, während sie ausgeführt werden, ohne die Möglichkeit, diese später rückgängig zu machen.  
  
 Weitere Informationen über Zugriffsmodi, finden Sie die *OLE\-Programmierreferenz*.  
  
###  <a name="_core_standardization"></a> Standardisierung  
 Die Struktur standardisierte von Verbunddateien können verschiedene OLE\-Anwendungen, Verbunddateien die durchzublättern, die von der OLE\-Anwendung ohne Kenntnis der Anwendung erstellt werden, die eigentlich die Datei erstellt.  
  
###  <a name="_core_size_and_performance_considerations"></a> Größe und Überlegungen zur Leistung  
 Aufgrund der Komplexität der Verbunddateispeicherstruktur und die Fähigkeit, Daten, erfordern tendenziell Dateien mit diesem Stil inkrementell zu speichern als andere, Dateien mithilfe von unstrukturierten oder "Flatfile" Speicher größer ist.  Wenn die Anwendung häufig Dateien geladen und gespeichert werden, mithilfe von Verbunddateien kann die Dateigröße führen, dass zu erhöhen viel schneller als noncompound Dateien.  Da Verbunddateien groß werden können, speichern die Zugriffsgeschwindigkeit für Dateien auf und hat von Disketten kann, mit dem Ergebnis der langsameren Zugriff auf Dateien auch beeinflusst werden.  
  
 Andere Thema, das die Leistung auswirkt, ist Verbunddateifragmentierung.  Die Größe einer Verbunddatei wird vom Unterschied zwischen dem ersten und den letzten Datenträgerbereichen verwendet die Datei bestimmt.  Eine fragmentierte Datei kann viele Bereiche des freien Speicherplatzes, enthalten, die keine Daten enthalten, wird aber gezählt, wenn die Größe abgeleitet.  Während der Lebensdauer einer Verbunddatei, werden diese Bereiche über die das Einfügen oder Löschen von dessen erstellt.  
  
##  <a name="_core_using_compound_files_format_for_your_data"></a> Verwenden des Verbunddatei\-Formats für die Daten  
 Nachdem eine Anwendung erfolgreich erstellen, die eine Dokumentklasse hat, von `COleDocument` abgeleiteten, sicherstellen, dass das Hauptdokumentkonstruktor `EnableCompoundFile` aufruft.  Wenn der OLE\-Containeranwendungen Anwendungs\-Assistent erstellt, wird dieser Aufruf für Sie eingefügt.  
  
 In der *OLE\-Programmierreferenz* finden Sie unter [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034), [IStorage](http://msdn.microsoft.com/library/windows/desktop/aa380015) und [ILockBytes](http://msdn.microsoft.com/library/windows/desktop/aa379238).  
  
## Siehe auch  
 [Container](../mfc/containers.md)   
 [Container: Probleme mit der Benutzeroberfläche](../mfc/containers-user-interface-issues.md)   
 [COleStreamFile Class](../mfc/reference/colestreamfile-class.md)   
 [COleDocument Class](../mfc/reference/coledocument-class.md)
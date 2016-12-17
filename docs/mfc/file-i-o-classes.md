---
title: "Datei-E/A-Klassen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vc.classes.file"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Datenträger-Dateiklassen"
  - "Datei-E/A-Klassen [C++]"
  - "E/A [C++], MFC-Klassen"
  - "E/A [MFC], Klassen"
  - "Arbeitsspeicher-Dateiklassen"
  - "OLE-Streams"
  - "Socketklassen"
  - "stdio-Klassen"
  - "stream-Klassen"
  - "übersetze stream-Klassen"
ms.assetid: 92821c3f-d9e1-47f6-98c9-3b632d86e811
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Datei-E/A-Klassen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Diese Klassen bieten eine Schnittstelle mit den herkömmlichen Datenträgerdateien, Dateien in den speicherresidenten, zu aktiven Streams und den Windows Sockets bereit.  Alle Klassen, die von `CFile` abgeleitet werden, können mit einem `CArchive`\-Objekt verwendet werden, um die Serialisierung auszuführen.  
  
 Verwenden Sie die folgenden Klassen, insbesondere `CArchive` und `CFile`, wenn Sie Ihr eigenes Eingabe\/Ausgabe\-Verarbeiten schreiben.  Normalerweise müssen Sie keinen, um aus diesen Klassen abzuleiten.  Wenn Sie das Anwendungsframework verwenden, behandeln die Standardimplementierungen **Öffnen** und die Befehle im Menü **DateiSpeichern** Datei\-E\/A \(mithilfe der `CArchive`\- Klasse\), solange Sie `Serialize`\-Funktion des Dokuments überschreiben, um bereitzustellen Informationen darüber, wie ein Dokument den Inhalt serialisiert.  Weitere Informationen über die Dateiklassen und zum, finden Sie im Artikel [Dateien in MFC](../mfc/files-in-mfc.md) und den Artikel [Serialisierung](../mfc/serialization-in-mfc.md).  
  
 [Die C\-Datei](../mfc/reference/cfile-class.md)  
 Stellt eine Dateischnittstelle in binäre Datenträgerdateien bereit.  
  
 [CStdioFile](../mfc/reference/cstdiofile-class.md)  
 Stellt eine `CFile`\-Schnittstelle zu Streamdatenträgerdateien gepufferten, normalerweise im Textmodus bereit.  
  
 [CMemFile](../mfc/reference/cmemfile-class.md)  
 Stellt eine `CFile`\-Schnittstelle an Dateien im Arbeitsspeicher bereit.  
  
 [CSharedFile](../mfc/reference/csharedfile-class.md)  
 Stellt eine `CFile`\-Schnittstelle auf freigegebene Dateien im Arbeitsspeicher bereit.  
  
 [COleStreamFile](../mfc/reference/colestreamfile-class.md)  
 Verwendet die Schnittstelle COM\- `IStream`, um `CFile` Zugriff an Verbunddateien zu ermöglichen.  
  
 [CSocketFile](../mfc/reference/csocketfile-class.md)  
 Stellt eine `CFile`\-Schnittstelle für einen Socket Windows bereit.  
  
## Verwandte Klassen  
 [CArchive](../mfc/reference/carchive-class.md)  
 Arbeitet mit einem `CFile`\-Objekt zum Werkzeugpersistenten speicher für Objekte durch Serialisierung zusammen \(siehe [CObject::Serialize](../Topic/CObject::Serialize.md)\).  
  
 [CArchiveException](../mfc/reference/carchiveexception-class.md)  
 Eine Archivausnahme.  
  
 [CFileException](../mfc/reference/cfileexception-class.md)  
 Eine dateiorientierten Ausnahme.  
  
 [CFileDialog](../mfc/reference/cfiledialog-class.md)  
 Stellt ein Standarddialogfeld zum Öffnen oder Speichern einer Datei.  
  
 [CRecentFileList](../mfc/reference/crecentfilelist-class.md)  
 Führt die zuletzt verwendete \(MRU\)\- Dateiliste.  
  
## Siehe auch  
 [Klassenübersicht](../mfc/class-library-overview.md)
---
title: "Dateien in MFC"
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
  - "Binärer Zugriff"
  - "Binärer Zugriff, Binäre Dateivorgänge in MFC"
  - "Datei-E/A-Klassen [C++]"
  - "Dateien [C++], Bearbeiten"
  - "Dateien [C++], MFC"
  - "Dateien [C++], Serialisierung"
  - "E/A [C++], MFC-Klassen"
  - "E/A [MFC]"
  - "MFC [C++], Dateivorgänge"
  - "Dauerhaftigkeit [C++]"
  - "Serialisierung [C++], MFC-Dateien"
ms.assetid: ae25e2c5-2859-4679-ab97-438824e93ce1
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Dateien in MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In der Microsoft Foundation Class\-Bibliothek " \(MFC\-Bibliothek\), behandelt Klasse [Die C\-Datei](../mfc/reference/cfile-class.md) normale Datei\-E\/A\-Vorgänge.  Diese Gruppe von Artikeln erläutert, wie Daten an diesen Dateien wird geöffnet und enthält Dateien sowie gelesen und geschrieben wird.  Sie werden außerdem Dateistatusvorgänge.  Eine Beschreibung dazu, wie der objektbasierten Serialisierungsfunktionen von MFC als alternative Methode aus das Lesen und Schreiben von Daten in Dateien, finden Sie im Artikel [Serialisierung](../mfc/serialization-in-mfc.md).  
  
> [!NOTE]
>  Wenn Sie Objekte MFC **CDocument** verwenden, übernimmt das Framework viele der Serialisierungsarbeit für Sie.  Insbesondere erstellt das Framework und verwendet das `CFile`\-Objekt.  Sie müssen Code in der Überschreibung der `Serialize`\-Memberfunktion der Klasse nur **CDocument** schreiben.  
  
 Die `CFile`\-Klasse stellt eine Schnittstelle für allgemeine Binärdateivorgänge bereit.  Die `CStdioFile` und `CMemFile`\-Klassen, die von `CFile` abgeleitet werden und die `CSharedFile`\-Klasse, die von `CMemFile` abgeleitet ist, stellen mehrere spezialisierte Dateidienste.  
  
 Weitere Informationen über Alternativen zur MFC\-Dateibehandlung, finden Sie unter [Datei\-Behandlung](../c-runtime-library/file-handling.md) in der Laufzeitbibliotheksreferenz.  
  
 Informationen zum `CFile` abgeleitete Klassen, finden Sie unter [MFC\-Hierarchiendiagramm](../mfc/hierarchy-chart.md).  
  
## Was möchten Sie tun?  
 *Verwenden Sie C\-Datei*  
  
-   [Öffnen Sie eine Datei mit C\-Datei](../mfc/opening-files.md)  
  
-   [Lesen und Schreiben Sie eine Datei mit C\-Datei](../mfc/reading-and-writing-files.md)  
  
-   [Schließen Sie eine Datei mit C\-Datei](../mfc/closing-files.md)  
  
-   [Greifen Sie auf Dateistatus mit C\-Datei zu](../mfc/accessing-file-status.md)  
  
 *Verwenden Sie MFC\-Serialisierung \(Objekt\-Persistenz\)*  
  
-   [Erstellen Sie eine serialisierbare Klasse](../mfc/serialization-making-a-serializable-class.md)  
  
-   [Serialisieren Sie ein Objekt über ein CArchive\-Objekt](../mfc/serialization-serializing-an-object.md)  
  
-   [Erstellen Sie ein CArchive\-Objekt](../mfc/two-ways-to-create-a-carchive-object.md)  
  
-   [Verwenden Sie CArchive \<\< und \>\>\-Operatoren](../mfc/using-the-carchive-output-and-input-operators.md)  
  
-   [Speichern und Laden Sie CObjects und von CObject abgeleiteten Objekte zu einem Archiv](../mfc/storing-and-loading-cobjects-via-an-archive.md)  
  
## Siehe auch  
 [Konzepte](../mfc/mfc-concepts.md)   
 [Allgemeine MFC\-Themen](../mfc/general-mfc-topics.md)   
 [CArchive Class](../mfc/reference/carchive-class.md)   
 [CObject Class](../mfc/reference/cobject-class.md)   
 [Wie behebe ich: Verwenden Sie die C\-Datei Klasse?](http://go.microsoft.com/fwlink/?LinkId=128046)
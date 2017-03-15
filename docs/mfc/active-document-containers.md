---
title: "Active Document-Container | Microsoft Docs"
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
  - "Active Document-Container [C++]"
  - "Aktive Dokumente [C++], Container"
  - "Container [C++], aktives Dokument"
  - "MFC-COM [C++], Active Document-Einschluss"
ms.assetid: ba20183a-8b4c-440f-9031-e5fcc41d391b
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Active Document-Container
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein Active Document\-Container, wie Microsoft Office\-Binder oder Internet Explorer, ermöglicht die Arbeit mit mehreren Dokumenten von verschiedenen Anwendungstypen innerhalb einzelnen Frames \(, anstatt Sie erzwingen, um mehrere Frames der Anwendung für jeden Dokumenttyp zu erstellen und zu verwenden\).  
  
 MFC bietet vollständige Unterstützung für Active Document\-Container in der Klasse `COleDocObjectItem`.  Sie können den MFC\-Anwendungs\-Assistenten verwenden, um einen Active Document\-Container erstellen, indem Sie das Kontrollkästchen **Active Document\-Container** auf der Seite **Verbunddokumente** des MFC\-Anwendungs\-Assistenten auswählen.  Weitere Informationen finden Sie unter [Erstellen einer Active Document\-Container\-Anwendung](../mfc/creating-an-active-document-container-application.md).  
  
 Weitere Informationen über Active Document\-Container, finden Sie unter:  
  
-   [Container\-Anforderungen](#container_requirements)  
  
-   [Dokument\-Site\-Objekte](#document_site_objects)  
  
-   [Ansichts\-Site\-Objekte](#view_site_objects)  
  
-   [Rahmenobjekt](#frame_object)  
  
-   [Menü Hilfe\-Zusammenführen](../mfc/help-menu-merging.md)  
  
-   [Programmgesteuerter Drucken](../mfc/programmatic-printing.md)  
  
-   [Befehls\-Ziele](../mfc/message-handling-and-command-targets.md)  
  
##  <a name="container_requirements"></a> Container\-Anforderungen  
 Active Document\-Unterstützung auf einem Active Document\-Container bedeutet mehr als nur Schnittstellenimplementierungen: sie benötigt auch Kenntnisse der Schnittstellen eines enthaltenden Objekts.  Dasselbe gilt auf aktive Dokumenterweiterungen zu, in denen der Container auch können muss die Erweiterungsschnittstellen auf den aktiven Dokumenten selbst verwenden.  
  
 Ein Active Document\-Container, der Active Documents integriert, muss:  
  
-   Stellen Sie zum Behandlungsobjektspeicher durch die **IPersistStorage** \-Schnittstelle möglich, d. h muss sie eine `IStorage`\-Instanz zu allen aktiven Dokumenten bereitstellen.  
  
-   Unterstützen Sie die grundlegenden Einbettungsfunktionen von OLE\-Dokumenten, "Site" erfordernd Objekte \(eine pro Dokument oder das Einbetten\) implementiert dieses **IOleClientSite**  und **IAdviseSink** ein.  
  
-   Stützdirekte aktivierung von eingebetteten Objekten oder von aktiven Dokumenten.  Die Siteobjekte des Containers müssen `IOleInPlaceSite` implementieren und das Frameobjekt des Containers muss **IOleInPlaceFrame** bereitstellen.  
  
-   Unterstützen Sie die aktuellen Erweiterungen der Dokumente, indem Sie `IOleDocumentSite` implementieren, um den Mechanismus bereitstellen, sodass der Container im Dokument ist.  Optional kann der Container die aktiven Dokumentoberflächen `IOleCommandTarget` und `IContinueCallback` implementieren, um einfache Befehle wie Drucken oder Speichern einzubinden.  
  
 Das Frameobjekt, die und Ansichtsobjekte das Containerobjekt **IOleCommandTarget**  können optional implementiert, um den Dispatch von bestimmten Befehlen zu unterstützen, wie in [Befehls\-Ziele](../mfc/message-handling-and-command-targets.md) erläutert.  Containerobjekte Ansicht und können `IPrint` und `IContinueCallback` auch optional implementiert, um programmgesteuertes Drucken zu unterstützen, wie in [Programmgesteuerter Drucken](../mfc/programmatic-printing.md) erläutert.  
  
 Die folgende Abbildung zeigt die grundlegende Beziehungen zwischen einem Container und ihren Komponenten an \(links\) und das aktive Dokument und die Ansichten angezeigt \(am rechts\).  Das aktive Dokument verwaltet Speicher und Daten, und die Ansicht zeigt oder optional Drucken an, der Daten.  Schnittstellen in fett sind die, für die aktive Dokumentteilnahme erforderlich sind; jenes Fett und kursive sind optional.  Alle anderen Schnittstellen sind erforderlich.  
  
 ![Schnittstellen des Containers für das aktive Dokument](../mfc/media/vc37gj1.png "vc37gj1")  
  
 Ein Dokument, das nur einer einzelnen Ansicht unterstützt, kann die Ansichts\- und Dokumentkomponenten \(das heißt, die entsprechenden Schnittstellen\) in einer einzelnen konkreten Klasse implementieren.  Außerdem kann eine Containersite, die nur eine Ansicht gleichzeitig unterstützt, die Dokumentsite und die Ansichtssite in einer einzelnen konkreten Bonität kombinieren.  Das Frameobjekt des Containers verbleiben muss jedoch anders, und die Dokumentkomponente des Containers ist lediglich hier enthalten, um ein Vollbild der Architektur zu verleihen; nicht durch die Active Document\-Kapselungsarchitektur beeinflusst.  
  
##  <a name="document_site_objects"></a> Dokument\-Site\-Objekte  
 In der Active Document\-Kapselungsarchitektur ist eine Dokumentsite genauso, die ein Clientsiteobjekt in OLE\-Dokumenten mit der Einführung der Schnittstelle: `IOleDocument`  
  
 `interface IOleDocumentSite : IUnknown`  
  
 `{`  
  
 `HRESULT ActivateMe(IOleDocumentView *pViewToActivate);`  
  
 `}`  
  
 Die Dokumentsite Konzept ist der Container für eine oder mehrere "Ansichtssite" Objekte.  Jedes Ansichtssiteobjekt wird mit einzelnen Ansichtsobjekte des Dokuments verknüpft, das durch die Dokumentsite verwaltet wird.  Wenn der Container nur einer einzelnen Ansicht pro Dokumentsite unterstützt, kann er die Dokumentsite und die Ansichtssite mit einer einzelnen konkreten Klasse implementieren.  
  
##  <a name="view_site_objects"></a> Ansichts\-Site\-Objekte  
 Ansichts\-Siteobjekt eines Containers verwaltet den Bilderpanel für eine bestimmte Ansicht eines Dokuments.  Zusätzlich zur Unterstützung der Standard\- `IOleInPlaceSite` implementiert eine Schnittstelle, Ansichtssite auch allgemein `IContinueCallback` für programmgesteuerte Drucksteuerelement. \(Beachten Sie, dass das Ansichtsobjekt niemals für `IContinueCallback` ausführt, sodass sie können für jedes Objekt tatsächlich implementiert werden, das die Container wünscht.\)  
  
 Ein Container, der mehrere Ansichten unterstützt, muss sein, mehrere Ansichtssiteobjekte innerhalb der Dokumentsite zu erstellen.  Dadurch verfügen jede Ansicht mit separaten Aktivieren und Ausschalten\-Dienstleistungen wie angegeben durch `IOleInPlaceSite`.  
  
##  <a name="frame_object"></a> Rahmenobjekt  
 Das Frameobjekt des Containers ist in den meisten Fällen die gleichen Frame, der für direkte Aktivierung in OLE\-Dokumenten d. h die verwendet wird, die Symbolleistenaushandlung Menü\- und behandelt.  Ein View\-Objekt hat Zugriff zu diesem Frameobjekt von **IOleInPlaceSite::GetWindowContext**, das auch den Zugriff auf das Containerobjekt bietet, das das Containerdokument darstellt \(das BereichEbenensymbolleistenaushandlung und betroffenen Objektenumeration behandeln kann\).  
  
 Ein Active Document\-Container kann die Frames erweitern, indem `IOleCommandTarget` hinzufügt.  Dadurch können sie, um Befehle zu empfangen, die aus der aktuellen Benutzeroberfläche des Dokuments auf stammen, dass diese Schnittstelle einem Container zulassen kann, um dieselben Befehle zu senden \(wie **Datei\/Neu**, **Öffnen**, **Speichern unter**, **Drucken**; **Kopie bearbeiten**, **Einfügen**, **Rückgängig** usw.\) auf einen aktiven Dokument.  Weitere Informationen finden Sie unter [Befehls\-Ziele](../mfc/message-handling-and-command-targets.md).  
  
## Siehe auch  
 [Active Document\-Container](../mfc/active-document-containment.md)
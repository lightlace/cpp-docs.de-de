---
title: "Alternativen zur Dokument-/Ansichtarchitektur | Microsoft Docs"
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
  - "CDocument-Klasse, Erforderlicher Speicherplatz"
  - "Dokumente, Anwendungen ohne"
  - "Ansichten, Anwendungen ohne"
ms.assetid: 2c22f352-a137-45ce-9971-c142173496fb
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Alternativen zur Dokument-/Ansichtarchitektur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC\-Anwendungen verwenden normalerweise die Dokument\-\/Ansichtarchitektur, um Informationen, Dateiformate und die visuelle Darstellung von Daten für Benutzer zu verwalten.  Für die Mehrzahl Desktopanwendungen, ist die Dokument\-\/Ansichtarchitektur eine entsprechende und effiziente Anwendungsarchitektur.  Diese Architektur trennt Daten von der Anzeige und den meisten Fällen vereinfacht die Anwendung und reduziert redundanten Code.  
  
 Es ist die Dokument\-\/Ansichtarchitektur nicht für mehrere Situationen geeignet.  Betrachten Sie diese Beispiele:  
  
-   Wenn Sie eine Anwendung portieren, die in C für Windows geschrieben wird, sollten Sie den Port ausführen, bevor Sie Dokument\/direkte zu der Anwendung hinzufügen.  
  
-   Wenn Sie ein einfaches Hilfsprogramm schreiben, kann es sein, dass Sie ohne Dokument\-\/Ansichtarchitektur verwenden können.  
  
-   Wenn der ursprüngliche Code bereits Datenverwaltung kombiniert mit zur Eingabe und Anzeige von Daten, den Code zum Dokument\/Ansichts\-Modell ist zu bewegen nicht wert den Aufwand, da die beiden getrennt ist.  Sie möchten, lieber den Code zu können, z ist.  
  
 Um eine Anwendung zu erstellen die keine Dokument\-\/Ansichtarchitektur verwendet, deaktivieren Sie das Kontrollkästchen **Unterstützung für die Dokument\-\/Ansichtarchitektur** im Schritt 1 des MFC\-Anwendungs\-Assistenten.  Ausführliche Informationen finden Sie unter [MFC\-Anwendungs\-Assistent](../mfc/reference/mfc-application-wizard.md).  
  
> [!NOTE]
>  Die auf Dialogfeldern basierenden Anwendungen, die vom MFC\-Anwendungs\-Assistenten erzeugten, verwenden keine Dokument\-\/Ansichtarchitektur, sodass das Kontrollkästchen **Unterstützung für die Dokument\-\/Ansichtarchitektur** deaktiviert, wenn Sie den Dialogfeld\-Anwendungstyp auswählen.  
  
 Die Visual C\+\+\-Assistenten sowie Quelle und die Dialog\-Editoren, mit der generierten Anwendung, wie sie mit jeder anderen vom Assistenten erstellten Anwendung wurden.  Die Anwendung kann Symbolleisten, Bildlaufleisten und eine Statusleiste unterstützen und verfügt über ein Feld **Info**.  die Anwendung registriert keine Dokumentvorlagen, und enthält keine Dokumentklasse.  
  
 Beachten Sie dass die generierte Anwendung verfügt eine Ansichtsklasse, **CChildView**, wird von `CWnd` abgeleitet.  MFC erstellt und positioniert eine Instanz der in der Ansichtsklasse Rahmenfenster, die von der Anwendung erstellt werden.  MFC erzwingt noch mithilfe eines Ansichtsfensters, da es die Positionierung und Verwalten von Inhalt der Anwendung vereinfacht.  Sie können für den `OnPaint`\-Member der Klasse hinzufügen.  Der Code sollte grundsätzlich der Ansicht anstelle den Frames hinzufügen.  
  
 Da die Dokument\-\/Ansichtarchitektur von MFC ist verantwortlich für das Implementieren viele von den grundlegenden Features einer Anwendung, seine Abwesenheit im Projekt bedeutet bereitgestellte, dass Sie für die Implementierung vieler wichtigen Funktionen der Anwendung zuständige:  
  
-   Wie von den MFC\-Anwendungs\-Assistenten, enthält das Menü für die Anwendung nur `New` und `Exit` Befehle im Menü **Datei**. \(Der Befehl `New` wird nur für MDI\-Anwendungen, nicht ohne SDI\-Anwendungen Dokument\/direkte unterstützt.\) Die generierte Menüressource unterstützt keine \(zuletzt verwendete\) Liste MRU.  
  
-   Sie müssen Handlerfunktionen und Implementierungen für alle Befehle, die die Anwendung unterstützt, einschließlich **Öffnen** und **Speichern** im Menü **Datei** hinzugefügt.  MFC enthält normalerweise Code, um diese Features zu unterstützen, aber diese Unterstützung ist eng zur Dokument\-\/Ansichtarchitektur gebunden.  
  
-   Die Symbolleiste für die Anwendung, wenn Sie ein angeforderten, ist minimal.  
  
 Es wird dringend empfohlen, dass Sie den MFC\-Anwendungs\-Assistenten verwenden, um ohne die Dokument\-\/Ansichtarchitektur zu erstellen, da der Assistent eine richtige MFC\-Architektur gewährleistet.  Wenn Sie den Assistenten, zu verwenden, vermeiden müssen hier sind mehrere Ansätze zum Umgehen der Dokument\-\/Ansichtarchitektur im Code:  
  
-   Behandeln Sie das Dokument als nicht verwendeter Anhang und implementieren Sie den Datenverwaltungscode in der Ansichtsklasse, wie oben vorgeschlagen.  Mehraufwand zum Dokument ist relativ gering.  Ein einzelnes [CDocument](../mfc/reference/cdocument-class.md)\-Objekt verursacht eine kleine Menge an Mehraufwand an, plus kleinen Aufwand von **CDocument** Basisklassen, \- [CCmdTarget](../mfc/reference/ccmdtarget-class.md) \- und [CObject](../mfc/reference/cobject-class.md).  Beide der letzten Klassen sind klein.  
  
     Deklariert in **CDocument**:  
  
    -   Zwei `CString`\-Objekte.  
  
    -   Drei **BOOL**s.  
  
    -   Ein `CDocTemplate` Zeiger.  
  
    -   Ein `CPtrList`\-Objekt, das eine Liste der Ansichten des Dokuments enthält.  
  
     Zusätzlich benötigt das Dokument der Zeitspanne, das Dokumentobjekt, seine Ansichtsobjekte, ein Rahmenfenster und ein Dokumentvorlagenobjekt zu erstellen.  
  
-   Behandeln Sie das Dokument und Ansicht als nicht verwendete Anhänge.  Geben Sie den Datenverwaltungs\- und Zeichnungscode im Rahmenfenster nicht die Ansicht ein.  Dieser Ansatz ist näher am Sprache C Programmiermodell.  
  
-   Überschreiben Sie die Teile des MFC\-Frameworks, die das Dokument und die Ansicht, um sie ggf. erstellen zu vermeiden.  Der Dokumenterstellungsprozess beginnt mit einem Aufruf von `CWinApp::AddDocTemplate`.  Entfernen Sie den Aufruf von `InitInstance`\-Memberfunktion der Anwendungsklasse und stellen Sie stattdessen ein Rahmenfenster in `InitInstance` selbst erstellt.  Geben Sie den Datenverwaltungscode in der Rahmenfensterklasse ein.  Im Dokument\/Ansichts\-Erstellungsprozess wird in [Dokument\/Ansichts\-Erstellung](../mfc/document-view-creation.md) veranschaulicht.  Dies ist mehr Arbeit und erfordert ein tiefer Verständnis des Frameworks, jedoch gibt Sie vollständig von Dokument\/Ansichts\-Mehraufwand frei.  
  
 Der Artikel [MFC: Verwenden von Datenbankklassen ohne Dokumente und Ansichten](../data/mfc-using-database-classes-without-documents-and-views.md) erläutert konkretere Beispiele von Dokument\/Ansichts\-Alternativen im Kontext von Datenbankanwendungen.  
  
## Siehe auch  
 [Dokument\-\/Ansichtsarchitektur](../mfc/document-view-architecture.md)
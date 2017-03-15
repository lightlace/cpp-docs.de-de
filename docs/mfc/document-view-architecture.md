---
title: "Dokument-/Ansichtsarchitektur | Microsoft Docs"
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
  - "CDocument-Klasse"
  - "CView-Klasse, view-Architektur"
  - "Document-Objekte"
  - "Document-Objekte, Dokument-/Ansichtsarchitektur"
  - "Document-Objekte, MFC-Dokument/Ansichtsmodel"
  - "Dokumente, MFC-Dokument/Ansichtsmodel"
  - "MFC, Dokumente"
  - "MFC, Ansichten"
  - "Ansichten, MFC-Dokument/Ansichtsmodel"
ms.assetid: 6127768a-553f-462a-b01b-a5ee6068c81e
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Dokument-/Ansichtsarchitektur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Standardmäßig erstellt der MFC\-Anwendungs\-Assistent ein Anwendungsskelett mit einer Dokumentklasse und einer Ansichtsklasse.  MFC trennt Datenverwaltung in diese beiden Klassen.  Die \- Archive die Daten und verwaltet das Drucken der Daten und die Koordinaten, die mehrere Ansichten der Daten aktualisieren.  Die Ansicht zeigt die Daten an und verwaltet Benutzerinteraktion damit, einschließlich Auswahl und Bearbeitung.  
  
 In diesem Modell wird ein MFC\-Dokumentobjekt und schreibt Daten permanenten Speicher.  Das Dokument enthält auch eine Schnittstelle an Daten bereit, auf dem es sich befindet \(wie in einer Datenbank\).  Ein separates Ansichtsobjekt verwaltet Datenanzeige, vom Rendern der Daten in einem Fenster der Benutzerauswahl und der Bearbeitung von Daten.  Die Ansicht erhält Daten vom Dokument und übermittelt zurück zum Dokument alle Datenänderungen mit.  
  
 Während Sie die Ansichts\-Trennung Dokument\/problemlos überschreiben oder ignorieren können, gibt es zwingende Gründe, diesem Modell in den meisten Fällen befolgen.  Eines der besten ist, wenn mehrere Ansichten des gleichen Dokuments, wie in einem Arbeitsblatt und eine Diagrammansicht benötigen.  Das Dokument\/Ansichts\-Modell können ein separates Ansichtsobjekt jede Ansicht der Daten darstellen, während Codeallen Common \(wie ein Berechnungsmodul\) kann im Dokument befinden anzeigt.  Das Dokument verfügt auch auf der Aufgabe zur Aktualisierung aller Ansichten, beim Ändern der Daten.  
  
 Die MFC\-Dokument\-\/Ansichtsarchitektur ist es einfach, mehrere Ansichten, mehrere Dokumenttypen, Splitterfenster und andere wichtige Benutzeroberflächefunktionen zu unterstützen.  
  
 Die Teile des sichtbarsten MFC\-Frameworks dem Benutzer und Sie, der Programmierer, sind das Dokument und die Ansicht.  Die meiste Arbeit, wenn eine Anwendung mit dem Framework entwickelt, wechselt in das Schreiben des Dokuments und Ansichtsklassen ein.  Diese Artikelfamilie beschrieben werden:  
  
-   Die Zwecken der Dokumente und Ansichten und wie sie im Framework interagieren.  
  
-   Was Sie tun müssen, um sie zu implementieren.  
  
 eine der im Dokument\/Ansicht sind vier wesentliche Klassen:  
  
 Die [CDocument](../mfc/reference/cdocument-class.md) \(oder [COleDocument](../mfc/reference/coledocument-class.md)\) unterstützt die Objekte, die verwendet werden, um die Daten des Programms zu speichern oder Steuerung und stellt die Grundfunktionen für Programmierer\-definierte Dokumentklassen bereit.  Ein Dokument stellt die Einheit von Daten dar, die der Benutzer in der Regel mit geöffnetem Befehl im Menü Datei geöffnet und mit dem Befehl Speichern im Menü Datei speichert.  
  
 [CView](../mfc/reference/cview-class.md) \(oder eine der vielen abgeleiteten Klassen\) stellt die grundlegenden Funktionen für Programmierer\-definierte Ansichtsklassen bereit.  Eine Ansicht zu einem Dokument wird angefügt und wird ausgelöst als Mittler zwischen das Dokument und den Benutzer: die Ansicht rendert ein Bild des Dokuments auf dem Bildschirm und interpretiert Benutzereingaben als Operationen nach dem Dokument.  Die Ansicht rendert auch das Bild für Drucken und Druckvorschau.  
  
 [CFrameWnd](../mfc/reference/cframewnd-class.md) \(oder eine seiner Variationen\) unterstützt Objekte, das der Rahmen um eine oder mehrere Ansichten eines Dokuments zur Verfügung stellt.  
  
 [CDocTemplate](../mfc/reference/cdoctemplate-class.md) \(oder [CSingleDocTemplate](../mfc/reference/csingledoctemplate-class.md) oder [CMultiDocTemplate](../mfc/reference/cmultidoctemplate-class.md)\) unterstützt ein Objekt, das eine oder mehrere vorhandene Dokumente eines angegebenen Typs und das Erstellen des richtigen Dokuments, Ansicht und der Rahmenfensterobjekte für diesen Typ verwaltet.  
  
 Die folgende Abbildung zeigt die Beziehung zwischen einem Dokument und der Ansicht an.  
  
 ![Die Ansicht ist Teil des angezeigten Dokuments](../mfc/media/vc379n1.png "vc379N1")  
Dokument und Ansicht  
  
 Die Dokument\/Ansichts\-Implementierung in der Klassenbibliothek trennt die Daten selbst von der Anzeige und den Teilnehmerbetrieben auf den Daten.  Alle Änderungen an den Daten werden durch die Dokumentklasse verwaltet.  Die Ansicht ruft diese Schnittstelle auf, um auf die Daten zuzugreifen und zu aktualisieren.  
  
 Dokumente, Ansichten und die ihnen zugeordneten Rahmenfenster, die Ansichten gestalten, werden durch eine Normal\-Vorlage erstellt.  Die Normal\-Vorlage wird für das Erstellen und Verwalten aller Dokumente eines Dokumenttyp zuständig.  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Ein Hochformat der Dokument\-\/Ansichtarchitektur](../mfc/a-portrait-of-the-document-view-architecture.md)  
  
-   [Vorteile der Dokument\-\/Ansichtarchitektur](../mfc/advantages-of-the-document-view-architecture.md)  
  
-   [Dokument\- und Ansichtsklassen vom Anwendungs\-Assistenten erstellt wurde](../mfc/document-and-view-classes-created-by-the-mfc-application-wizard.md)  
  
-   [Alternativen zur Dokument\-\/Ansichtarchitektur](../mfc/alternatives-to-the-document-view-architecture.md)  
  
-   [Hinzufügen von mehreren Ansichten zu einem einzelnen Dokument](../mfc/adding-multiple-views-to-a-single-document.md)  
  
-   [Verwenden der Dokumente](../mfc/using-documents.md)  
  
-   [Mithilfe von Ansichten](../mfc/using-views.md)  
  
-   [Mehrere Dokumenttypen, Ansichten und Rahmenfenster](../mfc/multiple-document-types-views-and-frame-windows.md)  
  
-   [Dokumente und Ansichten initialisieren und Objects](../mfc/initializing-and-cleaning-up-documents-and-views.md)  
  
-   [Initialisieren Sie eigene Hinzufügungen, um zu dokumentieren Ansichtsklassen &](../mfc/creating-new-documents-windows-and-views.md)  
  
-   [Verwenden von Datenbankklassen mit Dokumenten und Ansichten](../data/mfc-using-database-classes-with-documents-and-views.md)  
  
-   [Verwenden von Datenbankklassen ohne Dokumente und Ansichten](../data/mfc-using-database-classes-without-documents-and-views.md)  
  
-   [Beispiele](../top/visual-cpp-samples.md)  
  
## Siehe auch  
 [Benutzeroberflächenelemente](../mfc/user-interface-elements-mfc.md)   
 [Windows](../mfc/windows.md)   
 [Rahmenfenster](../mfc/frame-windows.md)   
 [Dokumentvorlagen und der Erstellungsvorgang für Dokumente und Ansichten](../mfc/document-templates-and-the-document-view-creation-process.md)   
 [Erstellen von Dokument\/Ansicht](../mfc/document-view-creation.md)   
 [Erstellen neuer Dokumente, Fenster und Ansichten](../mfc/creating-new-documents-windows-and-views.md)
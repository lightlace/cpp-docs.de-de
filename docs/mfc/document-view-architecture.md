---
title: Dokument-/ Ansichtarchitektur | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- CView class [MFC], view architecture
- CDocument class [MFC]
- MFC, views
- views [MFC], MFC document/view model
- document objects [MFC]
- document objects [MFC], MFC document/view model
- MFC, documents
- documents [MFC], MFC document/view model
- document objects [MFC], document/view architecture
ms.assetid: 6127768a-553f-462a-b01b-a5ee6068c81e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 45c595b78b17ed00691533369ec4837345fcce03
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="documentview-architecture"></a>Dokument-/Ansichtsarchitektur
Die MFC-Anwendung-Assistent erstellt standardmäßig eine Skeleton Anwendung mit einer Dokumentklasse und View-Klasse. MFC trennt die datenverwaltung von in diese beiden Klassen. Das Dokument speichert die Daten und Drucken der Daten und koordiniert mehrere Sichten der Daten aktualisieren. Die Sicht werden die Daten angezeigt und verwaltet die Benutzerinteraktion mit der Anwendung, einschließlich Auswahl und bearbeiten.  
  
 In diesem Modell ein Objekt der MFC-Dokument liest und schreibt Daten in den persistenten Speicher. Das Dokument kann zudem eine Schnittstelle zu den Daten liefern, wo er sich befindet (z. B. in einer Datenbank). Ein separates Objekt verwaltet Darstellung der Daten, die vom Rendern der Daten in einem Fenster auf Benutzerauswahl und Bearbeitung der Daten. Die Ansicht anzeigen von Daten aus dem Dokument abgerufen und kommuniziert zurück an das Dokument alle datenänderungen.  
  
 Sie können leicht überschreiben oder ignorieren die Dokument-/Ansichtarchitektur Trennung, gibt es überzeugende Gründe für dieses Modell in den meisten Fällen befolgen. Eine der am besten geeignet ist, wenn Sie mehrere Ansichten des gleichen Dokuments, z. B. eine Tabelle und eine Diagrammsicht benötigen. Das Dokument/ansichtsmodel kann ein separates Ansichtsobjekt jede Ansicht der Daten, während Code, die allgemeine Darstellung auf alle Ansichten (z. B. ein Berechnungsmodul) im Dokument vorhanden sein können. Das Dokument nimmt auch der Task alle Sichten aktualisiert, bei jeder Datenänderung.  
  
 Die MFC-Dokument-/ Ansichtarchitektur erleichtert es, um mehrere Sichten, mehrere Dokumenttypen, Splitterfenster und andere wertvolle Benutzeroberflächen-Funktionen zu unterstützen.  
  
 Die Teile des MFC-Frameworks sichtbarste sowohl für die Benutzer und den Programmierer sind das Dokument und Ansicht. Die meisten Schritte bei der Entwicklung einer Anwendung mit dem Framework wechselt in Ihr Dokument und Ansicht Klassen schreiben. Diese Artikelreihe werden beschrieben:  
  
-   Im Sinne von Dokumenten und Ansichten und ihre Interaktion in Framework.  
  
-   Was Sie tun müssen, um sie zu implementieren.  
  
 Der Kern von Dokument-/Ansichtarchitektur sind Sie vier Hauptklassen:  
  
 Die [CDocument](../mfc/reference/cdocument-class.md) (oder [COleDocument](../mfc/reference/coledocument-class.md))-Klasse unterstützt Objekte, die zum Speichern oder Steuern von Daten in das Programm verwendet und stellt die Basisfunktionen für Programmierer definierte Dokumentklassen bereit. Ein Dokument stellt die Dateneinheit, die der Benutzer in der Regel mit dem Befehl im Menü Datei öffnen wird geöffnet und speichert im Menü Datei mit dem Befehl speichern.  
  
 Die [CView](../mfc/reference/cview-class.md) (oder alle abgeleiteten Klassen) stellt die Basisfunktionen für Programmierer definierte Ansichtsklassen bereit. Eine Sicht ist an ein Dokument angefügt und dient als Vermittler zwischen dem Dokument und der Benutzer: die Ansicht rendert ein Bild des Dokuments auf dem Bildschirm und Benutzereingaben als Vorgänge auf das Dokument interpretiert. Die Ansicht rendert auch das Bild für Drucken und Druckvorschau.  
  
 [CFrameWnd](../mfc/reference/cframewnd-class.md) (oder dessen Varianten) unterstützt Objekte, die den Rahmen um eine oder mehrere Ansichten eines Dokuments enthält.  
  
 [CDocTemplate](../mfc/reference/cdoctemplate-class.md) (oder [CSingleDocTemplate](../mfc/reference/csingledoctemplate-class.md) oder [CMultiDocTemplate](../mfc/reference/cmultidoctemplate-class.md)) unterstützt ein Objekt, das eine oder mehrere vorhandene Dokumente eines bestimmten Typs koordiniert und verwaltet den richtigen erstellen Dokument anzeigen und Frame-Windows-Objekte für diesen Typ.  
  
 Die folgende Abbildung zeigt die Beziehung zwischen einem Dokument und seinen Ansichtszustand.  
  
 ![Die Ansicht ist Teil des Dokuments, das angezeigt wird,](../mfc/media/vc379n1.gif "vc379n1")  
Dokument und Ansicht  
  
 Die Dokument-/Ansichtarchitektur-Implementierung in der Klassenbibliothek unterteilt die Daten selbst aus der Anzeige und Operationen für Benutzer auf die Daten. Alle Änderungen an den Daten werden über die Dokumentklasse verwaltet. Die Ansicht ruft diese Schnittstelle, um den Zugriff auf und aktualisieren Sie die Daten.  
  
 Dokumente, deren zugehörigen Ansichten und das Rahmenfenster, die frame-Ansichten werden durch eine Dokumentvorlage erstellt. Die Dokumentvorlage ist verantwortlich für das Erstellen und Verwalten aller Dokumente des Typs in einem Dokument.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
  
-   [Ein Portrait der Dokument-/Ansichtarchitektur](../mfc/a-portrait-of-the-document-view-architecture.md)  
  
-   [Vorteile der Dokument-/Ansichtarchitektur](../mfc/advantages-of-the-document-view-architecture.md)  
  
-   [Dokument und Ansicht-Klassen, die vom Anwendungs-Assistenten erstellt](../mfc/document-and-view-classes-created-by-the-mfc-application-wizard.md)  
  
-   [Alternativen zur Dokument-/Ansichtarchitektur](../mfc/alternatives-to-the-document-view-architecture.md)  
  
-   [Hinzufügen mehrerer Ansichten zu einem Dokument](../mfc/adding-multiple-views-to-a-single-document.md)  
  
-   [Verwenden von Dokumenten](../mfc/using-documents.md)  
  
-   [Verwenden von Ansichten](../mfc/using-views.md)  
  
-   [Mehrere Dokumenttypen, Ansichten und Rahmenfenster](../mfc/multiple-document-types-views-and-frame-windows.md)  
  
-   [Initialisieren und Bereinigen von Dokumenten und Ansichten](../mfc/initializing-and-cleaning-up-documents-and-views.md)  
  
-   [Initialisieren Sie Ihre eigenen Ergänzungen zum Dokument und Ansicht-Klassen](../mfc/creating-new-documents-windows-and-views.md)  
  
-   [Verwenden von Datenbankklassen mit Dokumenten und Ansichten](../data/mfc-using-database-classes-with-documents-and-views.md)  
  
-   [Verwenden von Datenbankklassen ohne Dokumente und Ansichten](../data/mfc-using-database-classes-without-documents-and-views.md)  
  
-   [Beispiele](../visual-cpp-samples.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Benutzeroberflächenelemente](../mfc/user-interface-elements-mfc.md)   
 [Windows](../mfc/windows.md)   
 [Rahmenfenster](../mfc/frame-windows.md)   
 [Dokumentvorlagen und der Erstellungsvorgang für die Dokument-/Ansichtarchitektur](../mfc/document-templates-and-the-document-view-creation-process.md)   
 [Erstellen von Dokument/Ansicht](../mfc/document-view-creation.md)   
 [Erstellen neuer Dokumente, Fenster und Ansichten](../mfc/creating-new-documents-windows-and-views.md)


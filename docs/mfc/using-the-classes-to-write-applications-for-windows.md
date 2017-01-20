---
title: "Verwenden der Klassen zum Schreiben von Anwendungen f&#252;r Windows"
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
  - "Anwendungen [OLE], MFC-Anwendungsframework"
  - "Datenbankanwendungen [C++], Erstellen"
  - "MFC [C++], Anwendungsentwicklung"
  - "MFC-ActiveX-Steuerelemente, Erstellen"
  - "OLE-Anwendungen [C++], MFC-Anwendungsframework"
  - "Windows-Anwendungen [C++], MFC-Anwendungsframework"
ms.assetid: 73f63470-857d-43dd-9a54-b38b7be0f1b7
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Verwenden der Klassen zum Schreiben von Anwendungen f&#252;r Windows
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Zusammen entnommen, bilden die Klassen der MFC\-Bibliothek \(Microsoft Foundation Class \(MFC\) ein "Anwendungsframework," auf, der Sie eine Anwendung für das Windows\-Betriebssystem erstellen.  Auf einer sehr allgemeine Ebene definiert das Framework das Skelett einer Anwendung und stellt Standardbenutzeroberflächenimplementierungen, die das Skelett platziert werden können.  Ihre Aufgabe als Programmierer ist, den Rest des Skeletts füllen, die die Aufgaben sind, die der Anwendung bestimmt sind.  Sie können einen Vorsprung abrufen, indem Sie den MFC\-Anwendungs\-Assistenten verwenden, um die Dateien für eine verhältnismäßig gründliche Startanwendung zu erstellen.  Sie verwenden die Microsoft Visual C\+\+\-Ressourcen\-Editoren, um Benutzeroberflächenelemente, die visuell Klassenansichtsbefehle, diese Elemente an Code herzustellen und die Klassenbibliothek entwerfen, um die anwendungsspezifische Logik zu implementieren.  
  
 Version 3.0 und höher unterstützt des MFC\-Frameworks Programmierung für Win32\-Plattformen, einschließlich Microsoft Windows 95 und höher und Windows NT\-Versionen 3.51 und höher.  MFC\-Unterstützung Win32 enthält Multithreading.  Verwenden Sie Version 1.5*x,* wenn Sie 16\-Bit\-Programmierung vornehmen müssen.  
  
 Diese Gruppe von Artikeln stellt eine allgemeine Übersicht des Anwendungsframeworks dar.  Sie behandelt auch die wichtigsten Objekte, die die Anwendung bilden und wie sie erstellt werden.  Die Themen, die diese Elemente ist werden die abgedeckten, folgenden:  
  
-   [Das Framework](../mfc/framework-mfc.md).  
  
-   Arbeitsteilung zwischen dem Framework und dem Code, wie in [Erstellen auf dem Framework](../mfc/building-on-the-framework.md) beschrieben.  
  
-   [Die Application\-Klasse](../mfc/cwinapp-the-application-class.md), das Funktionen auf Anwendungsebene kapselt.  
  
-   Wie ihre zugeordneten [Dokumentvorlagen](../mfc/document-templates-and-the-document-view-creation-process.md) Dokumente und Ansichten und Rahmenfenster erstellen und verwalten.  
  
-   [CWnd](../mfc/window-objects.md)\- Klasse, die Stammbasisklasse aller Fenster.  
  
-   [Grafikobjekte](../mfc/graphic-objects.md), z Stifte und Pinsel.  
  
 Andere Teile des Frameworkeinschließung:  
  
-   [Fensterobjekte: Übersicht](../mfc/window-objects.md)  
  
-   [Meldungsbehandlung und Zuordnung](../mfc/message-handling-and-mapping.md)  
  
-   [CObject, die Stamm\-Basisklasse in MFC](../mfc/using-cobject.md)  
  
-   [Dokument\-\/Ansichtarchitektur](../mfc/document-view-architecture.md)  
  
-   [Dialogfelder](../mfc/dialog-boxes.md)  
  
-   [Steuerelemente](../mfc/controls-mfc.md)  
  
-   [Steuerleisten](../mfc/control-bars.md)  
  
-   [OLE](../mfc/ole-in-mfc.md)  
  
-   [Speicherverwaltung](../mfc/memory-management.md)  
  
     Außer dem Geben Sie für die Vorteile im Schreiben von Anwendungen für das Windows\-Betriebssystem, es macht MFC auch viel einfacher, Anwendungen, die speziell OLE verwenden, das verknüpft Technologie und einbettet.  Sie können die Anwendung einen Container der visuellen Bearbeitungen im OLE, einen Server zur visuellen Bearbeitung in OLE oder beide machen, und Sie können Automatisierung hinzufügen, sodass andere Anwendungen Objekte in der Anwendung verwenden oder sogar es remote steuern können.  
  
-   [MFC\-ActiveX\-Steuerelemente](../mfc/mfc-activex-controls.md)  
  
     Das OLE\-Steuerelement\-Entwicklungs\-Kit \(CDK\) ist jetzt vollständig mit dem Framework integriert.  Diese Artikelfamilie bietet eine Übersicht der ActiveX\-Steuerelement\-Entwicklung mit MFC. \(ActiveX\-Steuerelemente wird vor OLE\-Steuerelemente.\)  
  
-   [Datenbank\-Programmierung](../data/data-access-programming-mfc-atl.md)  
  
     MFC stellt auch zwei Sätze Datenbankklassen bereit, die Schreibendatenzugriffs\-Anwendungen vereinfachen.  Verwenden der ODBC\-Datenbankklassen können Sie an Datenbanken durch Treibers der Open Database Connectivity \(ODBC\) herstellen, Datensätze aus Tabellen und Anzeigenregisterinformation in einer Form auf dem Bildschirm.  Verwenden der Datenzugriffsobjekt \(dao\)\- Klassen können Sie Datenbanken vom Microsoft Jet\-Datenbankmodul oder externen \(die NichtJet\-\) Datenquellen, z ODBC\-Datenquellen arbeiten.  
  
     Außerdem MFC ist vollständig für das Schreiben von Anwendungen, die Unicode und Mehrbyte\-Zeichensätze \(MBCS\) verwenden, insbesondere Doppelbyte\-Zeichensätze \(DBCS\) aktiviert.  
  
 Ein allgemeines Führungslinie zu MFC\-Dokumentation, finden Sie unter [Allgemeine MFC\-Themen](../mfc/general-mfc-topics.md).  
  
## Siehe auch  
 [Allgemeine MFC\-Themen](../mfc/general-mfc-topics.md)
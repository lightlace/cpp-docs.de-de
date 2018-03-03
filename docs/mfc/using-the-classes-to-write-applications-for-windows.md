---
title: "Verwenden der Klassen zum Schreiben von Anwendungen für Windows | Microsoft Docs"
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
- Windows applications [MFC], MFC application framework
- MFC, application development
- applications [OLE], MFC application framework
- MFC ActiveX controls [MFC], creating
- OLE applications [MFC], MFC application framework
- database applications [MFC], creating
ms.assetid: 73f63470-857d-43dd-9a54-b38b7be0f1b7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4a8edcabee2f835bd3a3acd0ff3789690764c397
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="using-the-classes-to-write-applications-for-windows"></a>Verwenden der Klassen zum Schreiben von Anwendungen für Windows
Zusammen bilden die Klassen in der Bibliothek der Microsoft Foundation Class (MFC) zusammen eine "Application Framework" auf dem Sie eine Anwendung für das Windows-Betriebssystem erstellen. Auf einer Ebene sehr Allgemein das Framework das Skelett einer Anwendung definiert und stellt die standardmäßigen Benutzeroberflächen-Implementierungen, die in das Skelett platziert werden können. Ihre Aufgabe als Programmierer sind, füllen Sie das restliche rumpfdefinition ist die Dinge, die für Ihre Anwendung spezifisch sind. Sie können einen Vorsprung abrufen, indem Sie mit dem MFC-Anwendung-Assistenten zur Erstellung der Dateien für eine sehr umfassend startanwendung. Sie verwenden die Microsoft Visual C++ Ressourcen-Editoren um die Elemente der Benutzeroberfläche visuell zu entwerfen Klassenansicht Befehle aus, um diese Elemente mit Code und die Klassenbibliothek herstellen, um die anwendungsspezifische Logik zu implementieren.  
  
 Version 3.0 und höher von MFC-Framework unterstützt Programmierung für Win32-Plattformen, einschließlich Microsoft Windows 95 und höher und Windows NT, Version 3.51 und höher. MFC-Win32-Unterstützung umfasst multithreading. Verwenden Sie Version 1.5*x* Wenn Sie 16-Bit-Programmierung durchführen müssen.  
  
 Diese Artikelreihe bietet einen umfassenden Überblick über das Anwendungsframework. Es wird untersucht, die wichtigsten Objekte, aus denen Ihre Anwendung und wie sie erstellt werden. Sind Sie die folgenden Schritte aus, auf die Themen in den folgenden Artikeln:  
  
-   [Das Framework](../mfc/framework-mfc.md).  
  
-   Verteilung der Arbeit zwischen dem Framework und den Code, wie in beschrieben [erstellen im Framework](../mfc/building-on-the-framework.md).  
  
-   [Die Anwendungsklasse](../mfc/cwinapp-the-application-class.md), die Funktionalität auf Anwendungsebene kapselt.  
  
-   Wie [Dokumentvorlagen](../mfc/document-templates-and-the-document-view-creation-process.md) erstellen und Verwalten von Dokumenten und ihre zugehörigen Ansichten und Rahmenfenster.  
  
-   Klasse [CWnd](../mfc/window-objects.md), Stammbasisklasse aller Fenster.  
  
-   [Grafikobjekte](../mfc/graphic-objects.md), z. B. Stifte und Pinsel.  
  
 Andere Teile des Frameworks enthalten:  
  
-   [Fensterobjekte: Übersicht](../mfc/window-objects.md)  
  
-   [Meldungsbehandlung und Zuordnung](../mfc/message-handling-and-mapping.md)  
  
-   [CObject Stammbasisklasse in MFC](../mfc/using-cobject.md)  
  
-   [Dokument-/Ansichtsarchitektur](../mfc/document-view-architecture.md)  
  
-   [Dialogfelder](../mfc/dialog-boxes.md)  
  
-   [Steuerelemente](../mfc/controls-mfc.md)  
  
-   [Steuerleisten](../mfc/control-bars.md)  
  
-   [OLE](../mfc/ole-in-mfc.md)  
  
-   [Speicherverwaltung](../mfc/memory-management.md)  
  
     Neben der Möglichkeit, eines Vorteil beim Schreiben von Anwendungen für Windows-Betriebssystems, erleichtert MFC auch zum Schreiben von Anwendungen, die speziell OLE verlinken und Einbetten Technologie verwenden. Sie können Ihre Anwendung eine OLE visuellen Container, eine visuelle Bearbeitung OLE-Server oder beides bearbeiten, und Sie können Automation hinzufügen, sodass andere Anwendungen können Objekte aus Ihrer Anwendung verwenden oder auch remote steuern.  
  
-   [MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)  
  
     Das OLE-Steuerelements Development Kit (CDK) ist jetzt vollständig in das Framework integriert. Diese Artikelreihe bietet einen Überblick über die Entwicklung von ActiveX-Steuerelementen mit MFC. (ActiveX-Steuerelemente wurden früher als OLE-Steuerelemente bezeichnet.)  
  
-   [Datenbankprogrammierung](../data/data-access-programming-mfc-atl.md)  
  
     MFC bietet auch zwei Sätze von Datenbankklassen, die Schreiben von Datenzugriff zu vereinfachen Anwendungen. Verwenden die ODBC-Datenbankklassen, Sie können Herstellen einer Verbindung mit Datenbanken über einen Treiber für Open Database Connectivity (ODBC) Datensätze aus Tabellen auswählen und anzeigen Aufzeichnen von Informationen in ein Formular auf dem Bildschirm. Verwenden die Klassen (DAO, Data Access Object), können Sie dann, mit Datenbanken über das Microsoft Jet-Datenbankmodul oder externe (nicht-Jet) Datenquellen, einschließlich ODBC-Datenquellen arbeiten.  
  
     Darüber hinaus MFC ist vollständig für das Schreiben von Anwendungen, die Unicode verwenden aktiviert und Mehrbyte-Zeichensätzen (MBCS), speziell Doppelbyte-Zeichensätze (DBCS).  
  
 Allgemeiner Leitfaden zur MFC-Dokumentation finden Sie unter [allgemeine MFC-Themen](../mfc/general-mfc-topics.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Allgemeine MFC-Themen](../mfc/general-mfc-topics.md)


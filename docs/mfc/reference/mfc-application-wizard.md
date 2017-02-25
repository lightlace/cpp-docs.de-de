---
title: "MFC-Anwendungs-Assistent | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.mfc.exe.overview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Ausführbare Dateien, Erstellen"
  - "MFC-Anwendungs-Assistent"
ms.assetid: 227ac090-921d-4b2f-be0a-66a5f4cab0d4
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# MFC-Anwendungs-Assistent
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der MFC\-Anwendungs\-Assistent erstellt eine Anwendung, die beim Kompilieren die grundlegenden Funktionen einer ausführbaren Windows\-Anwendung \(.exe\) implementiert.  Die MFC\-Startanwendung umfasst C\+\+\-Quelldateien \(.cpp\), Ressourcendateien \(.rc\), Headerdateien \(.h\) sowie eine Projektdatei \(.vcxproj\).  Der in diesen Startdateien generierte Code basiert auf MFC.  
  
> [!NOTE]
>  Abhängig von den ausgewählten Optionen kann der Assistent zusätzliche Projektdateien erstellen.  Wenn Sie auf der Seite [Erweiterte Funktionen](../../mfc/reference/advanced-features-mfc-application-wizard.md) die Option **Kontextbezogene Hilfe** auswählen, erstellt der Assistent die zum Kompilieren der Projekthilfedateien erforderlichen Dateien.  Weitere Informationen über die vom Assistenten erstellten Dateien finden Sie unter [Für Visual C\+\+\-Projekte erstellte Dateitypen](../../ide/file-types-created-for-visual-cpp-projects.md) und in der projekteigenen Datei "Info.txt".  
  
## Übersicht  
 Auf dieser Seite des Assistenten sind die aktuellen Anwendungseinstellungen für die zu erstellende MFC\-Anwendung aufgeführt.  Der Assistent erstellt ein Projekt standardmäßig wie folgt:  
  
-   [Anwendungstyp, MFC\-Anwendungs\-Assistent](../../mfc/reference/application-type-mfc-application-wizard.md)  
  
    -   Das Projekt wird mit MDI \(Multiple Document Interface\)\-Unterstützung mit Registerkarten erstellt.  Weitere Informationen finden Sie unter [SDI und MDI](../../mfc/sdi-and-mdi.md).  
  
    -   Das Projekt verwendet die [Dokument\-\/Ansichtsarchitektur](../../mfc/document-view-architecture.md).  
  
    -   Das Projekt verwendet Unicode\-Bibliotheken.  
  
    -   Das Projekt wird mit dem Visual Studio\-Projektformat erstellt und aktiviert visuelle Stilumschaltung.  
  
    -   Das Projekt verwendet MFC in einer gemeinsam genutzten DLL.  Weitere Informationen finden Sie unter [DLLs in Visual C\+\+](../../build/dlls-in-visual-cpp.md).  
  
-   [Verbunddokumentunterstützung, MFC\-Anwendungs\-Assistent](../../mfc/reference/compound-document-support-mfc-application-wizard.md)  
  
    -   Das Projekt bietet keine Unterstützung für Verbunddokumente.  
  
-   [Zeichenfolgen für Dokumentvorlagen, MFC\-Anwendungs\-Assistent](../../mfc/reference/document-template-strings-mfc-application-wizard.md)  
  
    -   Das Projekt verwendet den Projektnamen als standardmäßige Zeichenfolgen für Dokumentvorlagen.  
  
-   [Datenbankunterstützung, MFC\-Anwendungs\-Assistent](../../mfc/reference/database-support-mfc-application-wizard.md)  
  
    -   Das Projekt bietet keine Datenbankunterstützung.  
  
-   [Benutzeroberflächen\-Features, MFC\-Anwendungs\-Assistent](../../mfc/reference/user-interface-features-mfc-application-wizard.md)  
  
    -   Das Projekt implementiert die standardmäßigen Benutzeroberflächen\-Funktionen von Windows, darunter ein Systemmenü, eine Statusleiste, Schaltflächen zum Minimieren und Maximieren, ein Dialogfeld **Info**, eine Standardmenüleiste, eine andockbare Symbolleiste sowie untergeordnete Rahmen.  
  
-   [Erweiterte Features, MFC\-Anwendungs\-Assistent](../../mfc/reference/advanced-features-mfc-application-wizard.md)  
  
    -   Das Projekt unterstützt das Drucken und die Seitenansicht.  
  
    -   Das Projekt unterstützt ActiveX\-Steuerelemente.  Weitere Informationen finden Sie unter [Operationssequenz zur Erstellung von ActiveX\-Steuerelementen](../../mfc/sequence-of-operations-for-creating-activex-controls.md).  
  
    -   Folgende Funktionen werden vom Projekt nicht unterstützt: [Automatisierung](../../mfc/automation.md), [MAPI](../../mfc/mapi-support-in-mfc.md), [Windows\-Sockets](../../mfc/windows-sockets-in-mfc.md) oder Active Accessibility.  
  
    -   Das Projekt unterstützt die andockbaren Bereiche **Explorer**, **Ausgabe** und **Eigenschaften**.  
  
-   [Erstellte Klassen, MFC\-Anwendungs\-Assistent](../../mfc/reference/generated-classes-mfc-application-wizard.md)  
  
    -   Die Ansichtsklasse des Projekts wird von der [CView Class](../../mfc/reference/cview-class.md) abgeleitet.  
  
    -   Die Anwendungsklasse des Projekts wird von der [CWinAppEx Class](../../mfc/reference/cwinappex-class.md) abgeleitet.  
  
    -   Die Dokumentklasse des Projekts wird von der [CDocument Class](../../mfc/reference/cdocument-class.md) abgeleitet.  
  
    -   Die Hauptrahmenklasse des Projekts wird von der [CMDIFrameWndEx\-Klasse](../../mfc/reference/cmdiframewndex-class.md) abgeleitet.  
  
    -   Die untergeordnete Klasse des Projekts wird von der [CMDIChildWndEx\-Klasse](../../mfc/reference/cmdichildwndex-class.md) abgeleitet.  
  
 Um diese Standardeinstellungen zu ändern, klicken Sie in der linken Spalte des Assistenten auf die Titel der entsprechenden Registerkarten und nehmen auf der angezeigten Seite die Änderungen vor.  
  
 Nachdem Sie ein MFC\-Anwendungsprojekt erstellt haben, können Sie dem Projekt mithilfe der [Code\-Assistenten](../../ide/adding-functionality-with-code-wizards-cpp.md) von Visual C\+\+ Objekte oder Steuerelemente hinzufügen.  
  
## Siehe auch  
 [Erstellen einer MFC\-Anwendung](../../mfc/reference/creating-an-mfc-application.md)   
 [MFC\-Desktopanwendungen](../../mfc/mfc-desktop-applications.md)   
 [Verwenden der Klassen zum Schreiben von Anwendungen für Windows](../../mfc/using-the-classes-to-write-applications-for-windows.md)
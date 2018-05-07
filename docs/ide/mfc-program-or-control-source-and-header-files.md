---
title: MFC-Programm oder Steuern von Quell- und Headerdateien | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- file types [C++], MFC source and header
ms.assetid: f61419a8-bf69-4bbb-8f7c-1734be5e6db6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5ab1ed04b9890fbed8de8b59354ab36d7be063e7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="mfc-program-or-control-source-and-header-files"></a>MFC-Programm oder Steuern von Quell- und Headerdateien
Die folgenden Dateien werden erstellt, wenn Sie abhängig von den Optionen, die Sie für das Projekt auswählen, die Sie erstellen ein MFC-Projekt in Visual Studio erstellen. Das Projekt enthält z. B. *Projname*dlg.cpp und *Projname*dlg.h Dateien nur dann, wenn Sie ein Dialogfeld-basiertes Projekt oder eine Klasse erstellen.  
  
 All diese Dateien befinden sich der *Projname* Verzeichnis, und im Ordner Headerdateien (.h-Dateien) oder der Ordner für Quelldateien (CPP-Dateien) im Projektmappen-Explorer.  
  
|Dateiname|Beschreibung|  
|---------------|-----------------|  
|*Projektname*h|Die Haupt-Include-Datei für die Anwendung oder DLL. Sie enthält alle globale Symbolen und `#include` Direktiven für die anderen Header-Dateien. Es leitet die `CPrjnameApp` -Klasse aus `CWinApp` und deklariert ein `InitInstance` Memberfunktion. Für ein Steuerelement die `CPrjnameApp` von abgeleitete Klasse `COleControlModule`.|  
|*Projektname*cpp|Die Quelldatei des Hauptprogramms gestartet. Erstellt ein Objekt der Klasse `CPrjnameApp`, abgeleitet aus `CWinApp`, und überschreibt die `InitInstance` Memberfunktion.<br /><br /> Für ausführbare Dateien `CPrjnameApp::InitInstance` führt mehrere Aufgaben aus. Sie registriert Dokumentvorlagen, die als eine Verbindung zwischen Dokumenten und Ansichten dienen; erstellt ein Hauptrahmenfenster. und erstellt ein leeres Dokument (oder ein Dokument öffnet, wenn als Argument an die Anwendung angegeben wird).<br /><br /> Für DLLs und ActiveX (früher OLE) steuert, `CProjNameApp::InitInstance` Objektfactory für das Steuerelement mit OLE registriert, durch den Aufruf `COleObjectFactory::RegisterAll` und einen Aufruf zum `AfxOLEInit`. Darüber hinaus die Memberfunktion `CProjNameApp::ExitInstance` wird verwendet, um das Steuerelement mit einem Aufruf aus dem Speicher entladen **AfxOleTerm**.<br /><br /> Diese Datei auch registriert und hebt die Registrierung des Steuerelements in der Windows-Registrierung-Datenbank durch die Implementierung der `DllRegisterServer` und `DllUnregisterServer` Funktionen.|  
|*Projektname*ctrl.h, *Projname*Ctrl.cpp fest|Deklarieren und implementieren Sie die `CProjnameCtrl` Klasse. `CProjnameCtrl` stammt aus `COleControl`, und das Gerüst eines Implementierungen von mehreren Memberfunktionen definiert sind, die zu initialisieren, zu zeichnen und serialisieren (laden und speichern) des Steuerelements. Meldung, Ereignis- und Dispatchzuordnungen sind auch definiert.|  
|*Projektname*dlg.cpp, *Projname*dlg.h|Erstellt, wenn Sie eine auf Dialogfeldern basierende Anwendung auswählen. Die Dateien abgeleitet und implementiert die Dialogfeldklasse, die mit dem Namen `CProjnameDlg`, und schließen Sie das Gerüst eines Memberfunktionen, um ein Dialogfeld zu initialisieren und Ausführen von Dialogdatenaustausch (DDX). Eigener Dialogfeldklassen zu befindet sich auch in diesen Dateien nicht in *Projname*cpp.|  
|Dlgproxy.cpp Dlgproxy.h|In einer Dialogfeldern basierende Anwendung, die Implementierung und die Header-Datei für das Projekt Automation-Proxyklasse für das Dialogfeld "main". Dies wird nur verwendet, wenn Sie automatisierungsunterstützung ausgewählt haben.|  
|*Projektname*doc.cpp, *Projname*doc.h|Abgeleitet und implementiert die Dokumentklasse, mit dem Namen `CProjnameDoc`, und schließen Sie das Gerüst eines Memberfunktionen zu serialisieren, initialisieren ein Dokument (Speichern und laden) ein Dokument, und implementieren, die Diagnose Debuggen.|  
|*Projektname*set.h/.cpp|Erstellt, wenn Sie ein Programm erstellen, unterstützt eine Datenbank, und enthält das Recordset-Klasse.|  
|*Projektname*view.cpp, *Projname*view.h|Abgeleitet und implementiert die View-Klasse, die mit dem Namen `CProjnameView`, die zum Anzeigen und Drucken der Dokumentdaten verwendet wird. Die `CProjnameView` von einer der folgenden MFC-Klassen abgeleitete Klasse:<br /><br /> -   [CEditView](../mfc/reference/ceditview-class.md)<br />-   [CFormView](../mfc/reference/cformview-class.md)<br />-   [CRecordView](../mfc/reference/crecordview-class.md)<br />-   [COleDBRecordView](../mfc/reference/coledbrecordview-class.md)<br />-   [CTreeView](../mfc/reference/ctreeview-class.md)<br />-   [CListView](../mfc/reference/clistview-class.md)<br />-   [CRichEditView](../mfc/reference/cricheditview-class.md)<br />-   [CScrollView](../mfc/reference/cscrollview-class.md)<br />-   [CView](../mfc/reference/cview-class.md)<br />-   [CHTMLView](../mfc/reference/chtmlview-class.md)<br />-   [CHTMLEditView](../mfc/reference/chtmleditview-class.md)<br /><br /> View-Klasse für das Projekt enthält das Gerüst eines Memberfunktionen zeichnen Sie die Ansicht und die Diagnose Debuggen implementieren. Wenn Sie Unterstützung für den Druck aktiviert haben, klicken Sie dann Meldungszuordnungseinträge für das Drucken, Drucken von Setup hinzugefügt werden, und Drucken Preview Command-Meldungen. Diese Einträge rufen die entsprechende Memberfunktionen in der Basissicht-Klasse.|  
|*Projektname*PropPage.h, *Projname*PropPage.cpp|Deklarieren und implementieren Sie die `CProjnamePropPage` Klasse. `CProjnamePropPage` stammt aus `COlePropertyPage` und einer Skelett Memberfunktion `DoDataExchange`, dient der Datenaustausch und Überprüfung implementieren.|  
|"IpFrame.cpp", IPframe.h|Erstellt, wenn die Option Miniserver oder Vollserver im Anwendungs-Assistenten ausgewählt ist **Automatisierungsoptionen** Seite (Schritt 3 von 6). Die Dateien abgeleitet und implementiert die direkte Rahmenfenster (Klasse), mit dem Namen **CInPlaceFrame**, verwendet werden, wenn der Server vorhanden, die von einem Containerprogramm aktiviert ist.|  
|"MainFrm.cpp", "MainFrm.h"|Leiten Sie die **CMainFrame** Klasse entweder [CFrameWnd](../mfc/reference/cframewnd-class.md) (für SDI-Anwendungen) oder [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) (für MDI-Anwendungen). Die **CMainFrame** Klasse behandelt die Erstellung des Symbolleistenschaltflächen und der Statusleiste an, wenn die entsprechenden Optionen im Anwendungs-Assistenten aktiviert werden **Anwendungsoptionen** Seite (Schritt 4 6). Informationen zur Verwendung **CMainFrame**, finden Sie unter [das Rahmenfenster-Klassen erstellt vom Anwendungs-Assistenten](../mfc/frame-window-classes-created-by-the-application-wizard.md).|  
|"ChildFrm.cpp", "Dateien" ChildFrm.h "|Leiten Sie die **CChildFrame** -Klasse aus [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md). Die **CChildFrame** -Klasse wird für MDI-Dokumentrahmenfenstern verwendet. Diese Dateien werden immer erstellt, wenn Sie die MDI-Option.|  
  
## <a name="see-also"></a>Siehe auch  
 [Für Visual C++-Projekte erstellte Dateitypen](../ide/file-types-created-for-visual-cpp-projects.md)   
 [ATL-Programm oder Steuern von Quell- und Headerdateien](../ide/atl-program-or-control-source-and-header-files.md)   
 [CLR-Projekte](../ide/files-created-for-clr-projects.md)
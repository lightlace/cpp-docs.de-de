---
title: "MFC-Programm oder Steuern von Quell- und Headerdateien | Microsoft Docs"
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
  - "Dateitypen [C++], MFC-Quelle und -Header"
ms.assetid: f61419a8-bf69-4bbb-8f7c-1734be5e6db6
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# MFC-Programm oder Steuern von Quell- und Headerdateien
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Abhängig von den Optionen, die Sie für das erstellte Projekt auswählen, werden bei der Erstellung eines MFC\-Projekts in Visual Studio die folgenden Dateien generiert.  Beispielsweise enthält das Projekt die Dateien Projname**dlg.cpp** und Projname**dlg.h** nur unter der Voraussetzung, dass Sie ein auf Dialogfeldern basierendes Projekt oder eine Klasse erstellen.  
  
 Alle diese Dateien sind im Verzeichnis Projname und im Projektmappen\-Explorer entweder im Ordner **Headerdateien** \(H\-Dateien\) oder im Ordner **Quelldateien** \(CPP\-Dateien\) enthalten.  
  
|Dateiname|Beschreibung|  
|---------------|------------------|  
|*Projname*.h|Zentrale Includedatei für das Programm oder die DLL.  Sie enthält alle globalen Symbole und `#include`\-Anweisungen für andere Headerdateien.  Durch diese Datei wird die `CPrjnameApp`\-Klasse von `CWinApp` abgeleitet und eine `InitInstance`\-Memberfunktion deklariert.  Bei einem Steuerelement wird die `CPrjnameApp`\-Klasse von `COleControlModule` abgeleitet.|  
|*Projname*.cpp|Zentrale Programmquelldatei.  Sie erstellt ein Objekt der von `CWinApp` abgeleiteten `CPrjnameApp`\-Klasse und überschreibt die Memberfunktion `InitInstance`.<br /><br /> Bei ausführbaren Dateien hat `CPrjnameApp::InitInstance` verschiedene Funktionen:  Sie registriert Dokumentvorlagen, die als Verbindung zwischen Dokumenten und Ansichten verwendet werden, erstellt ein Hauptrahmenfenster und ein leeres Dokument \(oder öffnet ein Dokument, wenn es als Befehlszeilenargument für die Anwendung angegeben ist\).<br /><br /> Bei DLLs und ActiveX\-Steuerelementen \(früher OLE\) registriert `CProjNameApp::InitInstance` die Objekterstellung durch das Steuerelement bei OLE, indem `COleObjectFactory::RegisterAll` aufgerufen und ein Aufruf an `AfxOLEInit` gesendet wird.  Außerdem wird die Memberfunktion `CProjNameApp::ExitInstance` verwendet, um das Steuerelement mit einem Aufruf von **AfxOleTerm** aus dem Speicher zu entfernen.<br /><br /> Diese Datei sorgt auch für die Registrierung bzw. Aufhebung der Registrierung des Steuerelements in der Windows\-Registrierungsdatenbank, indem sie die Funktionen `DllRegisterServer` und `DllUnregisterServer` implementiert.|  
|*Projname*ctrl.h, *Projname*ctrl.cpp|Durch diese Dateien wird die `CProjnameCtrl`\-Klasse deklariert und implementiert.  `CProjnameCtrl` wird von `COleControl` abgeleitet, und außerdem wird ein Gerüst von Implementierungen einiger Memberfunktionen definiert, die das Steuerelement initialisieren, zeichnen und serialisieren \(laden und speichern\).  Meldungs\-, Ereignis\- und Dispatchzuordnungen werden ebenfalls definiert.|  
|*Projname*dlg.cpp, *Projname*dlg.h|Diese Dateien werden erstellt, wenn Sie eine auf Dialogfeldern basierende Anwendung wählen.  Durch diese Dateien wird die `CProjnameDlg`\-Dialogfeldklasse abgeleitet und implementiert. Sie enthalten ein Gerüst von Memberfunktionen zur Initialisierung eines Dialogfelds und zur Ausführung eines Dialogdatenaustausches \(DDX\).  Außerdem ist die **Info**\-Dialogfeldklasse anstelle von Projname**.cpp** in diesen Dateien enthalten.|  
|Dlgproxy.cpp, Dlgproxy.h|In einem auf Dialogfeldern basierenden Programm sind dies die Implementierungs\- und Headerdatei für die projektspezifische Automatisierungsproxyklasse des Hauptdialogfelds.  Sie werden nur verwendet, wenn Sie die Automatisierungsunterstützung aktiviert haben.|  
|*Projname*doc.cpp, *Projname*doc.h|Durch diese Dateien wird die `CProjnameDoc`\-Dokumentklasse abgeleitet und implementiert. Sie enthalten ein Gerüst von Memberfunktionen zur Initialisierung und Serialisierung \(Speichern und Laden\) eines Dokuments und implementieren außerdem Diagnosedienste für das Debuggen.|  
|*Projname*set.h\/.cpp|Diese Dateien werden erstellt, wenn Sie ein Programm entwickeln, das eine Datenbank unterstützt und die Recordsetklasse enthält.|  
|*Projname*view.cpp, *Projname*view.h|Durch diese Dateien wird die `CProjnameView`\-Ansichtsklasse abgeleitet und implementiert, die zum Anzeigen und Drucken der Dokumentdaten verwendet wird.  Die `CProjnameView`\-Klasse wird von einer der folgenden MFC\-Klassen abgeleitet:<br /><br /> -   [CEditView](../mfc/reference/ceditview-class.md)<br />-   [CFormView](../mfc/reference/cformview-class.md)<br />-   [CRecordView](../mfc/reference/crecordview-class.md)<br />-   [COleDBRecordView](../mfc/reference/coledbrecordview-class.md)<br />-   [CTreeView](../mfc/reference/ctreeview-class.md)<br />-   [CListView](../mfc/reference/clistview-class.md)<br />-   [CRichEditView](../mfc/reference/cricheditview-class.md)<br />-   [CScrollView](../mfc/reference/cscrollview-class.md)<br />-   [CView](../mfc/reference/cview-class.md)<br />-   [CHTMLView](../mfc/reference/chtmlview-class.md)<br />-   [CHTMLEditView](../mfc/reference/chtmleditview-class.md)<br /><br /> Die Ansichtsklasse des Projekts enthält ein Gerüst von Memberfunktionen, durch die die Ansicht gezeichnet und Diagnosedienste für das Debuggen implementiert werden.  Falls Sie Druckunterstützung aktiviert haben, werden Meldungszuordnungseinträge für Druck\-, Druckeinrichtungs\- und Seitenansichts\-Befehlsmeldungen hinzugefügt.  Durch diese Einträge werden die entsprechenden Memberfunktionen in der Basisansichtsklasse aufgerufen.|  
|*Projname*PropPage.h, *Projname*PropPage.cpp|Durch diese Dateien wird die `CProjnamePropPage`\-Klasse deklariert und implementiert.  `CProjnamePropPage` wird von `COlePropertyPage` abgeleitet, und für Datenaustausch und \-validierung steht ein Gerüst der Memberfunktion `DoDataExchange` zur Verfügung.|  
|IPframe.cpp, IPframe.h|Diese Dateien werden erstellt, wenn auf der Seite mit den Automatisierungsoptionen des Anwendungs\-Assistenten \(Schritt 3 von 6\) die Option **Miniserver** oder **Vollserver** ausgewählt wird.  Durch diese Dateien wird die direkte **CInPlaceFrame**\-Rahmenfensterklasse abgeleitet und implementiert. Diese Klasse wird verwendet, wenn der Server direkt durch ein Containerprogramm aktiviert wird.|  
|Mainfrm.cpp, Mainfrm.h|Durch diese Dateien wird die **CMainFrame**\-Klasse entweder von [CFrameWnd](../mfc/reference/cframewnd-class.md) \(für SDI\-Anwendungen\) oder von [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) \(für MDI\-Anwendungen\) abgeleitet.  Die **CMainFrame**\-Klasse verarbeitet die Erstellung der Symbolleisten\-Schaltflächen und der Statusleiste, sofern die entsprechenden Optionen auf der Seite **Anwendungsoptionen** \(Schritt 4 von 6\) des Anwendungs\-Assistenten ausgewählt wurden.  Informationen zur Verwendung von **CMainFrame** finden Sie unter [Die vom Anwendungs\-Assistenten erstellten Rahmenfensterklassen](../mfc/frame-window-classes-created-by-the-application-wizard.md).|  
|Childfrm.cpp, Childfrm.h|Durch diese Dateien wird die **CChildFrame**\-Klasse von [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) abgeleitet.  Die **CChildFrame**\-Klasse wird für MDI\-Dokumentrahmenfenster verwendet.  Diese Dateien werden immer erstellt, wenn Sie die MDI\-Option ausgewählt haben.|  
  
## Siehe auch  
 [Für Visual C\+\+\-Projekte erstellte Dateitypen](../ide/file-types-created-for-visual-cpp-projects.md)   
 [ATL\-Programm oder Steuern von Quell\- und Headerdateien](../ide/atl-program-or-control-source-and-header-files.md)   
 [CLR\-Projekte](../ide/files-created-for-clr-projects.md)
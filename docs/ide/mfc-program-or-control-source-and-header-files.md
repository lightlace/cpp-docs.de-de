---
title: MFC-Programm oder Steuern von Quell- und Headerdateien | Microsoft-Dokumentation
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
ms.openlocfilehash: 0cb9518f60db98bd590cecdffa09ee7d814241ac
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46447907"
---
# <a name="mfc-program-or-control-source-and-header-files"></a>MFC-Programm oder Steuern von Quell- und Headerdateien

Folgende Dateien werden abhängig von den ausgewählten Optionen für das Projekt erstellt, wenn Sie ein MFC-Projekt in Visual Studio erstellen. Ihr Projekt enthält die Dateien „*Projname*dlg.cpp“ und „*Projname*dlg.h“ beispielsweise nur, wenn Sie ein Projekt oder eine Klasse erstellen, das bzw. die auf Dialogfeldern basiert.

Diese Dateien befinden Sich alle im Verzeichnis *Projname*. Im Projektmappen-Explorer befinden diese sich entweder im Ordner „Headerdateien“ (H-Dateien) oder im Ordner „Quelldateien“ (CPP-Dateien).

|Dateiname|Beschreibung |
|---------------|-----------------|
|*Projname*.h|Die Hauptincludedatei für das Programm oder die DLL. Diese enthält alle globalen Symbole und `#include`-Direktiven für andere Headerdateien. Sie leitet die `CPrjnameApp`-Klasse von `CWinApp` ab und deklariert eine `InitInstance`-Memberfunktion. Für ein Steuerelement wird die `CPrjnameApp`-Klasse von `COleControlModule` abgeleitet.|
|*Projname*.cpp|Die Quelldatei des Hauptprogramms. Diese erstellt ein Objekt der Klasse `CPrjnameApp`, die von `CWinApp` abgeleitet wird, und überschreibt die `InitInstance`-Memberfunktion.<br /><br /> Für ausführbare Dateien führt die Funktion `CPrjnameApp::InitInstance` mehrere Aktionen durch. Sie registriert Dokumentvorlagen, die als Verbindung zwischen Dokumenten und Ansichten fungieren und erstellt ein Hauptrahmenfenster und ein leeres Dokument (oder öffnet ein Dokument, wenn eines in einem Befehlszeilenargument der Anwendung angegeben ist).<br /><br /> Für DLLs und ActiveX-Steuerelemente (früher OLE) registriert `CProjNameApp::InitInstance` die Objektfactory des Steuerelements mit OLE, indem die Funktion `COleObjectFactory::RegisterAll` aufgerufen wird, die einen Aufruf von `AfxOLEInit` durchführt. Zusätzlich wird die Memberfunktion `CProjNameApp::ExitInstance` verwendet, um das Steuerelement mithilfe eines Aufrufs von **AfxOleTerm** aus dem Arbeitsspeicher zu entladen.<br /><br /> Diese Datei registriert das Steuerelement durch die Implementierung der Funktionen `DllRegisterServer` und `DllUnregisterServer` ebenfalls in der Windows-Registrierungsdatenbank oder hebt dessen Registrierung auf.|
|*Projname*ctrl.h, *Projname*ctrl.cpp|Deklarieren und implementieren die `CProjnameCtrl`-Klasse. `CProjnameCtrl` wird von `COleControl` abgeleitet, und die Implementierung der Gerüste einiger Memberfunktionen, die das Steuerelement initialisieren, zeichnen und serialisieren (laden und speichern), werden definiert. Meldungs-, Ereignis- und Dispatchzuordnungen werden ebenfalls definiert.|
|*Projname*dlg.cpp, *Projname*dlg.h|Werden erstellt, wenn Sie eine dialogfeldbasierte Anwendung auswählen. Diese Dateien leiten die Dialogfeldklasse namens `CProjnameDlg` ab, implementieren sie und fügen Gerüste für Memberfunktionen ein, um ein Dialogfeld zu initialisieren und Dialogdatenaustausch (DDX) durchzuführen. Die Dialogfeldklasse „About“ befindet sich ebenfalls in diesen Dateien, nicht in „*Projname*.cpp“.|
|Dlgproxy.cpp, Dlgproxy.h|In einem dialogfeldbasierten Programm entsprechen diese der Implementierung und der Headerdatei für die Automatisierungsproxyklasse des Projekts im Hauptdialogfeld. Diese werden nur verwendet, wenn Sie „Automatisierungsunterstützung“ ausgewählt haben.|
|*Projname*doc.cpp, *Projname*doc.h|Leiten die Dokumentklasse namens `CProjnameDoc` ab und implementieren diese. Zudem sind Gerüste für Memberfunktionen enthalten, die ein Dokument initialisieren, serialisieren (laden und speichern) und Debuggingdiagnosen implementieren.|
|*Projname*set.h/.cpp|Werden erstellt, wenn Sie ein Programm erstellen, das eine Datenbank unterstützt und die Recordset-Klasse enthält.|
|*Projname*view.cpp, *Projname*view.h|Leiten die Ansichtsklasse namens `CProjnameView` ab, die zum Anzeigen und Drucken der Dokumentdaten verwendet wird, und implementieren diese. Die `CProjnameView`-Klasse wird von einer der folgenden MFC-Klassen abgeleitet:<br /><br /> -   [CEditView](../mfc/reference/ceditview-class.md)<br />-   [CFormView](../mfc/reference/cformview-class.md)<br />-   [CRecordView](../mfc/reference/crecordview-class.md)<br />-   [COleDBRecordView](../mfc/reference/coledbrecordview-class.md)<br />-   [CTreeView](../mfc/reference/ctreeview-class.md)<br />-   [CListView](../mfc/reference/clistview-class.md)<br />-   [CRichEditView](../mfc/reference/cricheditview-class.md)<br />-   [CScrollView](../mfc/reference/cscrollview-class.md)<br />-   [CView](../mfc/reference/cview-class.md)<br />-   [CHTMLView](../mfc/reference/chtmlview-class.md)<br />-   [CHTMLEditView](../mfc/reference/chtmleditview-class.md)<br /><br /> Die Ansichtsklasse des Projekts enthält Gerüste für Memberfunktionen, um die Ansicht zu zeichnen und Debuggingdiagnosen zu implementieren. Wenn Sie die Unterstützung für das Drucken aktiviert haben, werden Einträge für die Meldungszuordnung für Befehlsmeldungen zum Drucken, zur Druckeinrichtung und zur Druckvorschau hinzugefügt. Diese Einträge rufen die entsprechenden Memberfunktionen in der Basisansichtsklasse auf.|
|*Projname*PropPage.h, *Projname*PropPage.cpp|Deklarieren und implementieren die `CProjnamePropPage`-Klasse. `CProjnamePropPage` wird von `COlePropertyPage` abgeleitet, und das Gerüst der Memberfunktion `DoDataExchange` wird bereitgestellt, um den Datenaustausch und die Datenüberprüfung zu implementieren.|
|IPframe.cpp, IPframe.h|Werden erstellt, wenn die Option „Miniserver“ oder „Vollserver“ auf der Seite **Automatisierungsoptionen** des Anwendungs-Assistenten (Schritt 3 von 6) ausgewählt ist. Die Dateien leiten die direkte Rahmenfensterklasse namens **CInPlaceFrame** ab, die verwendet wird, wenn der Server direkt von einem Containerprogramm aktiviert wird, und implementieren diese.|
|Mainfrm.cpp, Mainfrm.h|Leiten die Klasse **CMainFrame** von [CFrameWnd](../mfc/reference/cframewnd-class.md) (für SDI-Anwendungen) oder [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) (für MDI-Anwendungen) ab. Die Klasse **CMainFrame** verarbeitet die Erstellung von Symbolleistenschaltflächen und der Statusleiste, wenn die entsprechenden Optionen auf der Seite **Anwendungsoptionen** des Anwendungs-Assistenten (Schritt 4 von 6) ausgewählt sind. Weitere Informationen zur Verwendung von **CMainFrame** finden Sie unter [The Frame-Window Classes Created by the Application Wizard (Vom Anwendungs-Assistenten erstellte Rahmenfensterklassen)](../mfc/frame-window-classes-created-by-the-application-wizard.md).|
|Childfrm.cpp, Childfrm.h|Leiten die Klasse **CChildFrame**von [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) ab. Die Klasse **CChildFrame** wird für MDI-Dokumentrahmenfenster verwendet. Diese Dateien werden immer erstellt, wenn Sie die MDI-Option auswählen.|

## <a name="see-also"></a>Siehe auch

[Für Visual C++-Projekte erstellte Dateitypen](../ide/file-types-created-for-visual-cpp-projects.md)<br>
[ATL-Programm oder Steuern von Quell- und Headerdateien](../ide/atl-program-or-control-source-and-header-files.md)<br>
[CLR Projects (CLR-Projekte)](../ide/files-created-for-clr-projects.md)
---
title: "CFrameWnd Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CFrameWnd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFrameWnd class"
  - "frame window classes, Basisklasse"
  - "frame windows, Erstellen"
  - "Einzeldokumentoberfläche (SDI), frame windows"
ms.assetid: e2220aba-5bf4-4002-b960-fbcafcad01f1
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CFrameWnd Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt die Funktionalität eines Windows\-SingleDocument Interface \(SDI\) nicht überschnitt oder Popuprahmenfenster, zusammen mit Member zum Verwalten des Fensters.  
  
## Syntax  
  
```  
class CFrameWnd : public CWnd  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CFrameWnd::CFrameWnd](../Topic/CFrameWnd::CFrameWnd.md)|Erstellt ein `CFrameWnd`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CFrameWnd::ActivateFrame](../Topic/CFrameWnd::ActivateFrame.md)|Macht die Rahmen sichtbar und werden für den Benutzer.|  
|[CFrameWnd::BeginModalState](../Topic/CFrameWnd::BeginModalState.md)|Legt das Rahmenfenster zu modalem fest.|  
|[CFrameWnd::Create](../Topic/CFrameWnd::Create.md)|Rufen Sie auf, um das Windows\-Rahmenfenster zu erstellen und zu initialisieren, das mit dem `CFrameWnd`\-Objekt zugeordnet ist.|  
|[CFrameWnd::CreateView](../Topic/CFrameWnd::CreateView.md)|Erstellt eine Ansicht in Frame, die nicht von `CView` abgeleitet wird.|  
|[CFrameWnd::DockControlBar](../Topic/CFrameWnd::DockControlBar.md)|Dockt eine Steuerleiste an.|  
|[CFrameWnd::EnableDocking](../Topic/CFrameWnd::EnableDocking.md)|Bietet eine Steuerleiste, angedockt werden.|  
|[CFrameWnd::EndModalState](../Topic/CFrameWnd::EndModalState.md)|Beendet den modalen Zustand des Rahmenfensters.  Aktiviert alle Fenster, die von `BeginModalState` deaktiviert werden.|  
|[CFrameWnd::FloatControlBar](../Topic/CFrameWnd::FloatControlBar.md)|Schwimmt eine Steuerleiste.|  
|[CFrameWnd::GetActiveDocument](../Topic/CFrameWnd::GetActiveDocument.md)|Gibt das aktive **CDocument**\-Objekt zurück.|  
|[CFrameWnd::GetActiveFrame](../Topic/CFrameWnd::GetActiveFrame.md)|Gibt das aktive `CFrameWnd`\-Objekt zurück.|  
|[CFrameWnd::GetActiveView](../Topic/CFrameWnd::GetActiveView.md)|Gibt das aktive `CView`\-Objekt zurück.|  
|[CFrameWnd::GetControlBar](../Topic/CFrameWnd::GetControlBar.md)|Ruft die Steuerleiste ab.|  
|[CFrameWnd::GetDockState](../Topic/CFrameWnd::GetDockState.md)|Ruft den Dockzustand eines Rahmenfensters ab.|  
|[CFrameWnd::GetMenuBarState](../Topic/CFrameWnd::GetMenuBarState.md)|Ruft den Anzeigenzustand des Menüs in der aktuellen MFC\-Anwendung ab.|  
|[CFrameWnd::GetMenuBarVisibility](../Topic/CFrameWnd::GetMenuBarVisibility.md)|Gibt an, ob das Standardverhalten des Menüs in der aktuellen MFC\-Anwendung entweder ausgeblendet oder angezeigt wird.|  
|[CFrameWnd::GetMessageBar](../Topic/CFrameWnd::GetMessageBar.md)|Gibt einen Zeiger auf die Statusleiste zurück, die dem Rahmenfenster gehört.|  
|[CFrameWnd::GetMessageString](../Topic/CFrameWnd::GetMessageString.md)|Ruft Meldung entsprechend einer Befehl ID ab|  
|[CFrameWnd::GetTitle](../Topic/CFrameWnd::GetTitle.md)|Ruft den Titel der zugehörigen Steuerleiste ab.|  
|[CFrameWnd::InitialUpdateFrame](../Topic/CFrameWnd::InitialUpdateFrame.md)|Bewirkt die `OnInitialUpdate`\-Memberfunktion, die allen Ansichten im aufgerufen werden Rahmenfenster, gehört.|  
|[CFrameWnd::InModalState](../Topic/CFrameWnd::InModalState.md)|Gibt einen Wert zurück, ob ein Rahmenfenster in einem modalen Zustand ist.|  
|[CFrameWnd::IsTracking](../Topic/CFrameWnd::IsTracking.md)|Bestimmt, ob gerade Splitterleiste bewegt wird.|  
|[CFrameWnd::LoadAccelTable](../Topic/CFrameWnd::LoadAccelTable.md)|aufrufen, um einer Zugriffstastentabelle zu laden.|  
|[CFrameWnd::LoadBarState](../Topic/CFrameWnd::LoadBarState.md)|aufrufen, um von Steuerleisteneinstellungen wiederherzustellen.|  
|[CFrameWnd::LoadFrame](../Topic/CFrameWnd::LoadFrame.md)|aufrufen, um eines Rahmenfensters von den Ressourceninformationen dynamisch zu erstellen.|  
|[CFrameWnd::NegotiateBorderSpace](../Topic/CFrameWnd::NegotiateBorderSpace.md)|Verhandelt über Rahmenleerzeichen im Rahmenfenster.|  
|[CFrameWnd::OnBarCheck](../Topic/CFrameWnd::OnBarCheck.md)|Aufgerufen, wenn eine Aktion auf der angegebenen Steuerleiste ausgeführt wird.|  
|[CFrameWnd::OnContextHelp](../Topic/CFrameWnd::OnContextHelp.md)|Handles UMSCHALT\+F1\-Hilfe für direkte Elemente.|  
|[CFrameWnd::OnSetPreviewMode](../Topic/CFrameWnd::OnSetPreviewMode.md)|Legt das Hauptrahmenfenster der Anwendung in und aus der Seitenansicht out fest.|  
|[CFrameWnd::OnUpdateControlBarMenu](../Topic/CFrameWnd::OnUpdateControlBarMenu.md)|Aufgerufen vom Framework, wenn das zugeordnete Menü aktualisiert wird.|  
|[CFrameWnd::RecalcLayout](../Topic/CFrameWnd::RecalcLayout.md)|Ordnet die Steuerleisten des Objekts `CFrameWnd` neu.|  
|[CFrameWnd::SaveBarState](../Topic/CFrameWnd::SaveBarState.md)|aufrufen, um von Steuerleisteneinstellungen zu speichern.|  
|[CFrameWnd::SetActivePreviewView](../Topic/CFrameWnd::SetActivePreviewView.md)|Legt die angegebene Ansicht fest, um die aktive Ansicht für Reich\-Vorschau zu sein.|  
|[CFrameWnd::SetActiveView](../Topic/CFrameWnd::SetActiveView.md)|Legt das aktive `CView`\-Objekt fest.|  
|[CFrameWnd::SetDockState](../Topic/CFrameWnd::SetDockState.md)|aufrufen, um des Rahmenfensters im Hauptfenster anzudocken.|  
|[CFrameWnd::SetMenuBarState](../Topic/CFrameWnd::SetMenuBarState.md)|Legt den Anzeigenzustand des Menüs in der aktuellen MFC\-Anwendung zu ausgeblendetem angezeigt oder fest.|  
|[CFrameWnd::SetMenuBarVisibility](../Topic/CFrameWnd::SetMenuBarVisibility.md)|Legt das Standardverhalten des Menüs in der aktuellen MFC\-Anwendung, ausgeblendet oder sichtbar ist entweder fest.|  
|[CFrameWnd::SetMessageText](../Topic/CFrameWnd::SetMessageText.md)|Legt den Text einer Standardstatusleiste fest.|  
|[CFrameWnd::SetProgressBarPosition](../Topic/CFrameWnd::SetProgressBarPosition.md)|Legt aktuelle Position für Windows 7\-Statusanzeige angezeigt Taskleiste auf fest.|  
|[CFrameWnd::SetProgressBarRange](../Topic/CFrameWnd::SetProgressBarRange.md)|Sätze reichen für Windows 7\-Statusanzeige, die auf Taskleiste angezeigt wird.|  
|[CFrameWnd::SetProgressBarState](../Topic/CFrameWnd::SetProgressBarState.md)|Legt den Typ und den Zustand der Statusanzeige fest, die auf einer Schaltfläche der Taskleiste angezeigt wird.|  
|[CFrameWnd::SetTaskbarOverlayIcon](../Topic/CFrameWnd::SetTaskbarOverlayIcon.md)|Überladen.  Gilt ein Overlay auf eine Schaltfläche der Taskleiste verwenden, um Anwendungsstatus oder eine Benachrichtigung dem hinzuweisen.|  
|[CFrameWnd::SetTitle](../Topic/CFrameWnd::SetTitle.md)|Legt den Titel der zugehörigen Steuerleiste fest.|  
|[CFrameWnd::ShowControlBar](../Topic/CFrameWnd::ShowControlBar.md)|aufrufen, um die Steuerleiste anzuzeigen.|  
|[CFrameWnd::ShowOwnedWindows](../Topic/CFrameWnd::ShowOwnedWindows.md)|Zeigt alle Fenster, die Nachfolger des `CFrameWnd`\-Objekts sind.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CFrameWnd::OnCreateClient](../Topic/CFrameWnd::OnCreateClient.md)|Stellt ein Clientfenster für den Frame erstellt.|  
|[CFrameWnd::OnHideMenuBar](../Topic/CFrameWnd::OnHideMenuBar.md)|Aufgerufen vor dem Menü in der aktuellen MFC\-Anwendung werden ausgeblendet.|  
|[CFrameWnd::OnShowMenuBar](../Topic/CFrameWnd::OnShowMenuBar.md)|Aufgerufen vor dem Menü in der aktuellen MFC\-Anwendung wird angezeigt.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CFrameWnd::m\_bAutoMenuEnable](../Topic/CFrameWnd::m_bAutoMenuEnable.md)|Die automatischen Steuerelemente aktivieren und deaktivieren Funktionalität für Menüelemente.|  
|[CFrameWnd::rectDefault](../Topic/CFrameWnd::rectDefault.md)|Führen Sie dieses statische `CRect` als Parameter, wenn Sie ein `CFrameWnd`\-Objekt erstellen, um Windows ermöglichen, des die ursprüngliche Größe und Position Fensters auszuwählen.|  
  
## Hinweise  
 Um ein nützliches Rahmenfenster für die Anwendung zu erstellen, leiten Sie eine Klasse von `CFrameWnd`.  Fügen Sie Membervariablen der abgeleiteten Klasse Speicherdatenbesonderen der Anwendung hinzu.  Implementieren Sie Meldungshandlermemberfunktionen und eine Meldungszuordnung in der abgeleiteten Klasse, um anzugeben, was geschieht, wenn Meldungen in das Fenster verwiesen werden.  
  
 Es gibt drei Möglichkeiten, ein Rahmenfenster zu erstellen:  
  
-   Erstellen Sie es direkt mithilfe [Erstellen Sie](../Topic/CFrameWnd::Create.md).  
  
-   Erstellen Sie es direkt mithilfe [LoadFrame](../Topic/CFrameWnd::LoadFrame.md).  
  
-   Erstellen Sie es indirekt mit einer Normal\-Vorlage.  
  
 Bevor Sie entweder **Create** oder `LoadFrame` aufrufen, müssen Sie das Rahmenfensterobjekt auf dem Heap mithilfe des Operators C\+\+ **new** erstellen.  Bevor Sie **Create** aufrufen, können Sie eine Fensterklasse mit der globalen Funktion [AfxRegisterWndClass](../Topic/AfxRegisterWndClass.md) auch registrieren, um die Symbol\- und Klassenformate für den Frame festzulegen.  
  
 Verwenden Sie die **Create**\-Memberfunktion, um die Erstellungsparameter der Rahmen als unmittelbare Argumente zu übergeben.  
  
 `LoadFrame` erfordert weniger Argumente als **Create** und ruft stattdessen den Großteil der Standardwerte von Ressourcen, einschließlich der Frame die Beschriftung, das Symbol, die Zugriffstastentabelle und das Menü ab.  Um nach `LoadFrame` möglich ist, müssen alle diese Ressourcen dieselbe Ressourcen\-ID \(beispielsweise, **IDR\_MAINFRAME**\) verfügen.  
  
 Wenn ein Objekt `CFrameWnd` Ansichten und Dokumente enthält, werden sie indirekt durch das Framework statt direkt von des Programmierers erstellt.  Das Objekt `CDocTemplate` instrumentiert die Erstellung von Rahmen, die Erstellung der enthaltenen Ansichten und die Verbindung der Ansichten zum entsprechenden Dokument.  Die Parameter des `CDocTemplate`\-Konstruktors geben `CRuntimeClass`, der drei betroffenen Klassen an \(Dokument, Frames und Ansicht\).  Ein Objekt `CRuntimeClass` wird durch das Framework verwendet, um neue Frames dynamisch zu erstellen, wenn es vom Benutzer angegeben wird \(beispielsweise, mithilfe des neuen Befehls der Datei oder \(Multiple Document Interface\) neuen Befehls Fensters\).  
  
 Eine Rahmenfensterklasse, die von `CFrameWnd` abgeleitet ist, muss deklariert werden mit `DECLARE_DYNCREATE`, damit der obige `RUNTIME_CLASS` Mechanismus ordnungsgemäß funktioniert.  
  
 `CFrameWnd` enthält Implementierungen, um die folgenden Aufgaben eines Hauptfensters in einer typischen Anwendung für Windows auszuführen:  
  
-   Ein `CFrameWnd` Rahmenfenster verwaltet aktive Ansicht eine gerade verfolgt die unabhängig vom Windows\-aktivenFensters oder des aktuellen Eingabefokus ist.  Wenn die Frames erneut aktiviert werden, wird die aktive Ansicht benachrichtigt, indem `CView::OnActivateView` aufruft.  
  
-   Befehlsmeldungen und viele allgemeine FrameBenachrichtigung Meldungen, einschließlich der, die von `OnSetFocus`, `OnHScroll` und `OnVScroll`\-Funktionen von `CWnd` behandelt werden, werden durch ein `CFrameWnd` Rahmenfenster der aktuell aktiven Ansicht delegiert.  
  
-   Das gerade aktive Ansicht \(oder aktuell aktiven untergeordneten MDI\-Rahmenfenster im \- MDI\-Frame\) kann die Beschriftung des Rahmenfensters bestimmen.  Diese Funktion kann deaktiviert werden, indem das **FWS\_ADDTOTITLE** Stilbit des Rahmenfensters veranschaulicht.  
  
-   Ein `CFrameWnd` Rahmenfenster verwaltet die Positionierung der Steuerleisten, der Ansichten und anderer untergeordneter Fenster innerhalb des Clientbereichs des Rahmenfensters.  Ein Rahmenfenster führt auch das Leerlaufaktualisieren der Symbolleiste und anderer Steuerleistenschaltflächen.  Ein `CFrameWnd` Rahmenfenster hat auch Standardimplementierungen von Befehlen für das Menüelement auf und weg auf der Symbolleiste und der Statusleiste.  
  
-   Ein `CFrameWnd` Rahmenfenster verwaltet die Hauptmenüleiste.  Wenn ein Popupmenü angezeigt wird, verwendet das Rahmenfenster den **UPDATE\_COMMAND\_UI** Mechanismus, um zu bestimmen, welche Menüelemente aktiviert sind, deaktiviert oder überprüft werden sollen.  Wenn der Benutzer ein Menüelement auswählt, aktualisiert das Rahmenfenster die Statusleiste mit der Meldungszeichenfolge für diesen Befehl.  
  
-   Ein `CFrameWnd` Rahmenfenster verfügt über eine optionale Zugriffstastentabelle, die automatisch Zugriffstasten übersetzt.  
  
-   Ein `CFrameWnd` Rahmenfenster verfügt über eine optionale Hilfe ID, die mit `LoadFrame` festgelegt wird, die für die kontextbezogene Hilfe verwendet wird.  Ein Rahmenfenster ist der zentrale Organisator von semimodal Status wie Modi der kontextbezogenen Hilfe \(UMSCHALT\+F1\) und der Seitenansicht.  
  
-   Ein `CFrameWnd` Rahmenfenster öffnet eine Datei, die vom Datei\-Manager gezogen wird und auf dem Rahmenfenster abgelegt ist.  Wenn eine Dateierweiterung bei der Anwendung registriert und zugeordnet wird, reagiert das Rahmenfenster auf den dynamischen Datenaustausch \(DDE\) öffnen Anforderung, die auftritt, wenn der Benutzer eine Datendatei im Datei\-Manager öffnet, oder wenn die **ShellExecute** Windows\-Funktion aufgerufen wird.  
  
-   Wenn das Rahmenfenster das Hauptanwendungsfenster \(das heißt, `CWinThread::m_pMainWnd`\) ist, wenn der Benutzer die Anwendung schließt das Rahmenfenster, fordert den Benutzer auf, alle geänderten Dokumente zu speichern \(für `OnClose` und `OnQueryEndSession`\).  
  
-   Wenn das Rahmenfenster das Hauptanwendungsfenster ist, ist das Rahmenfenster der Kontext für diese Ausführung WinHelp.  Das Rahmenfenster schließt, wechselt WINHELP.EXE ab, wenn es für die Hilfe für diese Anwendung gestartet wurde.  
  
 Verwenden Sie den Operator C\+\+ **delete**, um ein Rahmenfenster zu zerstören.  Verwenden Sie stattdessen `CWnd::DestroyWindow`.  Die `CFrameWnd` Implementierung von `PostNcDestroy` löscht das C\+\+\-Objekt, wenn das Fenster zerstört wird.  Wenn der Benutzer das Rahmenfenster enthält, wird der Standardwert `OnClose`\-Handler `DestroyWindow` auf.  
  
 Weitere Informationen zu `CFrameWnd`, finden Sie unter [Rahmenfenster](../../mfc/frame-windows.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CFrameWnd`  
  
## Anforderungen  
 **Header:** afxwin.h  
  
## Siehe auch  
 [CWnd\-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CWnd\-Klasse](../../mfc/reference/cwnd-class.md)   
 [CMDIFrameWnd Class](../../mfc/reference/cmdiframewnd-class.md)   
 [CMDIChildWnd Class](../../mfc/reference/cmdichildwnd-class.md)   
 [CView Class](../../mfc/reference/cview-class.md)   
 [CDocTemplate Class](../../mfc/reference/cdoctemplate-class.md)   
 [CRuntimeClass Structure](../../mfc/reference/cruntimeclass-structure.md)
---
title: CFrameWnd-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFrameWnd
- AFXWIN/CFrameWnd
- AFXWIN/CFrameWnd::CFrameWnd
- AFXWIN/CFrameWnd::ActivateFrame
- AFXWIN/CFrameWnd::BeginModalState
- AFXWIN/CFrameWnd::Create
- AFXWIN/CFrameWnd::CreateView
- AFXWIN/CFrameWnd::DockControlBar
- AFXWIN/CFrameWnd::EnableDocking
- AFXWIN/CFrameWnd::EndModalState
- AFXWIN/CFrameWnd::FloatControlBar
- AFXWIN/CFrameWnd::GetActiveDocument
- AFXWIN/CFrameWnd::GetActiveFrame
- AFXWIN/CFrameWnd::GetActiveView
- AFXWIN/CFrameWnd::GetControlBar
- AFXWIN/CFrameWnd::GetDockState
- AFXWIN/CFrameWnd::GetMenuBarState
- AFXWIN/CFrameWnd::GetMenuBarVisibility
- AFXWIN/CFrameWnd::GetMessageBar
- AFXWIN/CFrameWnd::GetMessageString
- AFXWIN/CFrameWnd::GetTitle
- AFXWIN/CFrameWnd::InitialUpdateFrame
- AFXWIN/CFrameWnd::InModalState
- AFXWIN/CFrameWnd::IsTracking
- AFXWIN/CFrameWnd::LoadAccelTable
- AFXWIN/CFrameWnd::LoadBarState
- AFXWIN/CFrameWnd::LoadFrame
- AFXWIN/CFrameWnd::NegotiateBorderSpace
- AFXWIN/CFrameWnd::OnBarCheck
- AFXWIN/CFrameWnd::OnContextHelp
- AFXWIN/CFrameWnd::OnSetPreviewMode
- AFXWIN/CFrameWnd::OnUpdateControlBarMenu
- AFXWIN/CFrameWnd::RecalcLayout
- AFXWIN/CFrameWnd::SaveBarState
- AFXWIN/CFrameWnd::SetActivePreviewView
- AFXWIN/CFrameWnd::SetActiveView
- AFXWIN/CFrameWnd::SetDockState
- AFXWIN/CFrameWnd::SetMenuBarState
- AFXWIN/CFrameWnd::SetMenuBarVisibility
- AFXWIN/CFrameWnd::SetMessageText
- AFXWIN/CFrameWnd::SetProgressBarPosition
- AFXWIN/CFrameWnd::SetProgressBarRange
- AFXWIN/CFrameWnd::SetProgressBarState
- AFXWIN/CFrameWnd::SetTaskbarOverlayIcon
- AFXWIN/CFrameWnd::SetTitle
- AFXWIN/CFrameWnd::ShowControlBar
- AFXWIN/CFrameWnd::ShowOwnedWindows
- AFXWIN/CFrameWnd::OnCreateClient
- AFXWIN/CFrameWnd::OnHideMenuBar
- AFXWIN/CFrameWnd::OnShowMenuBar
- AFXWIN/CFrameWnd::m_bAutoMenuEnable
- AFXWIN/CFrameWnd::rectDefault
dev_langs:
- C++
helpviewer_keywords:
- frame window classes, base class
- single document interface (SDI), frame windows
- frame windows, creating
- CFrameWnd class
ms.assetid: e2220aba-5bf4-4002-b960-fbcafcad01f1
caps.latest.revision: 21
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: a8df28ed10208973832476b68140594c206bc22b
ms.lasthandoff: 02/24/2017

---
# <a name="cframewnd-class"></a>CFrameWnd-Klasse
Stellt die Funktionalität eines Windows-SDI-Rahmenfensters (Single Document Interface) bereit, wobei es sich um ein überlappendes oder ein Popupfenster handeln kann. Ebenfalls bereitgestellt werden Member zum Verwalten des Fensters.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CFrameWnd : public CWnd  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFrameWnd::CFrameWnd](#cframewnd)|Erstellt ein `CFrameWnd`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFrameWnd::ActivateFrame](#activateframe)|Die Verfügbarkeit des Rahmens sichtbar und verfügbar für Benutzer.|  
|[CFrameWnd::BeginModalState](#beginmodalstate)|Die Frame-Fenster festgelegt Modal.|  
|[CFrameWnd::Create](#create)|Aufruf erstellt und initialisiert das zugeordnete Windows-Rahmenfenster der `CFrameWnd` Objekt.|  
|[CFrameWnd::CreateView](#createview)|Erstellt eine Ansicht in einem Rahmen, die nicht von abgeleitet ist `CView`.|  
|[CFrameWnd:: DockControlBar](#dockcontrolbar)|Wird eine Steuerleiste angedockt.|  
|[EnableDocking](#enabledocking)|Ermöglicht eine Steuerleiste angedockt werden.|  
|[CFrameWnd::EndModalState](#endmodalstate)|Beendet das Rahmenfenster modalen Zustand. Aktiviert alle deaktiviert Windows `BeginModalState`.|  
|[CFrameWnd::FloatControlBar](#floatcontrolbar)|Befindet sich eine Steuerleiste.|  
|[CFrameWnd::GetActiveDocument](#getactivedocument)|Gibt den aktiven **CDocument** Objekt.|  
|[CFrameWnd::GetActiveFrame](#getactiveframe)|Gibt den aktiven `CFrameWnd` Objekt.|  
|[CFrameWnd::GetActiveView](#getactiveview)|Gibt den aktiven `CView` Objekt.|  
|[CFrameWnd::GetControlBar](#getcontrolbar)|Ruft die Steuerleiste ab.|  
|[CFrameWnd::GetDockState](#getdockstate)|Ruft den Zustand Andocken eines Rahmenfensters.|  
|[CFrameWnd::GetMenuBarState](#getmenubarstate)|Ruft den Anzeigezustand des Menüs in der aktuellen MFC-Anwendung ab.|  
|[CFrameWnd::GetMenuBarVisibility](#getmenubarvisibility)|Gibt an, ob das Standardverhalten des Menüs in der aktuellen MFC-Anwendung entweder ausgeblendet oder sichtbar ist.|  
|[CFrameWnd::GetMessageBar](#getmessagebar)|Gibt einen Zeiger auf die Statusleiste, die an das Rahmenfenster gehören.|  
|[CFrameWnd::GetMessageString](#getmessagestring)|Ruft die Nachricht entspricht, um eine Befehls-ID.|  
|[CFrameWnd::GetTitle](#gettitle)|Ruft den Titel der zugehörigen Steuerleiste ab.|  
|[CFrameWnd::InitialUpdateFrame](#initialupdateframe)|Bewirkt, dass die `OnInitialUpdate` Memberfunktion, die für alle Ansichten in das Rahmenfenster aufgerufen werden.|  
|[CFrameWnd::InModalState](#inmodalstate)|Gibt einen Wert, der angibt, ob ein Rahmenfenster in einen modalen Zustand ist.|  
|[CFrameWnd::IsTracking](#istracking)|Bestimmt, ob die Teilerleiste gerade verschoben wird.|  
|[CFrameWnd::LoadAccelTable](#loadacceltable)|Rufen Sie eine Zugriffstastentabelle zu laden auf.|  
|[CFrameWnd:: LoadBarState](#loadbarstate)|Rufen Sie zum Wiederherstellen der Steuerleiste.|  
|[CFrameWnd::LoadFrame](#loadframe)|Rufen Sie ein Rahmenfenster von Ressourceninformationen dynamisch zu erstellen.|  
|[CFrameWnd::NegotiateBorderSpace](#negotiateborderspace)|Verhandelt Rahmen Speicherplatz im Rahmenfenster.|  
|[CFrameWnd::OnBarCheck](#onbarcheck)|Aufgerufen, wenn eine Aktion auf der angegebenen Steuerleiste ausgeführt wird.|  
|[CFrameWnd::OnContextHelp](#oncontexthelp)|UMSCHALT + F1-Hilfe für direktes Elemente verarbeitet werden.|  
|[CFrameWnd::OnSetPreviewMode](#onsetpreviewmode)|Legt Hauptrahmenfenster für die Anwendung, in und aus den Seitenansicht-Modus.|  
|[CFrameWnd::OnUpdateControlBarMenu](#onupdatecontrolbarmenu)|Wird vom Framework aufgerufen, wenn das zugehörige Menü aktualisiert wird.|  
|[CFrameWnd::RecalcLayout](#recalclayout)|Positioniert die Steuerleisten von der `CFrameWnd` Objekt.|  
|[SaveBarState](#savebarstate)|Rufen Sie zum Speichern der Steuerleiste.|  
|[CFrameWnd::SetActivePreviewView](#setactivepreviewview)|Legt die angegebene Ansicht die aktive Ansicht for Rich Preview sein.|  
|[CFrameWnd::SetActiveView](#setactiveview)|Die aktuelle `CView` Objekt.|  
|[CFrameWnd::SetDockState](#setdockstate)|Rufen Sie das Rahmenfenster im Hauptfenster angedockt.|  
|[CFrameWnd::SetMenuBarState](#setmenubarstate)|Legt den Anzeigezustand des Menüs in der aktuellen MFC-Anwendung, ausgeblendet oder angezeigt.|  
|[CFrameWnd::SetMenuBarVisibility](#setmenubarvisibility)|Legt das Standardverhalten des Menüs in der aktuellen MFC-Anwendung entweder ausgeblendet oder sichtbar sein.|  
|[CFrameWnd::SetMessageText](#setmessagetext)|Legt den Text einer standard-Statusleiste.|  
|[CFrameWnd::SetProgressBarPosition](#setprogressbarposition)|Legt die aktuelle Position für Windows 7-Statusanzeige auf der Taskleiste angezeigt.|  
|[CFrameWnd::SetProgressBarRange](#setprogressbarrange)|Windows 7-Statusanzeige auf der Taskleiste angezeigten Bereich festgelegt.|  
|[CFrameWnd::SetProgressBarState](#setprogressbarstate)|Legt fest, Typ und Status der Statusanzeige auf die Taskleistenschaltfläche angezeigt.|  
|[CFrameWnd::SetTaskbarOverlayIcon](#settaskbaroverlayicon)|Überladen. Bezieht sich auf die Taskleistenschaltfläche Anwendungsstatus oder eine Benachrichtigung an den Benutzer an eine Überlagerung.|  
|[CFrameWnd::SetTitle](#settitle)|Legt den Titel der zugehörigen Steuerleiste fest.|  
|[CFrameWnd::ShowControlBar](#showcontrolbar)|Rufen Sie die Steuerelement-Statusleiste angezeigt.|  
|[CFrameWnd::ShowOwnedWindows](#showownedwindows)|Zeigt alle Fenster, die Nachfolger der `CFrameWnd` Objekt.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFrameWnd::OnCreateClient](#oncreateclient)|Erstellt ein Clientfenster für den Frame.|  
|[CFrameWnd::OnHideMenuBar](#onhidemenubar)|Aufgerufen, bevor Sie in der aktuellen MFC-Anwendung im Menü ausgeblendet ist.|  
|[CFrameWnd::OnShowMenuBar](#onshowmenubar)|Aufgerufen, bevor das Menü in der aktuellen MFC-Anwendung angezeigt wird.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFrameWnd::m_bAutoMenuEnable](#m_bautomenuenable)|Automatische Steuerelemente aktivieren und Deaktivieren von Funktionen für Menüelemente.|  
|[CFrameWnd::rectDefault](#rectdefault)|Übergeben Sie diesen statischen `CRect` als Parameter beim Erstellen einer `CFrameWnd` Objekt ermöglicht Windows die ursprüngliche Größe und Position des Fensters wählen.|  
  
## <a name="remarks"></a>Hinweise  
 Um eine nützliche Rahmenfenster für Ihre Anwendung zu erstellen, leiten Sie eine Klasse von `CFrameWnd`. Fügen Sie der abgeleiteten Klasse zum Speichern von Daten, die spezifisch für Ihre Anwendung Membervariablen hinzu. Implementieren Sie Meldungshandler-Memberfunktionen und eine Meldungszuordnung in der abgeleiteten Klasse, um anzugeben, was passiert, wenn Meldungen an das Fenster weitergeleitet werden.  
  
 Es gibt drei Möglichkeiten zum Erstellen eines Rahmenfensters:  
  
-   Erstellen Sie direkt mit [erstellen](#create).  
  
-   Erstellen Sie direkt mit [LoadFrame](#loadframe).  
  
-   Erstellen Sie indirekt über eine Dokumentvorlage.  
  
 Vor dem Aufruf von entweder **erstellen** oder `LoadFrame`, müssen Sie das Rahmenfenster Objekt auf dem Heap mithilfe des C++ erstellen **neue** Operator. Vor dem Aufruf von **erstellen**, Sie können auch eine Fensterklasse mit Registrieren der [AfxRegisterWndClass](../../mfc/reference/application-information-and-management.md#afxregisterwndclass) -Funktion verwenden, um das Symbol und Stile für den Rahmen festzulegen.  
  
 Verwenden der **erstellen** Memberfunktion Erstellungsparameter des Frames als sofortige Argumente übergeben.  
  
 `LoadFrame`erfordert weniger Argumente als **erstellen**, und stattdessen entnimmt die Standardwerte von Ressourcen, einschließlich der Beschriftung, Symbol, Zugriffstastentabelle und im Menü des Frames. Zugänglich sein `LoadFrame`, alle diese Ressourcen müssen die gleichen Ressourcen-ID (z. B. **IDR_MAINFRAME**).  
  
 Wenn ein `CFrameWnd` Objekt enthält, Ansichten und Dokumente, die indirekt vom Framework nicht direkt durch den Programmierer erstellt werden. Das `CDocTemplate` Objekt orchestriert die Erstellung des Frames, die Erstellung der enthaltenden Ansichten und die Verbindung der Ansichten auf das entsprechende Dokument. Die Parameter von der `CDocTemplate` Konstruktor Festlegen der `CRuntimeClass` der drei Klassen beteiligt (Dokument, Rahmen und Ansicht). Ein `CRuntimeClass` Objekt wird vom Framework verwendet, dynamisch neue Frames an, wenn vom Benutzer angegeben (z. B. mithilfe von dem Menü Datei auf neu oder mehrere Document Interface (MDI) im Fenster neue Befehl) erstellt.  
  
 Eine Klasse abgeleitet `CFrameWnd` muss deklariert werden, mit `DECLARE_DYNCREATE` in der Reihenfolge für die oben genannten `RUNTIME_CLASS` Mechanismus ordnungsgemäß funktioniert.  
  
 Ein `CFrameWnd` enthält die standardimplementierungen zum Ausführen der folgenden Funktionen des ein Hauptfenster in einer normalen Anwendung für Windows:  
  
-   Ein `CFrameWnd` Rahmenfenster verfolgt des eine aktive Ansicht, die von Windows aktiven Fenster oder dem aktuellen Eingabefokus unabhängig ist. Wenn der Frame reaktiviert wird, wird die aktive Ansicht durch Aufrufen von benachrichtigt `CView::OnActivateView`.  
  
-   -Nachrichten und viele allgemeine Frame-Benachrichtigungen, einschließlich behandelt, indem die `OnSetFocus`, `OnHScroll`, und `OnVScroll` Funktionen der `CWnd`, delegiert werden, von einer `CFrameWnd` Rahmenfenster auf die derzeit aktive Ansicht.  
  
-   Die momentan aktiven Ansicht (oder den derzeit aktiven untergeordneten MDI-Rahmenfenster im Falle eines MDI-Rahmens) kann die Beschriftung des Rahmenfensters bestimmen. Diese Funktion deaktiviert werden, indem das Deaktivieren der **FWS_ADDTOTITLE** Formatbit des Rahmenfensters.  
  
-   Ein `CFrameWnd` Rahmenfenster verwaltet die Positionierung der Steuerleisten, Ansichten und anderen untergeordneten Fenster im Clientbereich des Rahmenfensters. Ein Rahmenfenster übernimmt außerdem die Zeit im Leerlauf zu aktualisieren, der Symbolleiste und andere Steuerleiste Schaltflächen. Ein `CFrameWnd` Rahmenfenster verfügt auch über standardimplementierungen von Befehlen zum ein- und Ausschalten der Symbolleiste und Statusleiste umschalten.  
  
-   Ein `CFrameWnd` Rahmenfenster verwaltet der Hauptmenüleiste. Wenn ein Popup-Menü angezeigt wird, das Rahmenfenster verwendet die **UPDATE_COMMAND_UI** Mechanismus, um zu bestimmen, welche Menüelemente aktiviert, deaktiviert oder aktiviert werden sollte,. Wenn der Benutzer ein Menüelement auswählt, aktualisiert das Rahmenfenster die Statusleiste mit der Zeichenfolge für den Befehl.  
  
-   Ein `CFrameWnd` Rahmenfenster ist eine optionale Accelerator-Tabelle, die automatisch Zugriffstasten übersetzt.  
  
-   Ein `CFrameWnd` Rahmenfenster ist eine optionale Hilfe-ID festgelegt `LoadFrame` , die für die kontextbezogene Hilfe verwendet wird. Ein Rahmenfenster ist die wichtigste Orchestrator der halbmodaler Zustand wie kontextbezogene Hilfe (UMSCHALT + F1) und Seitenansicht Modi.  
  
-   Ein `CFrameWnd` Rahmenfenster öffnet eine Datei aus dem Datei-Manager Drag & Drop auf das Rahmenfenster. Wenn Erweiterung registriert und der Anwendung zugeordnet ist, antwortet das Rahmenfenster auf die öffnen dynamische Daten Datenaustausch (DDE)-Anforderung, das auftritt, wenn der Benutzer eine Datei im Datei-Manager öffnet oder die **ShellExecute** Windows-Funktion wird aufgerufen.  
  
-   Wenn das Rahmenfenster Hauptfenster der Anwendung ist (d. h. `CWinThread::m_pMainWnd`), wenn der Benutzer die Anwendung schließt Rahmenfenster fordert den Benutzer zum Speichern geänderter Dokumente (für `OnClose` und `OnQueryEndSession`).  
  
-   Wenn das Rahmenfenster Hauptfenster der Anwendung ist, ist das Rahmenfenster den Kontext für die Ausführung von WinHelp. Schließen das Rahmenfenster WINHELP heruntergefahren wird. EXE-Datei, wenn sie Hilfe für diese Anwendung gestartet wurde.  
  
 Verwenden Sie nicht die C++ **löschen** Operator, um ein Rahmenfenster zu zerstören. Verwenden Sie stattdessen `CWnd::DestroyWindow` . Die `CFrameWnd` Implementierung von `PostNcDestroy` das C++-Objekt wird gelöscht, wenn das Fenster zerstört wird. Der Benutzer schließt das Rahmenfenster standardmäßig `OnClose` Handler ruft `DestroyWindow`.  
  
 Weitere Informationen zu `CFrameWnd`, finden Sie unter [Rahmenfenster](../../mfc/frame-windows.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CFrameWnd`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="activateframe"></a>CFrameWnd::ActivateFrame  
 Rufen Sie diese Memberfunktion zum Aktivieren und das Rahmenfenster wiederherstellen, sodass es für den Benutzer sichtbar und verfügbar ist.  
  
```  
virtual void ActivateFrame(int nCmdShow = -1);
```  
  
### <a name="parameters"></a>Parameter  
 `nCmdShow`  
 Gibt den Parameter an übergeben [ShowWindow](../../mfc/reference/cwnd-class.md#showwindow). Standardmäßig ist der Frame angezeigt und ordnungsgemäß wiederhergestellt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion wird normalerweise aufgerufen, nach einem Ereignis ohne Benutzeroberfläche, z. B. eine DDE, OLE, oder ein anderes Ereignis, das Rahmenfenster oder dessen Inhalt an dem Benutzer anzeigen kann.  
  
 Die standardmäßige Implementierung den Frame und schaltet sie am Anfang der Z-Reihenfolge und führt bei Bedarf die gleichen Schritte für das Hauptrahmenfenster für die Anwendung.  
  
 Überschreiben Sie diese Memberfunktion zum Ändern, wie ein Frame aktiviert wird. Beispielsweise können Sie untergeordnete MDI-Fenster zu maximiert werden erzwingen. Fügen Sie die entsprechenden Funktionen hinzu, und rufen Sie die Basisklassenversion mit einem expliziten `nCmdShow`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&#1;](../../mfc/reference/codesnippet/cpp/cframewnd-class_1.cpp)]  
  
##  <a name="beginmodalstate"></a>CFrameWnd::BeginModalState  
 Rufen Sie diese Memberfunktion auf, um ein Framefenster modal zu machen.  
  
```  
virtual void BeginModalState();
```  
  
##  <a name="cframewnd"></a>CFrameWnd::CFrameWnd  
 Erstellt ein `CFrameWnd` -Objekt, erstellt jedoch keine sichtbaren Rahmenfenster.  
  
```  
CFrameWnd();
```  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie **erstellen** zum Erstellen des Fensters sichtbar.  
  
##  <a name="create"></a>CFrameWnd::Create  
 Aufruf erstellt und initialisiert das zugeordnete Windows-Rahmenfenster der `CFrameWnd` Objekt.  
  
```  
virtual BOOL Create(
    LPCTSTR lpszClassName,  
    LPCTSTR lpszWindowName,  
    DWORD dwStyle = WS_OVERLAPPEDWINDOW,  
    const RECT& rect = rectDefault,  
    CWnd* pParentWnd = NULL,  
    LPCTSTR lpszMenuName = NULL,  
    DWORD dwExStyle = 0,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszClassName`  
 Zeigt auf eine Null-terminierte Zeichenfolge, die die Windows-Klasse bezeichnet. Der Name der Klasse kann einen beliebigen Namen registriert die `AfxRegisterWndClass` globale Funktion oder die **RegisterClass** Windows-Funktion. Wenn **NULL**, verwendet die vordefinierte `CFrameWnd` Attribute.  
  
 `lpszWindowName`  
 Zeigt auf eine Null-terminierte Zeichenfolge, die den Namen des Fensters darstellt. Als Text verwendet für die Titelleiste.  
  
 `dwStyle`  
 Gibt das Zeitfenster [Stil](../../mfc/reference/window-styles.md) Attribute. Enthalten die **FWS_ADDTOTITLE** formatieren, wenn die Titelleiste automatisch der Name des Dokuments dargestellt im Fenster angezeigt werden soll.  
  
 `rect`  
 Gibt die Größe und Position des Fensters. Die `rectDefault` Wert ermöglicht es Windows, um die Größe und Position des neuen Fensters festzulegen.  
  
 `pParentWnd`  
 Gibt das übergeordnete Fenster dieses Frame-Fensters. Dieser Parameter sollte sein **NULL** für übergeordnete Rahmenfenster.  
  
 *lpszMenuName*  
 Gibt den Namen der Menüressource im Fenster verwendet werden. Verwendung **MAKEINTRESOURCE** Wenn das Menü eine ganzzahlige ID anstelle einer Zeichenfolge enthält. Dieser Parameter kann **NULL**.  
  
 `dwExStyle`  
 Gibt an, das Fenster Erweiterte [Stil](../../mfc/reference/extended-window-styles.md) Attribute.  
  
 `pContext`  
 Gibt einen Zeiger auf eine [angegeben ist und](../../mfc/reference/ccreatecontext-structure.md) Struktur. Dieser Parameter kann **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Initialisierung erfolgreich ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Erstellen einer `CFrameWnd` Objekt in zwei Schritten. Zunächst rufen den Konstruktor, die erstellt, die `CFrameWnd` Objekt, und rufen Sie dann **erstellen**, die dem Windows-Rahmenfenster erstellt und fügt es der `CFrameWnd` Objekt. **Erstellen Sie** Klassennamen und den Namen des Fensters initialisiert und registriert Sie Standardwerte für Stil, übergeordnete und zugehörige Menü.  
  
 Verwendung `LoadFrame` statt **erstellen** Rahmenfenster aus einer Ressource anstatt Argumente zu laden.  
  
##  <a name="createview"></a>CFrameWnd::CreateView  
 Rufen Sie `CreateView` zum Erstellen einer Ansicht in einem Frame.  
  
```  
CWnd* CreateView(
    CCreateContext* pContext,  
    UINT nID = AFX_IDW_PANE_FIRST);
```  
  
### <a name="parameters"></a>Parameter  
 `pContext`  
 Gibt den Typ der Ansicht und des Dokuments.  
  
 `nID`  
 Die ID einer Ansicht.  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf eine `CWnd` -Objekt, wenn erfolgreich, andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion "Ansichten" erstellen, die nicht `CView`-abgeleitete innerhalb eines Rahmens. Nach dem Aufruf von `CreateView`, müssen Sie manuell die Ansicht auf aktiv festgelegt und legen Sie ihn sichtbar sein; diese Aufgaben werden nicht automatisch vom ausgeführt `CreateView`.  
  
##  <a name="dockcontrolbar"></a>CFrameWnd:: DockControlBar  
 Bewirkt, dass eine Symbolleiste an das Rahmenfenster angedockt werden.  
  
```  
void DockControlBar(
    CControlBar* pBar,  
    UINT nDockBarID = 0,  
    LPCRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `pBar`  
 Zeigt auf der Steuerleiste angedockt werden.  
  
 `nDockBarID`  
 Bestimmt, welche Seiten des Rahmenfensters das Andocken berücksichtigen. Es kann 0 oder eine oder mehrere der folgenden sein:  
  
- `AFX_IDW_DOCKBAR_TOP`Docken Sie an der Oberseite des Rahmenfensters.  
  
- **AFX_IDW_DOCKBAR_BOTTOM** Andocken an der Unterseite des Rahmenfensters.  
  
- `AFX_IDW_DOCKBAR_LEFT`Docken Sie an der linken Seite des Rahmenfensters.  
  
- `AFX_IDW_DOCKBAR_RIGHT`Docken Sie an der rechten Seite des Rahmenfensters.  
  
 Bei 0 kann eine Seite zum Andocken von Rahmenfenster Ziel aktiviert Steuerleiste angedockt werden.  
  
 `lpRect`  
 Bestimmt, in Bildschirmkoordinaten, die in den nicht-Clientbereich eines Rahmenfensters das Ziel, in dem die Steuerleiste angedockt wird.  
  
### <a name="remarks"></a>Hinweise  
 Auf einer Seite des angegebenen Fensters in den Aufrufen für beide Frame Steuerleiste angedockt [CControlBar:: EnableDocking](../../mfc/reference/ccontrolbar-class.md#enabledocking) und [EnableDocking](#enabledocking). Die ausgewählte Seite richtet sich nach `nDockBarID`.  
  
##  <a name="enabledocking"></a>EnableDocking  
 Mit dieser Funktion können andockbare Steuerleisten in einem Rahmenfenster aktivieren.  
  
```  
void EnableDocking(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>Parameter  
 `dwDockStyle`  
 Gibt an, welche Seiten des Rahmenfensters als Andocken Sites Steuerleisten dienen können. Es kann eine oder mehrere der folgenden sein:  
  
- `CBRS_ALIGN_TOP`Ermöglicht das Andocken am oberen Rand des Clientbereichs.  
  
- `CBRS_ALIGN_BOTTOM`Ermöglicht das Andocken am unteren Rand des Clientbereichs.  
  
- `CBRS_ALIGN_LEFT`Ermöglicht das Andocken auf der linken Seite des Clientbereichs.  
  
- `CBRS_ALIGN_RIGHT`Ermöglicht das Andocken auf der rechten Seite des Clientbereichs.  
  
- `CBRS_ALIGN_ANY`Ermöglicht das Andocken auf jeder Seite des Clientbereichs.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig werden Steuerleisten auf einer Seite des Fensters Frame in der folgenden Reihenfolge angedockt werden: oben, unten, links, rechts.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [Symbolleistenformate](../../mfc/reference/ctoolbar-class.md#create).  
  
##  <a name="endmodalstate"></a>CFrameWnd::EndModalState  
 Rufen Sie diese Memberfunktion auf, um ein Framefenster von einem modalen in einen Status ohne Modus zu ändern.  
  
```  
virtual void EndModalState();
```  
  
### <a name="remarks"></a>Hinweise  
 `EndModalState`aktiviert alle deaktiviert Windows [BeginModalState](#beginmodalstate).  
  
##  <a name="floatcontrolbar"></a>CFrameWnd::FloatControlBar  
 Mit dieser Funktion können dazu führen, dass eine Symbolleiste nicht an das Rahmenfenster angedockt werden.  
  
```  
void FloatControlBar(
    CControlBar* pBar,  
    CPoint point,  
    DWORD dwStyle = CBRS_ALIGN_TOP);
```  
  
### <a name="parameters"></a>Parameter  
 `pBar`  
 Verweist auf die Steuerleiste abgedockt werden.  
  
 `point`  
 Der Speicherort, in Bildschirmkoordinaten, in der oberen linken Ecke der Steuerleiste platziert werden.  
  
 `dwStyle`  
 Gibt an, ob die Steuerleiste in das neue Rahmenfenster horizontal oder vertikal ausrichten. Es kann eine der folgenden sein:  
  
- `CBRS_ALIGN_TOP`Wird die Steuerleiste vertikal ausgerichtet.  
  
- `CBRS_ALIGN_BOTTOM`Wird die Steuerleiste vertikal ausgerichtet.  
  
- `CBRS_ALIGN_LEFT`Wird die Steuerleiste horizontal ausgerichtet.  
  
- `CBRS_ALIGN_RIGHT`Wird die Steuerleiste horizontal ausgerichtet.  
  
 Wenn Stile horizontale und vertikale Ausrichtung angeben übergeben werden, wird die Symbolleiste horizontal ausgerichtet werden.  
  
### <a name="remarks"></a>Hinweise  
 In der Regel beim Start der Anwendung geschieht dies, wenn die Anwendung aus der vorherigen Ausführung Prozess ist.  
  
 Diese Funktion wird vom Framework aufgerufen, wenn der Benutzer eine Drop-Operation führt durch Loslassen der Maus während des Ziehens Steuerleiste über einen Speicherort, der für die Zuordnung nicht verfügbar ist.  
  
##  <a name="getactivedocument"></a>CFrameWnd::GetActiveDocument  
 Rufen Sie diese Memberfunktion, um einen Zeiger auf den aktuellen erhalten **CDocument** an der derzeit aktiven Ansicht.  
  
```  
virtual CDocument* GetActiveDocument();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die aktuelle [CDocument](../../mfc/reference/cdocument-class.md). Wenn keine aktuelle Dokument vorhanden ist, gibt **NULL**.  
  
##  <a name="getactiveframe"></a>CFrameWnd::GetActiveFrame  
 Rufen Sie diese Memberfunktion, um einen Zeiger auf das aktive Fenster multiple Document Interface (MDI) untergeordnetes Element von einem MDI-Rahmenfenster abzurufen.  
  
```  
virtual CFrameWnd* GetActiveFrame();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das aktive untergeordnete MDI-Fenster. Wenn die Anwendung einer SDI-Anwendung oder MDI-Rahmenfenster kein aktives Dokument, das die implizite ist **dies** Zeiger zurückgegeben werden.  
  
### <a name="remarks"></a>Hinweise  
 Wenn keine aktive untergeordnete MDI-Element oder die Anwendung single Document Interface (SDI), die implizite ist **dies** Zeiger zurückgegeben.  
  
##  <a name="getactiveview"></a>CFrameWnd::GetActiveView  
 Rufen Sie diese Memberfunktion, um einen Zeiger auf die aktive Ansicht (sofern vorhanden) an der ein Rahmenfenster erhalten ( `CFrameWnd`).  
  
```  
CView* GetActiveView() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die aktuelle [CView](../../mfc/reference/cview-class.md). Wenn keine aktuelle Ansicht vorhanden ist, gibt **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion gibt **NULL** beim Aufruf für eine MDI-Hauptrahmenfenster ( `CMDIFrameWnd`). In einer MDI-Anwendung muss das untergeordnete MDI-Hauptrahmenfenster keine Ansicht zugeordnet. Stattdessen jedes einzelnen untergeordneten Fenster ( `CMDIChildWnd`) hat eine oder mehrere zugeordnete Ansichten. Zuerst suchen das aktive untergeordnete MDI-Fenster und dann die aktive Ansicht für dieses untergeordnete Fenster suchen, kann die aktive Ansicht in einer MDI-Anwendung abgerufen werden. Das aktive untergeordnete MDI-Fenster finden Sie durch Aufrufen der Funktion `MDIGetActive` oder **GetActiveFrame** wie im folgenden gezeigt:  
  
 [!code-cpp[NVC_MFCWindowing&#2;](../../mfc/reference/codesnippet/cpp/cframewnd-class_2.cpp)]  
  
##  <a name="getcontrolbar"></a>CFrameWnd::GetControlBar  
 Rufen Sie `GetControlBar` für den Zugriff auf die Titelleiste, die mit der ID verknüpft ist  
  
```  
CControlBar* GetControlBar(UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 `nID`  
 Die ID einer Steuerleiste.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die Steuerleiste, die mit der ID verknüpft ist  
  
### <a name="remarks"></a>Hinweise  
 Die `nID` Parameter verweist auf den eindeutigen Bezeichner, der zum Übergeben der **erstellen** Methode der Steuerleiste. Weitere Informationen zu Steuerleisten, finden Sie unter dem Thema [Steuerleisten](../../mfc/control-bars.md).  
  
 `GetControlBar`Gibt die Steuerleiste zurück, selbst wenn es nicht verankert ist, und daher nicht gerade ein untergeordnetes Fenster des Frames ist.  
  
##  <a name="getdockstate"></a>CFrameWnd::GetDockState  
 Rufen Sie diese Memberfunktion zum Speichern der Zustandsinformationen über das Rahmenfenster Steuerleisten in einem `CDockState` Objekt.  
  
```  
void GetDockState(CDockState& state) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `state`  
 Enthält den aktuellen Status der Steuerleisten bei der Rückgabe des Rahmenfensters.  
  
### <a name="remarks"></a>Hinweise  
 Anschließend können Sie den Inhalt der schreiben `CDockState` -Speicher mithilfe `CDockState::SaveState` oder `Serialize`. Wenn Sie später die Steuerleisten in einem vorherigen Zustand wiederherstellen möchten, laden Sie den Status mit `CDockState::LoadState` oder `Serialize`, rufen Sie dann `SetDockState` den vorherigen Zustand das Rahmenfenster Steuerleisten anwenden.  
  
##  <a name="getmenubarstate"></a>CFrameWnd::GetMenuBarState  
 Ruft den Anzeigezustand des Menüs in der aktuellen MFC-Anwendung ab.  
  
```  
virtual DWORD GetMenuBarState();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Rückgabewert kann die folgenden Werte aufweisen:  
  
-   AFX_MBS_VISIBLE (0 x&01;) – klicken Sie im Menü wird angezeigt.  
  
-   AFX_MBS_HIDDEN (0 x&02;) – klicken Sie im Menü ausgeblendet ist.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein Laufzeitfehler auftritt, wird diese Methode Assertionen im Debugmodus und löst eine Ausnahme, die von abgeleiteten der [CException](../../mfc/reference/cexception-class.md) Klasse.  
  
##  <a name="getmenubarvisibility"></a>CFrameWnd::GetMenuBarVisibility  
 Gibt an, ob die Standardwerte des in der aktuellen MFC-Anwendung im Menü ausgeblendet oder sichtbar ist.  
  
```  
virtual DWORD CFrameWnd::GetMenuBarVisibility();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt einen der folgenden Werte zurück:  
  
-   AFX_MBV_KEEPVISIBLE (0 x&01;) – klicken Sie im Menü erscheint überhaupt jederzeit und von Standard verfügt nicht über den Fokus.  
  
-   AFX_MBV_DISPLAYONFOCUS (0 x&02;) – klicken Sie im Menü standardmäßig ausgeblendet ist. Wenn Sie im Menü angezeigt wird, drücken Sie ALT, um das Menü anzuzeigen, und geben Sie ihm den Fokus. Wenn Sie im Menü angezeigt wird, drücken Sie die ALT-Taste oder die ESC-Taste, um ihn auszublenden.  
  
-   AFX_MBV_ DISPLAYONFOCUS (0 X&02;) | AFX_MBV_DISPLAYONF10 (0 x&04;) (bitweise Kombination (OR)) – klicken Sie im Menü standardmäßig ausgeblendet ist. Wenn Sie im Menü angezeigt wird, drücken Sie F10, um das Menü anzuzeigen, und geben Sie ihm den Fokus. Wenn Sie im Menü angezeigt wird, drücken Sie F10, um den Fokus auf oder aus dem Menü zu wechseln. Das Menü wird angezeigt, bis Sie die ALT-Taste oder die ESC-Taste drücken, um es ausblenden.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein Laufzeitfehler auftritt, wird diese Methode Assertionen im Debugmodus und löst eine Ausnahme, die von abgeleiteten der [CException](../../mfc/reference/cexception-class.md) Klasse.  
  
##  <a name="getmessagebar"></a>CFrameWnd::GetMessageBar  
 Rufen Sie diese Memberfunktion zum Abrufen eines Zeigers auf der Statusleiste angezeigt.  
  
```  
virtual CWnd* GetMessageBar();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das Fenster mit der Statusleiste.  
  
##  <a name="getmessagestring"></a>CFrameWnd::GetMessageString  
 Überschreiben Sie diese Funktion, um benutzerdefinierte Zeichenfolgen für die Befehls-IDs angeben.  
  
```  
virtual void GetMessageString(
    UINT nID,  
    CString& rMessage) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nID`  
 Ressourcen-ID der gewünschten Nachricht.  
  
 `rMessage`  
 `CString`Objekt in der Nachricht platziert.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung lädt die durch angegebene Zeichenfolge einfach `nID` aus der Ressourcendatei. Diese Funktion wird vom Framework aufgerufen, wenn die Zeichenfolge in der Statusleiste aktualisieren benötigt.  
  
##  <a name="gettitle"></a>CFrameWnd::GetTitle  
 Ruft den Titel des Window-Objekts ab.  
  
```  
CString GetTitle() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) Objekt, das den aktuellen Titel des Window-Objekts enthält.  
  
##  <a name="initialupdateframe"></a>CFrameWnd::InitialUpdateFrame  
 Rufen Sie **IntitialUpdateFrame** nach dem Erstellen eines neuen Rahmens mit **erstellen**.  
  
```  
void InitialUpdateFrame(
    CDocument* pDoc,  
    BOOL bMakeVisible);
```  
  
### <a name="parameters"></a>Parameter  
 `pDoc`  
 Verweist auf das Dokument, das das Rahmenfenster zugeordnet ist. Kann **NULL**.  
  
 `bMakeVisible`  
 Wenn **TRUE**, gibt an, dass der Frame angezeigt werden soll. Wenn **FALSE**, keine abhängigen Elemente sichtbar gemacht werden.  
  
### <a name="remarks"></a>Hinweise  
 Dies bewirkt, dass alle Ansichten in diesem Frame Fenster erhalten ihre `OnInitialUpdate` aufrufen.  
  
 Außerdem war es nicht bereits eine aktive Ansicht, die Hauptansicht des Rahmenfensters active erfolgt. Die primäre Ansicht ist eine Ansicht mit der ID untergeordneten **AFX_IDW_PANE_FIRST**. Schließlich wird das Rahmenfenster sichtbar gemacht Wenn `bMakeVisible` ungleich NULL ist. Wenn `bMakeVisible` gleich 0 ist, die aktueller Fokus und den Sichtbarkeitsstatus des Rahmenfensters bleiben unverändert. Es ist nicht erforderlich, diese Funktion aufzurufen, wenn die Framework Implementierung von Datei auf neu und öffnen.  
  
##  <a name="inmodalstate"></a>CFrameWnd::InModalState  
 Rufen Sie diese Memberfunktion zu überprüfen, ob ein Rahmenfenster gebunden oder ungebunden ist.  
  
```  
BOOL InModalState() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn dies der Fall; andernfalls 0.  
  
##  <a name="istracking"></a>CFrameWnd::IsTracking  
 Rufen Sie diese Memberfunktion, um festzustellen, ob die Teilerleiste im Fenster gerade verschoben wird.  
  
```  
BOOL IsTracking() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn ein Splitter-Vorgang ausgeführt wird; andernfalls 0.  
  
##  <a name="loadacceltable"></a>CFrameWnd::LoadAccelTable  
 Rufen Sie zum Laden der angegebenen Zugriffstastentabelle.  
  
```  
BOOL LoadAccelTable(LPCTSTR lpszResourceName);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszResourceName`  
 Gibt den Namen der Ressource Accelerator. Verwendung **MAKEINTRESOURCE** , wenn die Ressource mit einer ganzzahligen ID identifiziert wird  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Zugriffstaste erfolgreich geladen wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Nur eine Tabelle kann gleichzeitig geladen werden.  
  
 Zugriffstastentabellen aus Ressourcen geladen werden automatisch freigegeben, wenn die Anwendung beendet wird.  
  
 Wenn Sie aufrufen `LoadFrame` um Rahmenfenster erstellen, lädt das Framework einer Zugriffstastentabelle zusammen mit den Ressourcen im Menü und Symbol und ein nachfolgender Aufruf von dieser Memberfunktion ist dann nicht erforderlich.  
  
##  <a name="loadbarstate"></a>CFrameWnd:: LoadBarState  
 Rufen Sie diese Funktion, um die Einstellungen für jede Steuerleiste, die im Besitz des Rahmenfensters wiederherzustellen.  
  
```  
void LoadBarState(LPCTSTR lpszProfileName);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszProfileName`  
 Name des einen Abschnitt in der Initialisierungsdatei (INI) oder einen Schlüssel in der Windows-Registrierung, der Speicherort der Zustandsinformationen.  
  
### <a name="remarks"></a>Hinweise  
 Informationen, die wiederhergestellt umfassen Sichtbarkeit, horizontaler/vertikaler Ausrichtung, Andockstatus und Steuerleiste Position.  
  
 Die Einstellungen, die Sie wiederherstellen möchten müssen in die Registrierung geschrieben werden, vor dem Aufruf von `LoadBarState`. Schreiben der Informationen in der Registrierung durch Aufrufen von [CWinApp::SetRegistryKey](../../mfc/reference/cwinapp-class.md#setregistrykey). Schreiben Sie die Informationen in die INI-Datei durch Aufrufen von [SaveBarState](#savebarstate).  
  
##  <a name="loadframe"></a>CFrameWnd::LoadFrame  
 Rufen Sie ein Rahmenfenster von Ressourceninformationen dynamisch zu erstellen.  
  
```  
virtual BOOL LoadFrame(
    UINT nIDResource,  
    DWORD dwDefaultStyle = WS_OVERLAPPEDWINDOW | FWS_ADDTOTITLE,  
    CWnd* pParentWnd = NULL,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `nIDResource`  
 Die ID des freigegebenen Ressourcen, die das Rahmenfenster zugeordnet.  
  
 *dwDefaultStyle*  
 Des Frames [Stil](../../mfc/reference/window-styles.md). Enthalten die **FWS_ADDTOTITLE** formatieren, wenn die Titelleiste automatisch der Name des Dokuments dargestellt im Fenster angezeigt werden soll.  
  
 `pParentWnd`  
 Ein Zeiger auf den Rand des übergeordneten.  
  
 `pContext`  
 Ein Zeiger auf eine [angegeben ist und](../../mfc/reference/ccreatecontext-structure.md) Struktur. Dieser Parameter kann **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Erstellen einer `CFrameWnd` Objekt in zwei Schritten. Zunächst rufen den Konstruktor, die erstellt, die `CFrameWnd` -Objekt, und rufen Sie dann `LoadFrame`, die lädt das Windows-Rahmenfenster und die zugehörigen Ressourcen und fügt das Rahmenfenster der `CFrameWnd` Objekt. Die `nIDResource` Parameter gibt an, klicken Sie im Menü, der Zugriffstastentabelle, das Symbol und die Zeichenfolgenressource des Titels für das Rahmenfenster.  
  
 Verwenden der **erstellen** Memberfunktion statt `LoadFrame` Wenn Sie alle Erstellungsparameter des Rahmenfensters angeben möchten.  
  
 Das Framework ruft `LoadFrame` beim Erstellen eines Rahmenfensters Verwendung eines Dokumentobjekts-Vorlage.  
  
 Das Framework verwendet die `pContext` Argument für die Objekte an das Rahmenfenster, einschließlich der verbunden werden sollen enthaltenen Objekte anzeigen. Sie können festlegen, die `pContext` Argument **NULL** beim Aufruf von `LoadFrame`.  
  
##  <a name="m_bautomenuenable"></a>CFrameWnd::m_bAutoMenuEnable  
 Wenn dieses Datenelement aktiviert ist (die Standardeinstellung), Menüelemente, die keinen `ON_UPDATE_COMMAND_UI` oder `ON_COMMAND` Handler werden automatisch deaktiviert, wenn der Benutzer aus einer entnimmt.  
  
```  
BOOL m_bAutoMenuEnable;  
```  
  
### <a name="remarks"></a>Hinweise  
 Menüelemente, die über eine `ON_COMMAND` -Handler jedoch nicht `ON_UPDATE_COMMAND_UI` Handler wird automatisch aktiviert.  
  
 Wenn dieses Datenelement festgelegt ist, werden Menüelemente auf die gleiche Weise automatisch aktiviert, die Symbolleisten-Schaltflächen aktiviert sind.  
  
> [!NOTE]
> `m_bAutoMenuEnable`hat keine Auswirkung auf der obersten Ebene.  
  
 Dieses Datenelement vereinfacht die Implementierung der optionale Befehle basierend auf der aktuellen Auswahl und verringert den Bedarf an schreiben `ON_UPDATE_COMMAND_UI` Handler für das Aktivieren und Deaktivieren von Menüelementen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&3;](../../mfc/reference/codesnippet/cpp/cframewnd-class_3.cpp)]  
  
##  <a name="negotiateborderspace"></a>CFrameWnd::NegotiateBorderSpace  
 Rufen Sie diese Memberfunktion zum Rahmen Speicherplatz in einem Rahmenfenster während der Aktivierung der OLE-Inplace aushandeln.  
  
```  
virtual BOOL NegotiateBorderSpace(
    UINT nBorderCmd,  
    LPRECT lpRectBorder);
```  
  
### <a name="parameters"></a>Parameter  
 *nBorderCmd*  
 Enthält einen der folgenden Werte aus der **Enum BorderCmd**:  
  
- **BorderGet** = 1  
  
- **BorderRequest** = 2  
  
- **BorderSet** = 3  
  
 `lpRectBorder`  
 Zeiger auf eine [RECT](../../mfc/reference/rect-structure1.md) Struktur oder ein [CRect](../../atl-mfc-shared/reference/crect-class.md) -Objekt, das die Koordinaten des Rahmens angibt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion ist die **CFrameWnd** Implementierung von OLE Rahmen Speicherplatz Aushandlung.  
  
##  <a name="onbarcheck"></a>CFrameWnd::OnBarCheck  
 Aufgerufen, wenn eine Aktion auf der angegebenen Steuerleiste ausgeführt wird.  
  
```  
afx_msg BOOL OnBarCheck(UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 `nID`  
 Die ID des Steuerelements Leiste angezeigt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Steuerleiste vorhanden sind; andernfalls 0.  
  
##  <a name="oncontexthelp"></a>CFrameWnd::OnContextHelp  
 UMSCHALT + F1-Hilfe für direktes Elemente verarbeitet werden.  
  
```  
afx_msg void OnContextHelp();
```  
  
### <a name="remarks"></a>Hinweise  
 Um kontextbezogene Hilfe zu aktivieren, fügen Sie ein  
  
 [!code-cpp[NVC_MFCDocViewSDI Nr.&16;](../../mfc/codesnippet/cpp/cframewnd-class_4.cpp)]  
  
 Anweisung, um Ihre `CFrameWnd` meldungszuordnung Klasse und einen Zugriffstastentabelle-Eintrag in der Regel UMSCHALT + F1 drücken, aktivieren Sie diese Memberfunktion hinzufügen.  
  
 Wenn Ihre Anwendung einen OLE-Container, `OnContextHelp` setzt alle an die Elemente in der Frame-Window-Objekt in den Hilfemodus. Wechselt der Cursor zu einem Pfeil und ein Fragezeichen, und der Benutzer können dann den Mauszeiger und drücken Sie die linke Maustaste gedrückt, um ein Dialogfeld, Fenster, Menüs oder Befehlsschaltfläche auszuwählen. Diese Member-Funktion ruft die Windows-Funktion `WinHelp` mit dem Hilfekontext des Objekts unter dem Cursor.  
  
##  <a name="oncreateclient"></a>CFrameWnd::OnCreateClient  
 Vom Framework aufgerufen wird, während der Ausführung des `OnCreate`.  
  
```  
virtual BOOL OnCreateClient(
    LPCREATESTRUCT lpcs,  
    CCreateContext* pContext);
```  
  
### <a name="parameters"></a>Parameter  
 `lpcs`  
 Ein Zeiger auf ein Windows [CREATESTRUCT](../../mfc/reference/createstruct-structure.md) Struktur *.*  
  
 `pContext`  
 Ein Zeiger auf eine [angegeben ist und](../../mfc/reference/ccreatecontext-structure.md) Struktur *.*  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion niemals aufrufen.  
  
 Die standardmäßige Implementierung dieser Funktion erstellt eine `CView` Objekt aus den Angaben im `pContext`, sofern dies möglich.  
  
 Überschreiben Sie diese Funktion, um die übergebenen Werte überschreiben die `CCreateContext` -Objekt bzw. so ändern Sie die Funktionsweise der Steuerelemente im Clientbereich des Rahmenfensters main erstellt werden. Die `CCreateContext` Elemente, die Sie überschreiben können, werden im Abschnitt der [angegeben ist und](../../mfc/reference/ccreatecontext-structure.md) Klasse.  
  
> [!NOTE]
>  Tauschen Sie die übergebenen Werte für die `CREATESTRUCT` Struktur. Sie sind nur für Informationszwecke. Wenn Sie das erste Fenster Rechteck überschreiben möchten, z. B. überschreiben die `CWnd` Memberfunktion [PreCreateWindow](../../mfc/reference/cwnd-class.md#precreatewindow).  
  
##  <a name="onhidemenubar"></a>CFrameWnd::OnHideMenuBar  
 Diese Funktion wird aufgerufen, wenn das System zum Ausblenden der Menüleiste in der aktuellen MFC-Anwendung.  
  
```  
virtual void OnHideMenuBar();
```  
  
### <a name="remarks"></a>Hinweise  
 Dieser Ereignishandler kann die Anwendung benutzerdefinierte Aktionen durchzuführen, wenn das System das Menü ausgeblendet wird. Sie können nicht verhindern, dass im Menü ausgeblendet, aber Sie können z. B. andere Methoden, um das Format oder den Status abrufen aufrufen.  
  
##  <a name="onsetpreviewmode"></a>CFrameWnd::OnSetPreviewMode  
 Rufen Sie diese Memberfunktion auf, um für das Hauptrahmenfenster den Seitenansichtmodus zu aktivieren oder zu deaktivieren.  
  
```  
virtual void OnSetPreviewMode(
    BOOL bPreview,  
    CPrintPreviewState* pState);
```  
  
### <a name="parameters"></a>Parameter  
 *bPreview*  
 Gibt an, ob die Anwendung im Seitenansichtmodus-platzieren. Legen Sie auf **TRUE** , platzieren in der Seitenansicht **FALSE** Vorschaumodus Abbrechen.  
  
 `pState`  
 Ein Zeiger auf eine **CPrintPreviewState** Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung deaktiviert alle Standardsymbolleisten und im Hauptmenü und die wichtigsten Fenster ausgeblendet. Dies wandelt MDI-Rahmenfenster in temporären SDI-Rahmenfenster.  
  
 Überschreiben Sie diese Member-Funktion, um das aus- und Einblenden von Steuerleisten und andere Teile der Frame-Fensters Seitenansicht anzupassen. Rufen Sie die Implementierung der Basisklasse aus der überschriebenen Version.  
  
##  <a name="onshowmenubar"></a>CFrameWnd::OnShowMenuBar  
 Diese Funktion wird aufgerufen, wenn das System gerade die Menüleiste in der aktuellen MFC-Anwendung anzeigen.  
  
```  
virtual void OnShowMenuBar();
```  
  
### <a name="remarks"></a>Hinweise  
 Dieser Ereignishandler kann die Anwendung benutzerdefinierte Aktionen auszuführen, wird im Menü angezeigt werden soll. Sie können nicht verhindern, dass das Menü angezeigt wird, aber Sie können z. B. andere Methoden, um das Format oder den Status abrufen aufrufen.  
  
##  <a name="onupdatecontrolbarmenu"></a>CFrameWnd::OnUpdateControlBarMenu  
 Wird vom Framework aufgerufen, wenn das zugehörige Menü aktualisiert wird.  
  
```  
afx_msg void OnUpdateControlBarMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>Parameter  
 `pCmdUI`  
 Ein Zeiger auf eine [CCmdUI](../../mfc/reference/ccmdui-class.md) -Objekt, das Menü, das generierte Update-Befehl darstellt. Ruft die Aktualisierung der [aktivieren](../../mfc/reference/ccmdui-class.md#enable) Memberfunktion der `CCmdUI` -Objekt über `pCmdUI` zum Aktualisieren der Benutzeroberfläche.  
  
##  <a name="recalclayout"></a>CFrameWnd::RecalcLayout  
 Vom Framework aufgerufen, wenn die standardmäßige Steuerleisten ein- oder ausschalten umgeschaltet werden, oder beim Ändern der Größe des Rahmenfensters.  
  
```  
virtual void RecalcLayout(BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `bNotify`  
 Bestimmt, ob das aktive in-Place-Element für das Rahmenfenster Benachrichtigung über die layoutänderung empfängt. Wenn **TRUE**, das Element ist, andernfalls benannten **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 Ruft die standardmäßige Implementierung von dieser Memberfunktion der `CWnd` Memberfunktion `RepositionBars` die Steuerleisten im Frame sowie die wichtigsten Fenster neu anordnen (in der Regel eine `CView` oder **MDICLIENT**).  
  
 Überschreiben Sie diese Memberfunktion, um das Aussehen und Verhalten der Steuerleisten steuern, nachdem das Layout des Rahmenfensters geändert wurde. Nennen Sie es z. B. beim Aktivieren oder Deaktivieren der Steuerleisten oder einem anderen Steuerleiste hinzufügen.  
  
##  <a name="rectdefault"></a>CFrameWnd::rectDefault  
 Übergeben Sie diesen statischen `CRect` als Parameter beim Erstellen eines Fensters zum Zulassen von Windows auf die ursprüngliche Größe und Position des Fensters wählen.  
  
```  
static AFX_DATA const CRect rectDefault;  
```  
  
##  <a name="savebarstate"></a>SaveBarState  
 Rufen Sie diese Funktion zum Speichern von Informationen zu jeder Steuerleiste, die im Besitz des Rahmenfensters.  
  
```  
void SaveBarState(LPCTSTR lpszProfileName) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `lpszProfileName`  
 Name des einen Abschnitt in der Initialisierungsdatei oder einen Schlüssel in der Windows-Registrierung, der Speicherort der Zustandsinformationen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Informationen kann Auslesen der Initialisierung mit [LoadBarState](#loadbarstate). Gespeicherten Informationen zählen die Sichtbarkeit von horizontaler/vertikaler Ausrichtung andocken, Zustand und Position des Steuerelements angezeigt.  
  
##  <a name="setactivepreviewview"></a>CFrameWnd::SetActivePreviewView  
 Legt die angegebene Ansicht die aktive Ansicht for Rich Preview sein.  
  
```  
void SetActivePreviewView(CView* pViewNew);
```  
  
### <a name="parameters"></a>Parameter  
 `pViewNew`  
 Ein Zeiger auf eine Ansicht aktiviert werden.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setactiveview"></a>CFrameWnd::SetActiveView  
 Rufen Sie diese Memberfunktion, um die aktive Ansicht festlegen.  
  
```  
void SetActiveView(
    CView* pViewNew,  
    BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 *pViewNew*  
 Gibt einen Zeiger auf eine [CView](../../mfc/reference/cview-class.md) -Objekt, oder **NULL** für keine aktive Ansicht.  
  
 `bNotify`  
 Gibt an, ob die Ansicht der Aktivierung benachrichtigt werden. Wenn **TRUE**, `OnActivateView` wird für die neue Ansicht; aufgerufen, wenn **FALSE**, nicht.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Funktion automatisch, wie der Benutzer den Fokus auf eine Ansicht im Rahmenfenster ändert. Sie können explizit aufrufen, `SetActiveView` in der angegebenen Ansicht wechseln.  
  
##  <a name="setdockstate"></a>CFrameWnd::SetDockState  
 Rufen Sie diese Memberfunktion zum Anwenden von Statusinformationen, die in gespeicherten ein `CDockState` -Objekt, das Rahmenfenster Steuerleisten.  
  
```  
void SetDockState(const CDockState& state);
```  
  
### <a name="parameters"></a>Parameter  
 `state`  
 Das Rahmenfenster Steuerleisten des gespeicherten Zustands zuweisen.  
  
### <a name="remarks"></a>Hinweise  
 Um einen früheren Zustand der Steuerleisten wiederherzustellen, können Sie den gespeicherten Zustand mit laden `CDockState::LoadState` oder `Serialize`, dann `SetDockState` für das Rahmenfenster Steuerleisten übernehmen. Der vorherige Status befindet sich in der `CDockState` Objekt`GetDockState`  
  
##  <a name="setmenubarstate"></a>CFrameWnd::SetMenuBarState  
 Legt den Anzeigezustand des Menüs in der aktuellen MFC-Anwendung, ausgeblendet oder angezeigt.  
  
```  
virtual BOOL SetMenuBarState(DWORD nState);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `nState`|Gibt an, ob das Menü anzeigen oder ausblenden. Die `nState` Parameter kann die folgenden Werte aufweisen:<br /><br /> -AFX_MBS_VISIBLE (0 x&01;) – zeigt das Menü an, wenn es ausgeblendet ist, aber hat keine Auswirkung, wenn es angezeigt wird.<br />-AFX_MBS_HIDDEN (0 x&02;) – Blendet das Menü sichtbar ist, jedoch hat keine Auswirkung, wenn es ausgeblendet ist.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn diese Methode erfolgreich Menü; Zustandsänderungen andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein Laufzeitfehler auftritt, wird diese Methode Assertionen im Debugmodus und löst eine Ausnahme, die von abgeleiteten der [CException](../../mfc/reference/cexception-class.md) Klasse.  
  
##  <a name="setmenubarvisibility"></a>CFrameWnd::SetMenuBarVisibility  
 Legt das Standardverhalten des Menüs in der aktuellen MFC-Anwendung entweder ausgeblendet oder sichtbar sein.  
  
```  
virtual void SetMenuBarVisibility(DWORD nStyle);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `nStyle`|Gibt an, ob im Menü standardmäßig ausgeblendet ist oder sichtbar ist und den Fokus besitzt. Die `nStyle` Parameter kann die folgenden Werte aufweisen:<br /><br /> -AFX_MBV_KEEPVISIBLE (0 X&01;)-<br />     Das Menü wird immer angezeigt, und in der Standardeinstellung verfügt nicht über den Fokus.<br />-AFX_MBV_DISPLAYONFOCUS (0 X&02;)-<br />     Klicken Sie im Menü ist standardmäßig ausgeblendet. Wenn Sie im Menü angezeigt wird, drücken Sie ALT, um das Menü anzuzeigen, und geben Sie ihm den Fokus. Wenn Sie im Menü angezeigt wird, drücken Sie ALT oder ESC Menü ausblenden.<br />-AFX_MBV_ DISPLAYONFOCUS (0 X&02;) | AFX_MBV_DISPLAYONF10 (0 X&04;)<br />     (bitweise Kombination (OR)) – klicken Sie im Menü standardmäßig ausgeblendet ist. Wenn Sie im Menü angezeigt wird, drücken Sie F10, um das Menü anzuzeigen, und geben Sie ihm den Fokus. Wenn Sie im Menü angezeigt wird, drücken Sie F10, um den Fokus auf oder aus dem Menü zu wechseln. Das Menü wird angezeigt, bis Sie die ALT-Taste oder die ESC-Taste drücken, um es ausblenden.|  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Wert der `nStyle` -Parameter ist ungültig, im Debugmodus befindet und löst diese Methode bestätigt [CInvalidArgException](../../mfc/reference/cinvalidargexception-class.md) im Releasemodus. Bei anderen Fehlern Common Language Runtime diese Methode im Debugmodus bestätigt und löst eine Ausnahme, die von abgeleiteten der [CException](../../mfc/reference/cexception-class.md) Klasse.  
  
 Diese Methode beeinflusst den Zustand des Menüs in Anwendungen für [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] und höher.  
  
##  <a name="setmessagetext"></a>CFrameWnd::SetMessageText  
 Rufen Sie diese Funktion, um eine Zeichenfolge in der Statusleiste mit der ID 0 zu platzieren.  
  
```  
void SetMessageText(LPCTSTR lpszText);  
void SetMessageText(UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszText`  
 Verweist auf die Zeichenfolge, die auf der Statusleiste platziert werden.  
  
 `nID`  
 String-Ressourcen-ID der Zeichenfolge in der Statusleiste platziert werden.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist normalerweise der Bereich ganz links und am längsten, der Statusleiste.  
  
##  <a name="setprogressbarposition"></a>CFrameWnd::SetProgressBarPosition  
 Legt die aktuelle Position für die Windows 7-Statusanzeige auf der Taskleiste angezeigt.  
  
```  
void SetProgressBarPosition(int nProgressPos);
```  
  
### <a name="parameters"></a>Parameter  
 `nProgressPos`  
 Gibt die Position fest. Es muss sich innerhalb des Bereichs festlegen, indem Sie `SetProgressBarRange`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setprogressbarrange"></a>CFrameWnd::SetProgressBarRange  
 Legt den Bereich für die Windows 7-Statusanzeige auf der Taskleiste angezeigt.  
  
```  
void SetProgressBarRange(
    int nRangeMin,  
    int nRangeMax);
```  
  
### <a name="parameters"></a>Parameter  
 `nRangeMin`  
 Minimaler Wert.  
  
 `nRangeMax`  
 Maximaler Wert.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setprogressbarstate"></a>CFrameWnd::SetProgressBarState  
 Legt fest, Typ und Status der Statusanzeige auf die Taskleistenschaltfläche angezeigt.  
  
```  
void SetProgressBarState(TBPFLAG tbpFlags);
```  
  
### <a name="parameters"></a>Parameter  
 `tbpFlags`  
 Flags, die den aktuellen Zustand der Schaltfläche des Vorgangs zu steuern. Geben Sie nur eine der folgenden flags, da alle Zustände gegenseitig: TBPF_NOPROGRESS, TBPF_INDETERMINATE, TBPF_NORMAL, TBPF_ERROR, TBPF_PAUSED.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="settaskbaroverlayicon"></a>CFrameWnd::SetTaskbarOverlayIcon  
 Überladen. Bezieht sich auf die Taskleistenschaltfläche Anwendungsstatus oder zur Benachrichtigung des Benutzers eine Überlagerung.  
  
```  
BOOL SetTaskbarOverlayIcon(
    UINT nIDResource,  
    LPCTSTR lpcszDescr);

 
BOOL SetTaskbarOverlayIcon(
    HICON hIcon,  
    LPCTSTR lpcszDescr);
```  
  
### <a name="parameters"></a>Parameter  
 `nIDResource`  
 Gibt die Ressourcen-ID eines Symbols, das als die Überlagerung verwendet. Finden Sie in Beschreibung `hIcon` Details.  
  
 `lpcszDescr`  
 Ein Zeiger auf eine Zeichenfolge, die eine Alt-Text-Version von der Informationen, durch die Überlagerung Zugriff bietet.  
  
 `hIcon`  
 Der Handle für ein Symbol, um die Überlagerung verwenden. Dies sollte ein kleines Symbol, 16 x 16 Pixel bei 96 dpi (Dots per Inch) gemessen. Wenn ein Überlagerungssymbol bereits auf die Taskleistenschaltfläche angewendet wird, wird diese vorhandene Überlagerung ersetzt. Dieser Wert kann `NULL` sein. Wie ein `NULL` Wert erfolgt abhängig, ob die Taskleistenschaltfläche für ein einzelnes Fenster oder eine Gruppe von Windows darstellt. Es liegt in der Verantwortung der aufrufenden Anwendung freizugeben `hIcon` Wenn es nicht mehr benötigt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Bei Erfolg; `FALSE` ist Version des Betriebssystems kleiner als Windows 7 oder wenn ein Fehler auftritt, wenn das Symbol.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="settitle"></a>CFrameWnd::SetTitle  
 Legt den Titel des Window-Objekts fest.  
  
```  
void SetTitle(LPCTSTR lpszTitle);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszTitle`  
 Ein Zeiger auf eine Zeichenfolge mit dem Titel des Window-Objekts.  
  
##  <a name="showcontrolbar"></a>CFrameWnd::ShowControlBar  
 Rufen Sie diese Memberfunktion zum ein- oder Ausblenden der Steuerleiste.  
  
```  
void ShowControlBar(
    CControlBar* pBar,  
    BOOL bShow,  
    BOOL bDelay);
```  
  
### <a name="parameters"></a>Parameter  
 `pBar`  
 Zeiger auf der Steuerleiste angezeigt oder ausgeblendet werden.  
  
 `bShow`  
 Wenn **TRUE**, gibt an, dass die Steuerleiste angezeigt werden. Wenn **FALSE**, gibt an, dass die Symbolleiste ausgeblendet werden.  
  
 *bDelay*  
 Wenn **TRUE**, verzögert die Steuerleiste angezeigt. Wenn **FALSE**, die Steuerleiste sofort anzeigen.  
  
##  <a name="showownedwindows"></a>CFrameWnd::ShowOwnedWindows  
 Rufen Sie diese Memberfunktion, um alle Fenster anzuzeigen, die Nachfolger der `CFrameWnd` Objekt.  
  
```  
void ShowOwnedWindows(BOOL bShow);
```  
  
### <a name="parameters"></a>Parameter  
 `bShow`  
 Gibt an, ob die zugehörige Fenster angezeigt oder ausgeblendet werden.  
  
## <a name="see-also"></a>Siehe auch  
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [CMDIFrameWnd-Klasse](../../mfc/reference/cmdiframewnd-class.md)   
 [CMDIChildWnd-Klasse](../../mfc/reference/cmdichildwnd-class.md)   
 [CView-Klasse](../../mfc/reference/cview-class.md)   
 [CDocTemplate-Klasse](../../mfc/reference/cdoctemplate-class.md)   
 [CRuntimeClass-Struktur](../../mfc/reference/cruntimeclass-structure.md)


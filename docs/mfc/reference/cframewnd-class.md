---
title: CFrameWnd-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CFrameWnd [MFC], CFrameWnd
- CFrameWnd [MFC], ActivateFrame
- CFrameWnd [MFC], BeginModalState
- CFrameWnd [MFC], Create
- CFrameWnd [MFC], CreateView
- CFrameWnd [MFC], DockControlBar
- CFrameWnd [MFC], EnableDocking
- CFrameWnd [MFC], EndModalState
- CFrameWnd [MFC], FloatControlBar
- CFrameWnd [MFC], GetActiveDocument
- CFrameWnd [MFC], GetActiveFrame
- CFrameWnd [MFC], GetActiveView
- CFrameWnd [MFC], GetControlBar
- CFrameWnd [MFC], GetDockState
- CFrameWnd [MFC], GetMenuBarState
- CFrameWnd [MFC], GetMenuBarVisibility
- CFrameWnd [MFC], GetMessageBar
- CFrameWnd [MFC], GetMessageString
- CFrameWnd [MFC], GetTitle
- CFrameWnd [MFC], InitialUpdateFrame
- CFrameWnd [MFC], InModalState
- CFrameWnd [MFC], IsTracking
- CFrameWnd [MFC], LoadAccelTable
- CFrameWnd [MFC], LoadBarState
- CFrameWnd [MFC], LoadFrame
- CFrameWnd [MFC], NegotiateBorderSpace
- CFrameWnd [MFC], OnBarCheck
- CFrameWnd [MFC], OnContextHelp
- CFrameWnd [MFC], OnSetPreviewMode
- CFrameWnd [MFC], OnUpdateControlBarMenu
- CFrameWnd [MFC], RecalcLayout
- CFrameWnd [MFC], SaveBarState
- CFrameWnd [MFC], SetActivePreviewView
- CFrameWnd [MFC], SetActiveView
- CFrameWnd [MFC], SetDockState
- CFrameWnd [MFC], SetMenuBarState
- CFrameWnd [MFC], SetMenuBarVisibility
- CFrameWnd [MFC], SetMessageText
- CFrameWnd [MFC], SetProgressBarPosition
- CFrameWnd [MFC], SetProgressBarRange
- CFrameWnd [MFC], SetProgressBarState
- CFrameWnd [MFC], SetTaskbarOverlayIcon
- CFrameWnd [MFC], SetTitle
- CFrameWnd [MFC], ShowControlBar
- CFrameWnd [MFC], ShowOwnedWindows
- CFrameWnd [MFC], OnCreateClient
- CFrameWnd [MFC], OnHideMenuBar
- CFrameWnd [MFC], OnShowMenuBar
- CFrameWnd [MFC], m_bAutoMenuEnable
- CFrameWnd [MFC], rectDefault
ms.assetid: e2220aba-5bf4-4002-b960-fbcafcad01f1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 35a3fb35115e1fd86a2ccf168e048a697a17dc01
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="cframewnd-class"></a>CFrameWnd-Klasse
Stellt die Funktionalität eines Windows-SDI-Rahmenfensters (Single Document Interface) bereit, wobei es sich um ein überlappendes oder ein Popupfenster handeln kann. Ebenfalls bereitgestellt werden Member zum Verwalten des Fensters.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CFrameWnd : public CWnd  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFrameWnd::CFrameWnd](#cframewnd)|Erstellt ein `CFrameWnd`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFrameWnd::ActivateFrame](#activateframe)|Macht den Frame sichtbar und verfügbar für dem Benutzer.|  
|[CFrameWnd::BeginModalState](#beginmodalstate)|Legt das Rahmenfenster auf modale fest.|  
|[CFrameWnd::Create](#create)|Aufruf von erstellen und initialisieren Sie das zugeordnete Windows-Rahmenfenster der `CFrameWnd` Objekt.|  
|[CFrameWnd::CreateView](#createview)|Erstellt eine Ansicht in einem Frame, die nicht von abgeleitet ist `CView`.|  
|[CFrameWnd:: DockControlBar](#dockcontrolbar)|Wird eine Steuerleiste angedockt.|  
|[EnableDocking](#enabledocking)|Ermöglicht eine Steuerleiste angedockt werden.|  
|[CFrameWnd::EndModalState](#endmodalstate)|Beendet das Rahmenfenster modalen Zustand. Ermöglicht allen Fenstern deaktiviert `BeginModalState`.|  
|[CFrameWnd::FloatControlBar](#floatcontrolbar)|: Eine Steuerleiste verschiebt.|  
|[CFrameWnd::GetActiveDocument](#getactivedocument)|Gibt den aktiven **CDocument** Objekt.|  
|[CFrameWnd::GetActiveFrame](#getactiveframe)|Gibt den aktiven `CFrameWnd` Objekt.|  
|[CFrameWnd::GetActiveView](#getactiveview)|Gibt den aktiven `CView` Objekt.|  
|[CFrameWnd::GetControlBar](#getcontrolbar)|Ruft die Steuerleiste ab.|  
|[CFrameWnd::GetDockState](#getdockstate)|Ruft den Zustand Andocken Rand eines Rahmenfensters.|  
|[CFrameWnd::GetMenuBarState](#getmenubarstate)|Ruft den Anzeigezustand des Menüs in der aktuellen MFC-Anwendung ab.|  
|[CFrameWnd::GetMenuBarVisibility](#getmenubarvisibility)|Gibt an, ob das Standardverhalten des Menüs in der aktuellen MFC-Anwendung entweder ausgeblendet oder sichtbar ist.|  
|[CFrameWnd::GetMessageBar](#getmessagebar)|Gibt einen Zeiger auf der Statusleiste angezeigt, die zum Rahmenfenster gehören.|  
|[CFrameWnd::GetMessageString](#getmessagestring)|Ruft die Befehls-ID für eine entsprechende Meldung ab|  
|[CFrameWnd::GetTitle](#gettitle)|Ruft den Titel der zugehörigen Steuerleiste ab.|  
|[CFrameWnd::InitialUpdateFrame](#initialupdateframe)|Bewirkt, dass die `OnInitialUpdate` Memberfunktion, die auf alle Sichten im Rahmenfenster aufgerufen werden, gehören.|  
|[CFrameWnd::InModalState](#inmodalstate)|Gibt einen Wert, der angibt, ob ein Framefenster in einen modalen Zustand befindet oder nicht.|  
|[CFrameWnd::IsTracking](#istracking)|Bestimmt, ob die Teilerleiste gerade verschoben wird.|  
|[CFrameWnd::LoadAccelTable](#loadacceltable)|Rufen Sie zum Laden einer Zugriffstastentabelle.|  
|[CFrameWnd:: LoadBarState](#loadbarstate)|Rufen Sie zum Wiederherstellen der Steuerleiste.|  
|[CFrameWnd::LoadFrame](#loadframe)|Rufen Sie auf, um ein Framefenster von Ressourceninformationen dynamisch zu erstellen.|  
|[CFrameWnd::NegotiateBorderSpace](#negotiateborderspace)|Verhandelt Rahmen Speicherplatz im Rahmenfenster.|  
|[CFrameWnd::OnBarCheck](#onbarcheck)|Aufgerufen, wenn eine Aktion für die angegebene Steuerleiste ausgeführt wird.|  
|[CFrameWnd::OnContextHelp](#oncontexthelp)|UMSCHALT + F1-Hilfe für direkte Elemente verarbeitet werden.|  
|[CFrameWnd::OnSetPreviewMode](#onsetpreviewmode)|Legt Hauptrahmenfenster für die Anwendung, in und aus der Seitenansicht Modus.|  
|[CFrameWnd::OnUpdateControlBarMenu](#onupdatecontrolbarmenu)|Wird vom Framework aufgerufen, wenn das zugehörige Menü aktualisiert wird.|  
|[CFrameWnd::RecalcLayout](#recalclayout)|Positioniert die Steuerleisten von der `CFrameWnd` Objekt.|  
|[SaveBarState](#savebarstate)|Rufen Sie zum Speichern der Steuerleiste.|  
|[CFrameWnd::SetActivePreviewView](#setactivepreviewview)|Kennzeichnet die angegebene Ansicht die aktive Ansicht for Rich Preview sein.|  
|[CFrameWnd::SetActiveView](#setactiveview)|Legt die aktive `CView` Objekt.|  
|[CFrameWnd::SetDockState](#setdockstate)|Rufen Sie das Rahmenfenster im Hauptfenster angedockt.|  
|[CFrameWnd::SetMenuBarState](#setmenubarstate)|Legt den Anzeigezustand des Menüs in der aktuellen MFC-Anwendung, die ausgeblendet oder angezeigt.|  
|[CFrameWnd::SetMenuBarVisibility](#setmenubarvisibility)|Legt das Standardverhalten des Menüs in der aktuellen MFC-Anwendung entweder ausgeblendet oder sichtbar sein.|  
|[CFrameWnd::SetMessageText](#setmessagetext)|Legt den Text des eine Standardstatusleiste fest.|  
|[CFrameWnd::SetProgressBarPosition](#setprogressbarposition)|Legt die aktuelle Position für Windows 7-Statusanzeige auf der Taskleiste angezeigt.|  
|[CFrameWnd::SetProgressBarRange](#setprogressbarrange)|Legt fest, Bereich für Windows 7-Statusanzeige auf der Taskleiste angezeigt.|  
|[CFrameWnd::SetProgressBarState](#setprogressbarstate)|Legt fest, Typ und Status der Statusanzeige auf eine Schaltfläche der Taskleiste angezeigt.|  
|[CFrameWnd::SetTaskbarOverlayIcon](#settaskbaroverlayicon)|Überladen. Taskleistenschaltfläche Anwendungsstatus oder eine Benachrichtigung an den Benutzer an gilt eine Überlagerung.|  
|[CFrameWnd::SetTitle](#settitle)|Legt den Titel der zugehörigen Steuerleiste fest.|  
|[CFrameWnd::ShowControlBar](#showcontrolbar)|Rufen Sie zum Anzeigen der Steuerleiste.|  
|[CFrameWnd::ShowOwnedWindows](#showownedwindows)|Zeigt alle Fenster, die Nachfolger der `CFrameWnd` Objekt.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFrameWnd::OnCreateClient](#oncreateclient)|Erstellt ein Clientfenster für den Frame.|  
|[CFrameWnd::OnHideMenuBar](#onhidemenubar)|Wird aufgerufen, bevor Sie in der aktuellen MFC-Anwendung im Menü ausgeblendet ist.|  
|[CFrameWnd::OnShowMenuBar](#onshowmenubar)|Wird aufgerufen, bevor Sie in der aktuellen MFC-Anwendung im Menü angezeigt wird.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFrameWnd::m_bAutoMenuEnable](#m_bautomenuenable)|Steuerelemente, die automatische Aktivieren und Deaktivieren von Funktionen für Menüelemente.|  
|[CFrameWnd::rectDefault](#rectdefault)|Übergeben Sie das statische `CRect` als Parameter beim Erstellen einer `CFrameWnd` Objekt, das Zulassen von Windows auf die ursprüngliche Größe und Position des Fensters wählen.|  
  
## <a name="remarks"></a>Hinweise  
 Um eine nützliche Rahmenfenster für Ihre Anwendung zu erstellen, leiten Sie eine Klasse von `CFrameWnd`. Fügen Sie der abgeleiteten Klasse zum Speichern von Daten, die spezifisch für Ihre Anwendung Membervariablen hinzu. Implementieren Sie Meldungshandler-Memberfunktionen und eine Meldungszuordnung in der abgeleiteten Klasse, um anzugeben, was passiert, wenn Meldungen an das Fenster weitergeleitet werden.  
  
 Es gibt drei Möglichkeiten zum Erstellen eines Rahmenfensters:  
  
-   Erstellen Sie direkt mit [erstellen](#create).  
  
-   Erstellen Sie direkt mit [LoadFrame](#loadframe).  
  
-   Erstellen Sie mithilfe einer Dokumentvorlage indirekt.  
  
 Vor dem Aufruf entweder **erstellen** oder `LoadFrame`, müssen Sie das Rahmenfenster Objekt auf dem Heap mithilfe des C++ erstellen **neue** Operator. Vor dem Aufruf **erstellen**, Sie können auch eine Fensterklasse mit Registrieren der [AfxRegisterWndClass](../../mfc/reference/application-information-and-management.md#afxregisterwndclass) globale Funktion die Stile-Symbol und die Klasse für den Frame festgelegt.  
  
 Verwenden der **erstellen** Memberfunktion, die Frame-Erstellungsparameter als sofortige Argumente zu übergeben.  
  
 `LoadFrame` erfordert weniger Argumente als **erstellen**, und ruft stattdessen die meisten die Standardwerte aus Ressourcen, einschließlich der Frame Beschriftung, Symbol Zugriffstastentabelle und im Menü ab. Um zugänglich `LoadFrame`, alle diese Ressourcen müssen die gleichen Ressourcen-ID (z. B. **IDR_MAINFRAME**).  
  
 Wenn ein `CFrameWnd` Objekt enthält, Ansichten und Dokumente, die indirekt durch das Framework statt direkt vom Programmierer erstellt werden. Die `CDocTemplate` Objekt organisiert, die Erstellung des Frames, die Erstellung der enthaltenden Ansichten und die Verbindung der Ansichten dem entsprechenden Dokument. Die Parameter von der `CDocTemplate` Konstruktor angeben der `CRuntimeClass` der drei Klassen beteiligt (Dokument, Rahmen und Ansicht). Ein `CRuntimeClass` Objekt wird vom Framework verwendet, dynamisch neue Frames an, wenn vom Benutzer angegeben (z. B. mithilfe der neuen Datei Befehl oder neue Fenster mehrere Document Interface (MDI)-Befehl) erstellt.  
  
 Eine Rahmenfenster abgeleitete Klasse `CFrameWnd` muss deklariert werden, mit `DECLARE_DYNCREATE` in der Reihenfolge für die oben genannten `RUNTIME_CLASS` Mechanismus ordnungsgemäß funktioniert.  
  
 Ein `CFrameWnd` enthält standardimplementierungen, um die folgenden Funktionen von ein Hauptfenster in einer typischen Anwendung für Windows ausführen:  
  
-   Ein `CFrameWnd` Rahmenfenster der nachverfolgt eine derzeit aktive Ansicht, unabhängig von der aktiven Windows-Fenster oder den aktuellen Eingabefokus ist. Wenn das Frame erneut aktiviert wird, wird die aktive Ansicht benachrichtigt, durch Aufrufen `CView::OnActivateView`.  
  
-   Befehl Nachrichten und viele allgemeine Frame-Notification-Nachrichten, einschließlich der behandelt, indem die `OnSetFocus`, `OnHScroll`, und `OnVScroll` Funktionen `CWnd`, werden von delegiert eine `CFrameWnd` Rahmenfenster der momentan aktiven Ansicht.  
  
-   Der momentan aktiven Ansicht (oder der aktuell aktiven untergeordneten MDI-Rahmenfenster im Falle eines MDI-Rahmens) kann dazu führen, dass die Beschriftung des Rahmenfensters bestimmen. Diese Funktion kann deaktiviert werden, indem Sie durch das Deaktivieren der **FWS_ADDTOTITLE** Formatbit des Rahmenfensters.  
  
-   Ein `CFrameWnd` Rahmenfenster verwaltet die Positionierung von den Steuerleisten, Ansichten und andere untergeordnete Fenster im Clientbereich des Rahmenfensters. Ein Framefenster übernimmt außerdem die Zeit im Leerlauf zu aktualisieren, der Symbolleiste und die anderen Schaltflächen Steuerleiste. Ein `CFrameWnd` Rahmenfenster verfügt auch über die standardmäßigen Implementierungen von Befehlen für ein- und Ausschalten der Symbolleiste und der Statusleiste umschalten.  
  
-   Ein `CFrameWnd` Rahmenfenster verwaltet der Hauptmenüleiste. Wenn ein Popupmenü angezeigt wird, verwendet das Rahmenfenster der **UPDATE_COMMAND_UI** Mechanismus, um zu bestimmen, welche Menüelemente aktiviert, deaktiviert oder aktiviert werden sollte,. Wenn der Benutzer ein Menüelement auswählt, aktualisiert das Rahmenfenster die Statusleiste mit der die Meldungszeichenfolge für diesen Befehl an.  
  
-   Ein `CFrameWnd` Rahmenfenster ist eine optionale Accelerator-Tabelle, die automatisch Zugriffstasten übersetzt.  
  
-   Ein `CFrameWnd` Rahmenfenster ist eine optionale Hilfe-ID festgelegt `LoadFrame` , die für die kontextbezogene Hilfe verwendet wird. Ein Rahmenfenster ist die wichtigsten Orchestrator von halbmodaler Zustand wie z. B. Seitenansicht Modi "und" kontextbezogene Hilfe (UMSCHALT + F1).  
  
-   Ein `CFrameWnd` Rahmenfenster öffnet eine Datei aus dem Datei-Manager gezogen und auf das Rahmenfenster gelöscht. Wenn eine Erweiterung registriert und mit der Anwendung verknüpft wird, antwortet das Rahmenfenster auf die open dynamische Daten Datenaustausch (DDE)-Anforderung, das auftritt, wenn der Benutzer eine Datei im Datei-Manager öffnet oder wenn die **ShellExecute** Windows-Funktion wird aufgerufen.  
  
-   Wenn das Rahmenfenster Hauptfenster der Anwendung ist (d. h. `CWinThread::m_pMainWnd`), wenn der Benutzer die Anwendung geschlossen wird das Rahmenfenster fordert den Benutzer auf alle geänderten Dokumente speichern (für `OnClose` und `OnQueryEndSession`).  
  
-   Das Rahmenfenster ist Hauptfenster der Anwendung, das Rahmenfenster der Kontext für die Ausführung von WinHelp. Schließen das Rahmenfenster WINHELP heruntergefahren wird. EXE, wenn sie Hilfe für diese Anwendung gestartet wurde.  
  
 Verwenden Sie nicht den C++ **löschen** Operator, um ein Framefenster zu zerstören. Verwenden Sie stattdessen `CWnd::DestroyWindow`. Die `CFrameWnd` Implementierung der `PostNcDestroy` der C++-Objekt wird gelöscht, wenn das Fenster zerstört wird. Wenn der Benutzer das Rahmenfenster der Standardeinstellung schließt `OnClose` Handler ruft `DestroyWindow`.  
  
 Weitere Informationen zu `CFrameWnd`, finden Sie unter [Rahmenfenster](../../mfc/frame-windows.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CFrameWnd`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="activateframe"></a>  CFrameWnd::ActivateFrame  
 Rufen Sie diese Memberfunktion zum Aktivieren und das Rahmenfenster wiederhergestellt werden, dass es für den Benutzer sichtbar und verfügbar ist.  
  
```  
virtual void ActivateFrame(int nCmdShow = -1);
```  
  
### <a name="parameters"></a>Parameter  
 `nCmdShow`  
 Gibt den Parameter an übergeben [ShowWindow](../../mfc/reference/cwnd-class.md#showwindow). Standardmäßig wird der Frame dargestellt und ordnungsgemäß wiederhergestellt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion heißt in der Regel nach einem Schnittstellenereignis nichtbenutzer-, z. B. eine DDE, OLE oder andere Ereignis, das das Rahmenfenster oder dessen Inhalt an dem Benutzer anzeigen kann.  
  
 Die standardmäßige Implementierung den Frame und schaltet sie am Anfang der Z-Reihenfolge und bei Bedarf führt dieselben Schritte für die Anwendung Hauptrahmenfenster.  
  
 Überschreiben Sie diese Memberfunktion zum Ändern, wie ein Frame aktiviert ist. Beispielsweise können Sie untergeordnete MDI-Fenster zu maximiert werden erzwingen. Fügen Sie der entsprechenden Funktionalität hinzu, und rufen Sie die Basisklassenversion mit einem expliziten `nCmdShow`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing#1](../../mfc/reference/codesnippet/cpp/cframewnd-class_1.cpp)]  
  
##  <a name="beginmodalstate"></a>  CFrameWnd::BeginModalState  
 Rufen Sie diese Memberfunktion auf, um ein Framefenster modal zu machen.  
  
```  
virtual void BeginModalState();
```  
  
##  <a name="cframewnd"></a>  CFrameWnd::CFrameWnd  
 Erstellt eine `CFrameWnd` -Objekt, aber nicht sichtbar Rahmenfenster erstellt.  
  
```  
CFrameWnd();
```  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie **erstellen** zum Erstellen des Fensters sichtbar.  
  
##  <a name="create"></a>  CFrameWnd::Create  
 Aufruf von erstellen und initialisieren Sie das zugeordnete Windows-Rahmenfenster der `CFrameWnd` Objekt.  
  
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
 Verweist auf eine Null-terminierte Zeichenfolge, die den Namen die Windows-Klasse. Der Klassenname kann einen beliebigen Namen registriert die `AfxRegisterWndClass` globale Funktion oder die **RegisterClass** Windows-Funktion. Wenn **NULL**, verwendet die vordefinierten Standardwerte `CFrameWnd` Attribute.  
  
 `lpszWindowName`  
 Verweist auf eine Null-terminierte Zeichenfolge, die den Fensternamen darstellt. Als Text verwendet der Titelleiste.  
  
 `dwStyle`  
 Gibt das Zeitfenster [Stil](../../mfc/reference/styles-used-by-mfc.md#window-styles) Attribute. Enthalten die **FWS_ADDTOTITLE** Format zuzuweisen, wenn die Titelleiste automatisch der Name des Dokuments dargestellt, die im Fenster angezeigt werden soll.  
  
 `rect`  
 Gibt die Größe und Position des Fensters. Die `rectDefault` Wert ermöglicht es Windows, um die Größe und Position des neuen Fensters festzulegen.  
  
 `pParentWnd`  
 Gibt das übergeordnete Fenster eines dieses Rahmenfenster. Dieser Parameter muss **NULL** für Rahmenfenster der obersten Ebene.  
  
 *lpszMenuName*  
 Identifiziert den Namen der Menüressource im mit Fenster verwendet werden soll. Verwendung **MAKEINTRESOURCE** verfügt im Menü eine ganzzahlige ID anstelle einer Zeichenfolge. Dieser Parameter kann **NULL**.  
  
 `dwExStyle`  
 Gibt an, das Fenster Erweitert [Stil](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles) Attribute.  
  
 `pContext`  
 Gibt einen Zeiger auf eine [angegeben ist und](../../mfc/reference/ccreatecontext-structure.md) Struktur. Dieser Parameter kann **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Initialisierung erfolgreich ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Erstellen einer `CFrameWnd` Objekt in zwei Schritten. Rufen Sie zuerst den Konstruktor, der erstellt die `CFrameWnd` Objekt, und rufen Sie anschließend **erstellen**, das erstellt des Windows-Rahmenfensters und fügt es der `CFrameWnd` Objekt. **Erstellen Sie** Klassennamen und entweder ist der Name des Fensters initialisiert und Standardwerte für seine, übergeordnete und die zugeordneten registriert.  
  
 Verwendung `LoadFrame` statt **erstellen** aus einer Ressource, die Argumente angeben, statt das Rahmenfenster geladen.  
  
##  <a name="createview"></a>  CFrameWnd::CreateView  
 Rufen Sie `CreateView` zum Erstellen einer Ansicht innerhalb eines Rahmens.  
  
```  
CWnd* CreateView(
    CCreateContext* pContext,  
    UINT nID = AFX_IDW_PANE_FIRST);
```  
  
### <a name="parameters"></a>Parameter  
 `pContext`  
 Gibt den Typ des Dokuments und anzeigen.  
  
 `nID`  
 Die ID-Nummer einer Sicht.  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf eine `CWnd` -Objekt, wenn erfolgreich; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Memberfunktion, die nicht zum Erstellen von "Ansichten" `CView`-abgeleitet, die innerhalb eines Rahmens. Nach dem Aufruf `CreateView`, müssen Sie manuell die Sicht auf aktiv festgelegt und legen Sie es sichtbar sein; diese Aufgaben werden nicht automatisch ausgeführten `CreateView`.  
  
##  <a name="dockcontrolbar"></a>  CFrameWnd:: DockControlBar  
 Bewirkt, dass eine Steuerleiste, die an das Rahmenfenster angedockt werden.  
  
```  
void DockControlBar(
    CControlBar* pBar,  
    UINT nDockBarID = 0,  
    LPCRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `pBar`  
 Verweist auf die Steuerleiste angedockt werden.  
  
 `nDockBarID`  
 Bestimmt, welche Seiten des Rahmenfensters Andocken berücksichtigen. Sie können 0 (null) oder mindestens eine der folgenden sein:  
  
- `AFX_IDW_DOCKBAR_TOP` Docken Sie an, am oberen Rand des Rahmenfensters.  
  
- **AFX_IDW_DOCKBAR_BOTTOM** Andocken an die Unterseite des Rahmenfensters.  
  
- `AFX_IDW_DOCKBAR_LEFT` Andocken von der linken Seite des Rahmenfensters.  
  
- `AFX_IDW_DOCKBAR_RIGHT` Andocken von der rechten Seite des Rahmenfensters.  
  
 Bei 0, kann eine Seite zum Andocken in das Ziel-Rahmenfenster aktiviert Steuerleiste angedockt werden.  
  
 `lpRect`  
 Bestimmt, in Bildschirmkoordinaten, die in den Clientbereich des Rahmenfensters Ziel, in dem die Steuerleiste angedockt wird.  
  
### <a name="remarks"></a>Hinweise  
 Steuerleiste wird auf eine der Seiten des Rahmenfensters angegeben, die in den Aufrufen für beide angedockt werden [CControlBar:: EnableDocking](../../mfc/reference/ccontrolbar-class.md#enabledocking) und [EnableDocking](#enabledocking). Die ausgewählte Seite richtet sich nach `nDockBarID`.  
  
##  <a name="enabledocking"></a>  EnableDocking  
 Mit dieser Funktion können andockbaren Balken in einem Rahmenfenster zu aktivieren.  
  
```  
void EnableDocking(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>Parameter  
 `dwDockStyle`  
 Gibt an, welche Seiten des Rahmenfensters als Andocken von Websites für Steuerleisten dienen können. Es kann eine oder mehrere der folgenden sein:  
  
- `CBRS_ALIGN_TOP` Ermöglicht das Andocken am oberen Rand des Clientbereichs.  
  
- `CBRS_ALIGN_BOTTOM` Ermöglicht das Andocken am unteren Rand des Clientbereichs.  
  
- `CBRS_ALIGN_LEFT` Ermöglicht das Andocken auf der linken Seite des Clientbereichs.  
  
- `CBRS_ALIGN_RIGHT` Ermöglicht das Andocken auf der rechten Seite des Clientbereichs.  
  
- `CBRS_ALIGN_ANY` Ermöglicht das Andocken auf jeder Seite des Clientbereichs.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig werden Schiebeleisten-Steuerelemente auf einer Seite des Rahmenfensters in der folgenden Reihenfolge angedockt werden: oben, unten, links, rechts.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [Symbolleistenformate](../../mfc/reference/ctoolbar-class.md#create).  
  
##  <a name="endmodalstate"></a>  CFrameWnd::EndModalState  
 Rufen Sie diese Memberfunktion auf, um ein Framefenster von einem modalen in einen Status ohne Modus zu ändern.  
  
```  
virtual void EndModalState();
```  
  
### <a name="remarks"></a>Hinweise  
 `EndModalState` ermöglicht allen Fenstern deaktiviert [BeginModalState](#beginmodalstate).  
  
##  <a name="floatcontrolbar"></a>  CFrameWnd::FloatControlBar  
 Mit dieser Funktion können dazu führen, dass eine Steuerleiste, die nicht an das Rahmenfenster angedockt werden.  
  
```  
void FloatControlBar(
    CControlBar* pBar,  
    CPoint point,  
    DWORD dwStyle = CBRS_ALIGN_TOP);
```  
  
### <a name="parameters"></a>Parameter  
 `pBar`  
 Verweist auf die Steuerleiste umfließt sein.  
  
 `point`  
 Der Speicherort, in Bildschirmkoordinaten, in der oberen linken Ecke der Steuerleiste platziert werden.  
  
 `dwStyle`  
 Gibt an, ob die Steuerleiste in das neue Rahmenfenster horizontal oder vertikal ausgerichtet werden soll. Es kann einer der folgenden sein:  
  
- `CBRS_ALIGN_TOP` Steuerleiste vertikal ausgerichtet.  
  
- `CBRS_ALIGN_BOTTOM` Steuerleiste vertikal ausgerichtet.  
  
- `CBRS_ALIGN_LEFT` Steuerleiste horizontal ausgerichtet.  
  
- `CBRS_ALIGN_RIGHT` Steuerleiste horizontal ausgerichtet.  
  
 Wenn Stilen horizontale und vertikale Ausrichtung angeben übergeben werden, wird die Symbolleiste horizontal ausgerichtet sein.  
  
### <a name="remarks"></a>Hinweise  
 In der Regel wird dies beim Start der Anwendung durchgeführt, wenn das Programm Einstellungen aus der vorherigen Ausführung wiederhergestellt wird.  
  
 Diese Funktion wird vom Framework aufgerufen, wenn der Benutzer führt dazu, dass es sich bei einer Drop-Vorgangs durch den linken loslassen beim Ziehen die Steuerleiste über einen Speicherort, der für die Zuordnung nicht verfügbar ist.  
  
##  <a name="getactivedocument"></a>  CFrameWnd::GetActiveDocument  
 Rufen Sie diese Memberfunktion, um einen Zeiger auf den aktuellen erhalten **CDocument** angefügt, die zurzeit aktive Sicht.  
  
```  
virtual CDocument* GetActiveDocument();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die aktuelle [CDocument](../../mfc/reference/cdocument-class.md). Wenn keine aktuelle Dokument vorhanden ist, gibt **NULL**.  
  
##  <a name="getactiveframe"></a>  CFrameWnd::GetActiveFrame  
 Rufen Sie diese Memberfunktion, um einem Zeiger auf den aktiven Fensters multiple Document Interface (MDI) untergeordnetes Element von einem MDI-Rahmenfenster abzurufen.  
  
```  
virtual CFrameWnd* GetActiveFrame();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das aktive untergeordnete MDI-Fenster. Wenn die Anwendung eine SDI-Anwendung ist, oder der MDI-Rahmenfenster kein aktives Dokument, das die implizite hat **dies** Zeiger zurückgegeben werden.  
  
### <a name="remarks"></a>Hinweise  
 Wenn keine aktive untergeordnete MDI-Element oder die Anwendung eine Einzeldokumentoberfläche (SDI), die implizite ist **dies** Zeiger zurückgegeben.  
  
##  <a name="getactiveview"></a>  CFrameWnd::GetActiveView  
 Rufen Sie diese Memberfunktion, um einen Zeiger auf die aktive Ansicht (sofern vorhanden) an einem Rahmenfenster angefügt ( `CFrameWnd`).  
  
```  
CView* GetActiveView() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die aktuelle [CView](../../mfc/reference/cview-class.md). Wenn keine aktuelle Ansicht vorhanden ist, gibt **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion gibt **NULL** beim Aufruf für eine MDI-Hauptrahmenfenster ( `CMDIFrameWnd`). In einer MDI-Anwendung verfügt der MDI-Hauptrahmenfenster keine Sicht zugeordnet. Stattdessen jedes einzelnen untergeordneten Fenster ( `CMDIChildWnd`) verfügt über eine oder mehrere zugeordnete Ansichten. Die aktive Ansicht in einer MDI-Anwendung kann abgerufen werden, indem zuerst das aktive untergeordnete MDI-Fenster Suchen und klicken Sie dann die aktive Ansicht für diese untergeordnete Fenster suchen. Das aktive untergeordnete MDI-Fenster verwendbaren durch Aufrufen der Funktion `MDIGetActive` oder **GetActiveFrame** wie im folgenden gezeigt:  
  
 [!code-cpp[NVC_MFCWindowing#2](../../mfc/reference/codesnippet/cpp/cframewnd-class_2.cpp)]  
  
##  <a name="getcontrolbar"></a>  CFrameWnd::GetControlBar  
 Rufen Sie `GetControlBar` für den Zugriff auf die Steuerleiste, die mit der ID verknüpft ist  
  
```  
CControlBar* GetControlBar(UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 `nID`  
 Die ID einer Steuerleiste.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die Steuerleiste, die mit der ID verknüpft ist  
  
### <a name="remarks"></a>Hinweise  
 Die `nID` Parameter verweist auf den eindeutigen Bezeichner übergeben, um die **erstellen** Methode der Steuerleiste. Weitere Informationen zu Steuerleisten, finden Sie im Thema [Steuerleisten](../../mfc/control-bars.md).  
  
 `GetControlBar` Gibt die Steuerleiste zurück, auch wenn es unverankert ist und daher befindet sich derzeit kein untergeordnetes Fenster von Frames.  
  
##  <a name="getdockstate"></a>  CFrameWnd::GetDockState  
 Rufen Sie diese Memberfunktion zum Speichern von Zustandsinformationen über das Rahmenfenster Steuerleisten in einem `CDockState` Objekt.  
  
```  
void GetDockState(CDockState& state) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `state`  
 Enthält den aktuellen Status von Steuerleisten bei der Rückgabe das Rahmenfenster.  
  
### <a name="remarks"></a>Hinweise  
 Anschließend können Sie den Inhalt der schreiben `CDockState` -Speicher mithilfe `CDockState::SaveState` oder `Serialize`. Wenn Sie später die Steuerleisten in einem vorherigen Zustand wiederherstellen möchten, laden Sie den Status mit `CDockState::LoadState` oder `Serialize`, rufen Sie anschließend `SetDockState` auf den vorherigen Zustand für das Rahmenfenster Steuerleisten gelten.  
  
##  <a name="getmenubarstate"></a>  CFrameWnd::GetMenuBarState  
 Ruft den Anzeigezustand des Menüs in der aktuellen MFC-Anwendung ab.  
  
```  
virtual DWORD GetMenuBarState();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Rückgabewert kann die folgenden Werte aufweisen:  
  
-   AFX_MBS_VISIBLE (0 x 01) – klicken Sie im Menü wird angezeigt.  
  
-   AFX_MBS_HIDDEN (0 x 02) - Menü ausgeblendet ist.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein Laufzeitfehler auftritt, wird diese Methode Assertionen im Debugmodus befindet und löst eine Ausnahme abgeleitet wurde. die [CException](../../mfc/reference/cexception-class.md) Klasse.  
  
##  <a name="getmenubarvisibility"></a>  CFrameWnd::GetMenuBarVisibility  
 Gibt an, ob der Standardzustand des in der aktuellen MFC-Anwendung im Menü ausgeblendet oder sichtbar ist.  
  
```  
virtual DWORD CFrameWnd::GetMenuBarVisibility();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt einen der folgenden Werte zurück:  
  
-   AFX_MBV_KEEPVISIBLE (0 x 01) – klicken Sie im Menü wird angezeigt, überhaupt Zeiten und vom Standardwert verfügt nicht über den Fokus.  
  
-   AFX_MBV_DISPLAYONFOCUS (0 x 02) - Menü wird standardmäßig ausgeblendet. Wenn Sie im Menü ausgeblendet ist, drücken Sie die ALT-Taste auf das Menü anzuzeigen, und geben Sie ihm den Fokus. Wenn Sie im Menü angezeigt wird, drücken Sie die ALT-Taste oder die ESC-Taste, um ihn auszublenden.  
  
-   AFX_MBV_ DISPLAYONFOCUS (0 x 02) &#124; AFX_MBV_DISPLAYONF10 (0 x 04) (bitweise Kombination (OR)) – klicken Sie im Menü wird standardmäßig ausgeblendet. Wenn Sie im Menü ausgeblendet ist, drücken Sie F10, um das Menü anzuzeigen, und geben Sie ihm den Fokus. Wenn Sie im Menü angezeigt wird, drücken Sie F10, um den Fokus aktivieren oder deaktivieren Sie im Menü zu wechseln. Klicken Sie im Menü wird angezeigt, bis Sie der ALT-Taste oder die ESC-Taste drücken, um ihn auszublenden.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein Laufzeitfehler auftritt, wird diese Methode Assertionen im Debugmodus befindet und löst eine Ausnahme abgeleitet wurde. die [CException](../../mfc/reference/cexception-class.md) Klasse.  
  
##  <a name="getmessagebar"></a>  CFrameWnd::GetMessageBar  
 Rufen Sie diese Memberfunktion zum Abrufen eines Zeigers auf der Statusleiste an.  
  
```  
virtual CWnd* GetMessageBar();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf Fenster mit der Statusleiste.  
  
##  <a name="getmessagestring"></a>  CFrameWnd::GetMessageString  
 Überschreiben Sie diese Funktion, um benutzerdefinierte Zeichenfolgen für Befehls-IDs zu gewährleisten.  
  
```  
virtual void GetMessageString(
    UINT nID,  
    CString& rMessage) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nID`  
 Ressourcen-ID der gewünschten Nachricht.  
  
 `rMessage`  
 `CString` Objekt in das die Nachricht eingefügt werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung lädt einfach angegebene Zeichenfolge `nID` aus der Ressourcendatei. Diese Funktion wird vom Framework aufgerufen, wenn die Zeichenfolge in der Statusleiste Aktualisierung benötigt.  
  
##  <a name="gettitle"></a>  CFrameWnd::GetTitle  
 Ruft den Titel des Window-Objekts ab.  
  
```  
CString GetTitle() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) Objekt, das den aktuellen Titel des Window-Objekts enthält.  
  
##  <a name="initialupdateframe"></a>  CFrameWnd::InitialUpdateFrame  
 Rufen Sie **IntitialUpdateFrame** nach dem Erstellen eines neuen Frames mit dem **erstellen**.  
  
```  
void InitialUpdateFrame(
    CDocument* pDoc,  
    BOOL bMakeVisible);
```  
  
### <a name="parameters"></a>Parameter  
 `pDoc`  
 Verweist auf das Dokument, das das Rahmenfenster zugeordnet ist. Kann **NULL**.  
  
 `bMakeVisible`  
 Wenn **"true"**, gibt an, dass Frames angezeigt werden soll. Wenn **"false"**, keine abhängigen Elemente sichtbar gemacht werden.  
  
### <a name="remarks"></a>Hinweise  
 Dies bewirkt, dass alle Ansichten in diesem Fenster Frame erhalten ihre `OnInitialUpdate` aufrufen.  
  
 Außerdem war es nicht bereits eine aktive Ansicht, die Hauptansicht des Rahmenfensters active erfolgt. Die primäre Ansicht ist eine Ansicht mit der ID untergeordneten **AFX_IDW_PANE_FIRST**. Schließlich wird das Rahmenfenster sichtbar gemacht Wenn `bMakeVisible` ungleich NULL ist. Wenn `bMakeVisible` gleich 0 ist, das gegenwärtig den Fokus und der sichtbaren Zustand des Rahmenfensters bleiben unverändert. Es ist nicht notwendig, diese Funktion aufrufen, wenn das Framework-Implementierung der neuen Datei und die Datei öffnen zu verwenden.  
  
##  <a name="inmodalstate"></a>  CFrameWnd::InModalState  
 Rufen Sie diese Memberfunktion, um festzustellen, ob ein Framefenster gebunden oder ungebunden ist.  
  
```  
BOOL InModalState() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn dies der Fall; andernfalls 0.  
  
##  <a name="istracking"></a>  CFrameWnd::IsTracking  
 Rufen Sie diese Memberfunktion, um festzustellen, ob die Teilerleiste in das Fenster derzeit verschoben wird.  
  
```  
BOOL IsTracking() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn ein Splitter-Vorgang ausgeführt wird; andernfalls 0.  
  
##  <a name="loadacceltable"></a>  CFrameWnd::LoadAccelTable  
 Rufen Sie die angegebenen Zugriffstastentabelle geladen.  
  
```  
BOOL LoadAccelTable(LPCTSTR lpszResourceName);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszResourceName`  
 Identifiziert den Namen der Zugriffstastenressource. Verwendung **MAKEINTRESOURCE** , wenn die Ressource mit einer ganzzahligen ID identifiziert wird  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Zugriffstastentabelle erfolgreich geladen wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Nur eine Tabelle kann gleichzeitig geladen werden.  
  
 Zugriffstastentabellen aus Ressourcen geladen werden automatisch freigegeben, wenn die Anwendung beendet wird.  
  
 Beim Aufrufen `LoadFrame` um das Rahmenfenster zu erstellen, lädt das Framework einer Zugriffstastentabelle zusammen mit den Ressourcen im Menü "und"-Symbol, und ein nachfolgender Aufruf von dieser Memberfunktion ist dann nicht erforderlich.  
  
##  <a name="loadbarstate"></a>  CFrameWnd:: LoadBarState  
 Mit dieser Funktion wird zum Wiederherstellen der Einstellungen der jede Steuerleiste, die im Besitz des Rahmenfensters.  
  
```  
void LoadBarState(LPCTSTR lpszProfileName);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszProfileName`  
 Der Name von einem Abschnitt in der Initialisierungsdatei (INI) oder einen Schlüssel in der Windows-Registrierung, in dem Statusinformationen gespeichert ist.  
  
### <a name="remarks"></a>Hinweise  
 Informationen, die wiederhergestellt umfassen Sichtbarkeit, horizontaler/vertikaler Ausrichtung andockzustand und Position der Steuerleiste.  
  
 Die Einstellungen, die Sie wiederherstellen möchten müssen in der Registrierung geschrieben werden, vor dem Aufruf `LoadBarState`. Schreiben Sie die Informationen in die Registrierung durch den Aufruf [CWinApp::SetRegistryKey](../../mfc/reference/cwinapp-class.md#setregistrykey). Schreiben Sie die Informationen in die INI-Datei aufrufen [SaveBarState](#savebarstate).  
  
##  <a name="loadframe"></a>  CFrameWnd::LoadFrame  
 Rufen Sie auf, um ein Framefenster von Ressourceninformationen dynamisch zu erstellen.  
  
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
 Der Frame [Stil](../../mfc/reference/styles-used-by-mfc.md#window-styles). Enthalten die **FWS_ADDTOTITLE** Format zuzuweisen, wenn die Titelleiste automatisch der Name des Dokuments dargestellt, die im Fenster angezeigt werden soll.  
  
 `pParentWnd`  
 Ein Zeiger auf den Frame übergeordneten.  
  
 `pContext`  
 Ein Zeiger auf eine [angegeben ist und](../../mfc/reference/ccreatecontext-structure.md) Struktur. Dieser Parameter kann **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Erstellen einer `CFrameWnd` Objekt in zwei Schritten. Zunächst Aufrufen den Konstruktor, der erstellt die `CFrameWnd` Objekt, und rufen Sie anschließend `LoadFrame`, dem lädt das Windows-Rahmenfenster und die zugehörigen Ressourcen und fügt die Frame-Fenster an die `CFrameWnd` Objekt. Die `nIDResource` Parameter gibt an, klicken Sie im Menü, die Zugriffstastentabelle, das Symbol und eine Zeichenfolgenressource des Titels für das Rahmenfenster.  
  
 Verwenden der **erstellen** Memberfunktion statt `LoadFrame` Wenn Sie alle Erstellungsparameter für das Rahmenfenster angeben möchten.  
  
 Das Framework ruft `LoadFrame` beim Erstellen eines Rahmenfensters mit einem Dokument Template-Objekt.  
  
 Das Framework verwendet die `pContext` Argument, um die Objekte an das Rahmenfenster, einschließlich eines beliebigen verbunden sein anzugeben enthaltenen Objekte anzeigen. Sie können festlegen, die `pContext` Argument **NULL** beim Aufruf `LoadFrame`.  
  
##  <a name="m_bautomenuenable"></a>  CFrameWnd::m_bAutoMenuEnable  
 Wenn dieses Datenelement aktiviert ist (die Standardeinstellung), Menüelemente, die keine `ON_UPDATE_COMMAND_UI` oder `ON_COMMAND` Handler werden automatisch deaktiviert, wenn der Benutzer aus einer abruft.  
  
```  
BOOL m_bAutoMenuEnable;  
```  
  
### <a name="remarks"></a>Hinweise  
 Menüelemente, die über eine `ON_COMMAND` Handler jedoch keine `ON_UPDATE_COMMAND_UI` Handler automatisch aktiviert.  
  
 Wenn dieses Datenelement festgelegt ist, sind Menüelemente automatisch auf die gleiche Weise aktiviert werden, die Schaltflächen der Symbolleiste aktiviert sind.  
  
> [!NOTE]
> `m_bAutoMenuEnable` hat keine Auswirkungen auf die Menüelemente auf oberster Ebene.  
  
 Dieses Datenelement vereinfacht die Implementierung der optionale Befehle, die basierend auf der aktuellen Auswahl und verringert den Bedarf an schreiben `ON_UPDATE_COMMAND_UI` Handler für das Aktivieren und Deaktivieren von Menüelementen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing#3](../../mfc/reference/codesnippet/cpp/cframewnd-class_3.cpp)]  
  
##  <a name="negotiateborderspace"></a>  CFrameWnd::NegotiateBorderSpace  
 Rufen Sie diese Memberfunktion zum Rahmen Speicherplatz in einem Rahmenfenster während der Aktivierung der OLE-Inplace aushandeln.  
  
```  
virtual BOOL NegotiateBorderSpace(
    UINT nBorderCmd,  
    LPRECT lpRectBorder);
```  
  
### <a name="parameters"></a>Parameter  
 *nBorderCmd*  
 Enthält die folgenden Werte aus der **Enum BorderCmd**:  
  
- **BorderGet** = 1  
  
- **BorderRequest** = 2  
  
- **BorderSet** = 3  
  
 `lpRectBorder`  
 Zeiger auf eine [RECT](../../mfc/reference/rect-structure1.md) Struktur oder ein [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt, das die Koordinaten des Rahmens angibt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion wird die **CFrameWnd** Implementierung von OLE Rahmen Speicherplatz Aushandlung.  
  
##  <a name="onbarcheck"></a>  CFrameWnd::OnBarCheck  
 Aufgerufen, wenn eine Aktion für die angegebene Steuerleiste ausgeführt wird.  
  
```  
afx_msg BOOL OnBarCheck(UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 `nID`  
 Die ID des Steuerelements Leiste angezeigt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Steuerleiste vorhanden; andernfalls 0.  
  
##  <a name="oncontexthelp"></a>  CFrameWnd::OnContextHelp  
 UMSCHALT + F1-Hilfe für direkte Elemente verarbeitet werden.  
  
```  
afx_msg void OnContextHelp();
```  
  
### <a name="remarks"></a>Hinweise  
 Um kontextbezogene Hilfe zu aktivieren, fügen Sie ein  
  
 [!code-cpp[NVC_MFCDocViewSDI#16](../../mfc/codesnippet/cpp/cframewnd-class_4.cpp)]  
  
 Anweisung, um Ihre `CFrameWnd` -Klasse meldungszuordnung und auch einen Zugriffstastentabellen-Eintrag, der in der Regel UMSCHALT + F1 sind, aktivieren Sie diese Memberfunktion hinzufügen.  
  
 Wenn Ihre Anwendung mit einem OLE-Container ist `OnContextHelp` setzt alle direkten-Elementen, die die Frame-Fensterobjekt in den Hilfemodus enthaltenen. Der Cursor geändert, um einen Pfeil und ein Fragezeichen ersetzt und der Benutzer können dann bewegen Sie den Mauszeiger und drücken Sie die linke Maustaste gedrückt, um eine (Dialogfeld), Fenster, Menüs oder Befehlsschaltfläche auszuwählen. Diese Memberfunktion Ruft die Windows-Funktion `WinHelp` mit dem Hilfekontext des Objekts, unter dem Cursor.  
  
##  <a name="oncreateclient"></a>  CFrameWnd::OnCreateClient  
 Vom Framework aufgerufen, während der Ausführung des `OnCreate`.  
  
```  
virtual BOOL OnCreateClient(
    LPCREATESTRUCT lpcs,  
    CCreateContext* pContext);
```  
  
### <a name="parameters"></a>Parameter  
 `lpcs`  
 Ein Zeiger auf ein Windows [CREATESTRUCT](../../mfc/reference/createstruct-structure.md) Struktur.  
  
 `pContext`  
 Ein Zeiger auf eine [angegeben ist und](../../mfc/reference/ccreatecontext-structure.md) Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion nicht.  
  
 Die Standardimplementierung dieser Funktion erstellt eine `CView` Objekt aus den Angaben in `pContext`, sofern dies möglich.  
  
 Überschreiben Sie diese Funktion, um die empfangenen Werte überschreiben die `CCreateContext` Objekt oder um zu ändern, wie Steuerelemente in das Hauptfenster den Clientbereich des Rahmenfensters erstellt werden. Die `CCreateContext` beschrieben Elemente, die Sie überschreiben können, sind die [angegeben ist und](../../mfc/reference/ccreatecontext-structure.md) Klasse.  
  
> [!NOTE]
>  Ersetzen Sie die empfangenen Werte nicht den `CREATESTRUCT` Struktur. Sie dienen nur zu Informationszwecken verwendet. Wenn Sie das Fenster mit der Erstkonfiguration Rechteck überschreiben möchten, z. B. überschreiben die `CWnd` Memberfunktion [PreCreateWindow](../../mfc/reference/cwnd-class.md#precreatewindow).  
  
##  <a name="onhidemenubar"></a>  CFrameWnd::OnHideMenuBar  
 Diese Funktion wird aufgerufen, wenn das System zum Ausblenden der Menüleiste in der aktuellen MFC-Anwendung.  
  
```  
virtual void OnHideMenuBar();
```  
  
### <a name="remarks"></a>Hinweise  
 Dieser Ereignishandler kann die Anwendung benutzerdefinierte Aktionen durchzuführen, wenn das System das Menü ausgeblendet wird. Sie können nicht verhindern, dass Sie im Menü ausgeblendet wird, aber andere Methoden, um das Format oder den Status abrufen können, z. B. aufrufen können.  
  
##  <a name="onsetpreviewmode"></a>  CFrameWnd::OnSetPreviewMode  
 Rufen Sie diese Memberfunktion auf, um für das Hauptrahmenfenster den Seitenansichtmodus zu aktivieren oder zu deaktivieren.  
  
```  
virtual void OnSetPreviewMode(
    BOOL bPreview,  
    CPrintPreviewState* pState);
```  
  
### <a name="parameters"></a>Parameter  
 *bPreview*  
 Gibt an, ob die Anwendung im Seitenansichtsmodus-platzieren. Legen Sie auf **"true"** , platzieren Sie in der Seitenansicht, **"false"** Vorschaumodus Abbrechen.  
  
 `pState`  
 Ein Zeiger auf eine **CPrintPreviewState** Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung deaktiviert alle Standardsymbolleisten und blendet das Hauptmenü und des hauptclientfensters. Dadurch aktiviert sich MDI-Rahmenfenster in temporären SDI-Rahmenfenster.  
  
 Überschreiben Sie diese Memberfunktion zum Anpassen der aus- und Einblenden von Steuerleisten und andere Teile der Frame-Fensters der Seitenansicht an. Rufen Sie die Implementierung der Basisklasse aus die überschriebene Version.  
  
##  <a name="onshowmenubar"></a>  CFrameWnd::OnShowMenuBar  
 Diese Funktion wird aufgerufen, wenn das System zum Anzeigen der Menüleiste in der aktuellen MFC-Anwendung.  
  
```  
virtual void OnShowMenuBar();
```  
  
### <a name="remarks"></a>Hinweise  
 Dieser Ereignishandler kann die Anwendung benutzerdefinierte Aktionen durchzuführen, wenn Sie im Menü angezeigt wird. Sie können nicht verhindern, dass Sie im Menü angezeigt werden, aber Sie können z. B. andere Methoden zum Abrufen von das Format oder der Zustand aufrufen.  
  
##  <a name="onupdatecontrolbarmenu"></a>  CFrameWnd::OnUpdateControlBarMenu  
 Wird vom Framework aufgerufen, wenn das zugehörige Menü aktualisiert wird.  
  
```  
afx_msg void OnUpdateControlBarMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>Parameter  
 `pCmdUI`  
 Ein Zeiger auf eine [CCmdUI](../../mfc/reference/ccmdui-class.md) Objekt, das das Menü, das den Updatebefehl generiert darstellt. Ruft das Update der [aktivieren](../../mfc/reference/ccmdui-class.md#enable) Memberfunktion der `CCmdUI` -Objekt über `pCmdUI` zum Aktualisieren der Benutzeroberfläche.  
  
##  <a name="recalclayout"></a>  CFrameWnd::RecalcLayout  
 Vom Framework aufgerufen, wenn die standard Steuerleisten ein- oder ausgeschaltet werden, oder beim Ändern der Größe des Rahmenfensters.  
  
```  
virtual void RecalcLayout(BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `bNotify`  
 Bestimmt, ob das aktive direkte-Element für das Rahmenfenster Benachrichtigung von der layoutänderung empfängt. Wenn **"true"**, das Element ist, andernfalls benannten **"false"**.  
  
### <a name="remarks"></a>Hinweise  
 Die Standardimplementierung von dieser Memberfunktion Ruft die `CWnd` Memberfunktion `RepositionBars` an die Steuerleisten im Frame sowie des hauptclientfensters neu positionieren (in der Regel eine `CView` oder **MDICLIENT**) .  
  
 Überschreiben Sie diese Memberfunktion, um das Aussehen und Verhalten von Steuerleisten zu steuern, nachdem das Layout des Rahmenfensters geändert wurde. Beispielsweise rufen sie beim Aktivieren oder Deaktivieren von Steuerleisten oder einem anderen Steuerleiste hinzufügen.  
  
##  <a name="rectdefault"></a>  CFrameWnd::rectDefault  
 Übergeben Sie das statische `CRect` als Parameter beim Erstellen eines Fensters, damit Windows anfänglichen Größe und Position des Fensters auswählen können.  
  
```  
static AFX_DATA const CRect rectDefault;  
```  
  
##  <a name="savebarstate"></a>  SaveBarState  
 Mit dieser Funktion wird zum Speichern von Informationen über jede Steuerleiste, die im Besitz des Rahmenfensters.  
  
```  
void SaveBarState(LPCTSTR lpszProfileName) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `lpszProfileName`  
 Name eines Abschnitts in der Initialisierungsdatei oder einen Schlüssel in der Windows-Registrierung, in dem Statusinformationen gespeichert ist.  
  
### <a name="remarks"></a>Hinweise  
 Diese Informationen kann gelesen werden, aus die Initialisierung mit [LoadBarState](#loadbarstate). Gespeicherten Informationen zählen die Sichtbarkeit, Horizontal/Vertical Ausrichtung, andocken, Status und die Position des Steuerelements angezeigt.  
  
##  <a name="setactivepreviewview"></a>  CFrameWnd::SetActivePreviewView  
 Kennzeichnet die angegebene Ansicht die aktive Ansicht for Rich Preview sein.  
  
```  
void SetActivePreviewView(CView* pViewNew);
```  
  
### <a name="parameters"></a>Parameter  
 `pViewNew`  
 Ein Zeiger auf eine Sicht aktiviert werden.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setactiveview"></a>  CFrameWnd::SetActiveView  
 Rufen Sie diese Memberfunktion, um die aktive Ansicht festzulegen.  
  
```  
void SetActiveView(
    CView* pViewNew,  
    BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 *pViewNew*  
 Gibt einen Zeiger auf eine [CView](../../mfc/reference/cview-class.md) -Objekt, oder **NULL** für keine aktive Ansicht.  
  
 `bNotify`  
 Gibt an, ob die Sicht der Aktivierung benachrichtigt werden. Wenn **"true"**, `OnActivateView` wird für die neue Sicht; aufgerufen, wenn **"false"**, es ist nicht.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Funktion automatisch als der Benutzer den Fokus auf eine Ansicht im Rahmenfenster festlegt. Sie können explizit aufrufen, `SetActiveView` so ändern Sie den Fokus auf die angegebene Ansicht.  
  
##  <a name="setdockstate"></a>  CFrameWnd::SetDockState  
 Rufen Sie diese Memberfunktion zum Anwenden von Zustandsinformationen, die in gespeicherten ein `CDockState` -Objekt, das Rahmenfenster Steuerleisten.  
  
```  
void SetDockState(const CDockState& state);
```  
  
### <a name="parameters"></a>Parameter  
 `state`  
 Wenden Sie den gespeicherten Zustand, auf das Rahmenfenster Steuerleisten.  
  
### <a name="remarks"></a>Hinweise  
 Um einen früheren Zustand der Steuerleisten wiederherzustellen, können Sie den gespeicherten Zustand mit laden `CDockState::LoadState` oder `Serialize`, verwenden Sie dann `SetDockState` , um das Rahmenfenster Steuerleisten anzuwenden. Der vorherige Status befindet sich in der `CDockState` -Objekt mit `GetDockState`  
  
##  <a name="setmenubarstate"></a>  CFrameWnd::SetMenuBarState  
 Legt den Anzeigezustand des Menüs in der aktuellen MFC-Anwendung, die ausgeblendet oder angezeigt.  
  
```  
virtual BOOL SetMenuBarState(DWORD nState);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `nState`|Gibt an, ob das Menü anzeigen oder ausblenden. Die `nState` Parameter kann die folgenden Werte aufweisen:<br /><br /> -AFX_MBS_VISIBLE (0 x 01) – zeigt das Menü an, wenn es ausgeblendet ist, aber hat keine Auswirkung, wenn es sichtbar ist.<br />-AFX_MBS_HIDDEN (0 x 02) - Blendet das Menü wird angezeigt, jedoch hat keine Auswirkung, wenn es ausgeblendet ist.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true` Wenn diese Methode erfolgreich Menü; Zustandsänderungen andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein Laufzeitfehler auftritt, wird diese Methode Assertionen im Debugmodus befindet und löst eine Ausnahme abgeleitet wurde. die [CException](../../mfc/reference/cexception-class.md) Klasse.  
  
##  <a name="setmenubarvisibility"></a>  CFrameWnd::SetMenuBarVisibility  
 Legt das Standardverhalten des Menüs in der aktuellen MFC-Anwendung entweder ausgeblendet oder sichtbar sein.  
  
```  
virtual void SetMenuBarVisibility(DWORD nStyle);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `nStyle`|Gibt an, ob im Menü standardmäßig ausgeblendet ist oder sichtbar ist und den Fokus besitzt. Die `nStyle` Parameter kann die folgenden Werte aufweisen:<br /><br /> -AFX_MBV_KEEPVISIBLE (0 X 01 –)<br />     Klicken Sie im Menü jederzeit angezeigt wird, und in der Standardeinstellung verfügt nicht über den Fokus.<br />-AFX_MBV_DISPLAYONFOCUS (0 X 02)-<br />     Klicken Sie im Menü wird standardmäßig ausgeblendet. Wenn Sie im Menü ausgeblendet ist, drücken Sie die ALT-Taste auf das Menü anzuzeigen, und geben Sie ihm den Fokus. Wenn Sie im Menü angezeigt wird, drücken Sie die ALT-Taste oder die ESC-Taste So blenden Sie im Menü aus.<br />-AFX_MBV_ DISPLAYONFOCUS (0 x 02) &#124; AFX_MBV_DISPLAYONF10 (0 x 04)<br />     (bitweise Kombination (OR)) – klicken Sie im Menü wird standardmäßig ausgeblendet. Wenn Sie im Menü ausgeblendet ist, drücken Sie F10, um das Menü anzuzeigen, und geben Sie ihm den Fokus. Wenn Sie im Menü angezeigt wird, drücken Sie F10, um den Fokus aktivieren oder deaktivieren Sie im Menü zu wechseln. Klicken Sie im Menü wird angezeigt, bis Sie der ALT-Taste oder die ESC-Taste drücken, um ihn auszublenden.|  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Wert der `nStyle` -Parameter ist ungültig, im Debugmodus befindet und löst diese Methode bestätigt [CInvalidArgException](../../mfc/reference/cinvalidargexception-class.md) im Releasemodus. Klicken Sie im Falle eines andere Laufzeitfehler diese Methode Assertionen im Debugmodus befindet, und löst eine Ausnahme abgeleitet aus dem [CException](../../mfc/reference/cexception-class.md) Klasse.  
  
 Diese Methode wirkt sich auf den Status des Menüs in Anwendungen für [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] und höher.  
  
##  <a name="setmessagetext"></a>  CFrameWnd::SetMessageText  
 Rufen Sie diese Funktion, um eine Zeichenfolge in der Statusleiste zu platzieren, der ID 0 hat.  
  
```  
void SetMessageText(LPCTSTR lpszText);  
void SetMessageText(UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszText`  
 Verweist auf die Zeichenfolge, die auf der Statusleiste platziert werden.  
  
 `nID`  
 String-Ressourcen-ID der Zeichenfolge auf der Statusleiste abgelegt werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist in der Regel im am weitesten links stehende und am längsten, der Statusleiste.  
  
##  <a name="setprogressbarposition"></a>  CFrameWnd::SetProgressBarPosition  
 Legt die aktuelle Position für die Windows 7-Statusanzeige auf der Taskleiste angezeigt.  
  
```  
void SetProgressBarPosition(int nProgressPos);
```  
  
### <a name="parameters"></a>Parameter  
 `nProgressPos`  
 Gibt die Position festgelegt. Muss er innerhalb des Bereichs festlegen, indem `SetProgressBarRange`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setprogressbarrange"></a>  CFrameWnd::SetProgressBarRange  
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
 Maximale Wert.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setprogressbarstate"></a>  CFrameWnd::SetProgressBarState  
 Legt fest, Typ und Status der Statusanzeige auf eine Schaltfläche der Taskleiste angezeigt.  
  
```  
void SetProgressBarState(TBPFLAG tbpFlags);
```  
  
### <a name="parameters"></a>Parameter  
 `tbpFlags`  
 Flags, die den aktuellen Zustand der Schaltfläche mit den Fortschritt zu steuern. Geben Sie nur eines der folgenden flags, weil alle Status gegenseitig: TBPF_NOPROGRESS, TBPF_INDETERMINATE, TBPF_NORMAL, TBPF_ERROR, TBPF_PAUSED.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="settaskbaroverlayicon"></a>  CFrameWnd::SetTaskbarOverlayIcon  
 Überladen. Taskleistenschaltfläche um Anwendungsstatus anzugeben oder um Benutzer zu benachrichtigen gilt Overlay.  
  
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
 Gibt die Ressourcen-ID eines Symbols, das als das Overlay verwendet. Finden Sie in der Beschreibung für `hIcon` Einzelheiten.  
  
 `lpcszDescr`  
 Ein Zeiger auf eine Zeichenfolge, die eine Alternativtext-Version von der Informationen, durch das Overlay, für die Barrierefreiheit bietet.  
  
 `hIcon`  
 Das Handle eines Symbols, das als das Overlay verwendet werden soll. Dabei sollte es sich um ein kleines Symbol, das Messen von 16 x 16 Pixel bei 96 dpi (Dots per Inch) handeln. Wenn ein Overlay-Symbol auf die Schaltfläche auf der Taskleiste bereits angewendet wird, wird diese vorhandenen Überlagerung ersetzt. Dieser Wert kann `NULL` sein. Wie eine `NULL` Wert erfolgt abhängig, ob die Schaltfläche auf der Taskleiste ein einziges Fenster oder eine Gruppe von Windows darstellt. Es ist Aufgabe der aufrufenden Anwendung um freizugeben `hIcon` wenn er nicht mehr benötigt.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Bei Erfolg; `FALSE` Wenn Betriebssystemversion kleiner als Windows 7 ist oder wenn ein Fehler auftritt, das Symbol "festlegen.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="settitle"></a>  CFrameWnd::SetTitle  
 Legt den Titel des Window-Objekts.  
  
```  
void SetTitle(LPCTSTR lpszTitle);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszTitle`  
 Ein Zeiger auf eine Zeichenfolge mit dem Titel des Window-Objekt.  
  
##  <a name="showcontrolbar"></a>  CFrameWnd::ShowControlBar  
 Rufen Sie diese Memberfunktion zum ein- oder Ausblenden der Steuerleiste.  
  
```  
void ShowControlBar(
    CControlBar* pBar,  
    BOOL bShow,  
    BOOL bDelay);
```  
  
### <a name="parameters"></a>Parameter  
 `pBar`  
 Ein Zeiger auf die Steuerleiste ein-oder ausgeblendet werden.  
  
 `bShow`  
 Wenn **"true"**, gibt an, dass die Steuerleiste angezeigt werden. Wenn **"false"**, gibt an, dass die Steuerleiste ausgeblendet werden.  
  
 *bDelay*  
 Wenn **"true"**, verzögern die Steuerleiste angezeigt. Wenn **"false"**, die Steuerleiste sofort anzeigen.  
  
##  <a name="showownedwindows"></a>  CFrameWnd::ShowOwnedWindows  
 Rufen Sie diese Memberfunktion zum aller Fenster angezeigt werden, die Nachfolger der `CFrameWnd` Objekt.  
  
```  
void ShowOwnedWindows(BOOL bShow);
```  
  
### <a name="parameters"></a>Parameter  
 `bShow`  
 Gibt an, ob die zugehörige Windows oder ausgeblendet werden.  
  
## <a name="see-also"></a>Siehe auch  
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [CMDIFrameWnd-Klasse](../../mfc/reference/cmdiframewnd-class.md)   
 [CMDIChildWnd-Klasse](../../mfc/reference/cmdichildwnd-class.md)   
 [CView-Klasse](../../mfc/reference/cview-class.md)   
 [CDocTemplate-Klasse](../../mfc/reference/cdoctemplate-class.md)   
 [CRuntimeClass-Struktur](../../mfc/reference/cruntimeclass-structure.md)

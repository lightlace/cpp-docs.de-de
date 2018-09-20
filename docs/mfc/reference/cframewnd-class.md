---
title: CFrameWnd-Klasse | Microsoft-Dokumentation
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
ms.openlocfilehash: 12982c212cf8ff4fe502638a5c466306bfe15eb1
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46374287"
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
|[CFrameWnd::ActivateFrame](#activateframe)|Können den Rahmen für dem Benutzer sichtbar und verfügbar.|
|[CFrameWnd::BeginModalState](#beginmodalstate)|Legt das Rahmenfenster zum modalen Element fest.|
|[CFrameWnd::Create](#create)|Aufrufen zum Erstellen und initialisieren das zugeordnete Windows-Rahmenfenster der `CFrameWnd` Objekt.|
|[CFrameWnd::CreateView](#createview)|Erstellt eine Ansicht innerhalb eines Rahmens, der nicht vom abgeleitet wird `CView`.|
|[CFrameWnd:: DockControlBar](#dockcontrolbar)|Wird eine Steuerleiste angedockt.|
|[EnableDocking](#enabledocking)|Ermöglicht eine Steuerleiste angedockt werden.|
|[CFrameWnd::EndModalState](#endmodalstate)|Beendet das Rahmenfenster modalen Zustand. Aktiviert alle deaktiviert Windows `BeginModalState`.|
|[CFrameWnd::FloatControlBar](#floatcontrolbar)|Schwebt eine Steuerleiste.|
|[CFrameWnd::GetActiveDocument](#getactivedocument)|Gibt den aktiven `CDocument` Objekt.|
|[CFrameWnd::GetActiveFrame](#getactiveframe)|Gibt den aktiven `CFrameWnd` Objekt.|
|[CFrameWnd::GetActiveView](#getactiveview)|Gibt den aktiven `CView` Objekt.|
|[CFrameWnd::GetControlBar](#getcontrolbar)|Ruft die Steuerleiste ab.|
|[CFrameWnd::GetDockState](#getdockstate)|Ruft den Zustand Dock Rand eines Rahmenfensters ab.|
|[CFrameWnd::GetMenuBarState](#getmenubarstate)|Ruft den Anzeigezustand des Menüs in der aktuellen MFC-Anwendung ab.|
|[CFrameWnd::GetMenuBarVisibility](#getmenubarvisibility)|Gibt an, ob das Standardverhalten des Menüs in der aktuellen MFC-Anwendung entweder ausgeblendet oder sichtbar ist.|
|[CFrameWnd::GetMessageBar](#getmessagebar)|Gibt einen Zeiger auf die Statusleiste, die zum Rahmenfenster gehören.|
|[CFrameWnd::GetMessageString](#getmessagestring)|Ruft die Meldung, die für eine Befehls-ID ab|
|[CFrameWnd::GetTitle](#gettitle)|Ruft den Titel der zugehörigen Steuerleiste ab.|
|[CFrameWnd::InitialUpdateFrame](#initialupdateframe)|Bewirkt, dass die `OnInitialUpdate` Member-Funktion, die für alle Ansichten im Fenster "Frame" aufgerufen werden, gehören.|
|[CFrameWnd::InModalState](#inmodalstate)|Gibt einen Wert, der angibt, ob ein Rahmenfenster in einem modalen Zustand ist.|
|[CFrameWnd::IsTracking](#istracking)|Bestimmt, ob der Teilerleiste gerade verschoben wird.|
|[CFrameWnd::LoadAccelTable](#loadacceltable)|Rufen Sie eine Tabelle mit Zugriffstasten wird geladen.|
|[CFrameWnd:: LoadBarState](#loadbarstate)|Rufen Sie zum Wiederherstellen der Steuerleiste.|
|[CFrameWnd::LoadFrame](#loadframe)|Aufruf, um ein Framefenster von Ressourceninformationen dynamisch zu erstellen.|
|[CFrameWnd::NegotiateBorderSpace](#negotiateborderspace)|Handelt Rahmenbereich Rahmenfenster.|
|[CFrameWnd::OnBarCheck](#onbarcheck)|Aufgerufen, wenn eine Aktion für die angegebene Steuerleiste ausgeführt wird.|
|[CFrameWnd::OnContextHelp](#oncontexthelp)|Verarbeitet die UMSCHALT + F1-Hilfe für ein direktes Elemente.|
|[CFrameWnd:: Onsetpreviewmode](#onsetpreviewmode)|Legt die anwendungshauptrahmenfensters fest, in und aus den Seitenansicht-Modus.|
|[CFrameWnd::OnUpdateControlBarMenu](#onupdatecontrolbarmenu)|Vom Framework aufgerufen, wenn das zugeordnete Menü aktualisiert wird.|
|[CFrameWnd::RecalcLayout](#recalclayout)|Automatisch neu positioniert und die Steuerleisten, der die `CFrameWnd` Objekt.|
|[SaveBarState](#savebarstate)|Rufen Sie zum Speichern der Steuerleiste.|
|[CFrameWnd::SetActivePreviewView](#setactivepreviewview)|Legt fest, die angegebene Ansicht die aktive Ansicht for Rich Preview sein.|
|[CFrameWnd::SetActiveView](#setactiveview)|Legt den aktiven `CView` Objekt.|
|[CFrameWnd::SetDockState](#setdockstate)|Rufen Sie das Rahmenfenster im Hauptfenster von angedockt.|
|[CFrameWnd::SetMenuBarState](#setmenubarstate)|Legt den Anzeigezustand des Menüs in der aktuellen MFC-Anwendung, die ausgeblendet oder angezeigt.|
|[CFrameWnd::SetMenuBarVisibility](#setmenubarvisibility)|Legt das Standardverhalten des Menüs in der aktuellen MFC-Anwendung entweder ausgeblendet oder sichtbar sein.|
|[CFrameWnd::SetMessageText](#setmessagetext)|Legt den Text eine Standardstatusleiste fest.|
|[CFrameWnd::SetProgressBarPosition](#setprogressbarposition)|Legt die aktuelle Position für Windows 7-Statusanzeige auf der Taskleiste angezeigt.|
|[CFrameWnd::SetProgressBarRange](#setprogressbarrange)|Legt fest, der Bereich für Windows 7-Statusanzeige auf der Taskleiste angezeigt.|
|[CFrameWnd::SetProgressBarState](#setprogressbarstate)|Legt fest, Typ und Status der Statusanzeige in der Taskleistenschaltfläche angezeigt.|
|[CFrameWnd::SetTaskbarOverlayIcon](#settaskbaroverlayicon)|Überladen. Wendet eine Überlagerung auf eine Taskleistenschaltfläche Status der Anwendung oder eine Benachrichtigung an den Benutzer an.|
|[CFrameWnd::SetTitle](#settitle)|Legt den Titel der zugehörigen Steuerleiste fest.|
|[CFrameWnd::ShowControlBar](#showcontrolbar)|Rufen Sie die Steuerelement-Statusleiste angezeigt.|
|[CFrameWnd::ShowOwnedWindows](#showownedwindows)|Zeigt alle Fenster, die Nachfolger der `CFrameWnd` Objekt.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CFrameWnd::OnCreateClient](#oncreateclient)|Erstellt ein Clientfenster für den Frame.|
|[CFrameWnd::OnHideMenuBar](#onhidemenubar)|Wird aufgerufen, bevor im Menü in der aktuellen MFC-Anwendung ausgeblendet wird.|
|[CFrameWnd::OnShowMenuBar](#onshowmenubar)|Wird aufgerufen, bevor Sie das Menü in der aktuellen MFC-Anwendung angezeigt wird.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CFrameWnd::m_bAutoMenuEnable](#m_bautomenuenable)|Steuerelemente, die automatische Aktivieren und Deaktivieren von Funktionen für Menüelemente.|
|[CFrameWnd::rectDefault](#rectdefault)|Übergeben Sie diese statische `CRect` als Parameter beim Erstellen einer `CFrameWnd` Objekt, das Zulassen von Windows auf die ursprüngliche Größe und Position des Fensters auswählen.|

## <a name="remarks"></a>Hinweise

Um eine nützliche Rahmenfenster für Ihre Anwendung zu erstellen, leiten Sie eine Klasse von `CFrameWnd`. Hinzufügen von Membervariablen des Typs der abgeleiteten Klasse zum Speichern von Daten, die spezifisch für Ihre Anwendung. Implementieren Sie Meldungshandler-Memberfunktionen und eine Meldungszuordnung in der abgeleiteten Klasse, um anzugeben, was passiert, wenn Meldungen an das Fenster weitergeleitet werden.

Es gibt drei Möglichkeiten zum Erstellen eines Rahmenfensters:

- Erstellen Sie direkt mit [erstellen](#create).

- Erstellen Sie direkt mit [LoadFrame](#loadframe).

- Erstellen Sie mithilfe einer Dokumentvorlage indirekt.

Vor dem Aufruf entweder `Create` oder `LoadFrame`, müssen Sie die Frame-Window-Objekt, auf dem Heap mit C++ erstellen **neue** Operator. Vor dem Aufruf `Create`, Sie können auch eine Fensterklasse mit Registrieren der [AfxRegisterWndClass](../../mfc/reference/application-information-and-management.md#afxregisterwndclass) -Funktion verwenden, um die Stile-Symbol und die Klasse für den Frame festgelegt.

Verwenden der `Create` Member-Funktion, Parameter zum Erstellen des Frames als sofortige Argumente übergeben.

`LoadFrame` erfordert weniger Argumente als `Create`, und ruft stattdessen die meisten von den Standardwerten aus Ressourcen, einschließlich der Beschriftung, Symbol, Zugriffstastentabelle und im Menü des Frames. Zugänglich sein `LoadFrame`, alle diese Ressourcen müssen die Ressourcen-ID (z. B. IDR_MAINFRAME).

Wenn eine `CFrameWnd` Objekt enthält Ansichten und Dokumente, indirekt vom Framework nicht direkt vom Programmierer erstellt werden. Die `CDocTemplate` Objekt orchestriert die Erstellung des Frames, die Erstellung der Ansichten enthält und die Verbindung der Ansichten für das entsprechende Dokument. Die Parameter der `CDocTemplate` Konstruktor Festlegen der `CRuntimeClass` der drei Klassen beteiligt (Dokument, Rahmen und Ansicht). Ein `CRuntimeClass` Objekt wird vom Framework verwendet, dynamisch neue Frames an, wenn vom Benutzer angegeben (z. B. mithilfe der neuen Datei Befehl oder neue Fenster mehrere Document Interface (MDI)-Befehl) erstellt.

Eine Rahmenfenster abgeleitete Klasse `CFrameWnd` muss mit DECLARE_DYNCREATE deklariert werden, in der Reihenfolge für die oben genannten RUNTIME_CLASS-Mechanismus ordnungsgemäß funktioniert.

Ein `CFrameWnd` standardimplementierungen, die zum Ausführen der folgenden Funktionen des ein Hauptfenster in einer typischen Anwendung für Windows enthält:

- Ein `CFrameWnd` Rahmenfenster verfolgt des eine aktive Ansicht, die unabhängig von der aktiven Windows-Fenster oder den aktuellen Eingabefokus ist. Wenn der Frame erneut aktiviert wird, wird die aktive Ansicht durch den Aufruf benachrichtigt `CView::OnActivateView`.

- Befehl Nachrichten und viele allgemeine Frame-Notification-Meldungen, einschließlich behandelt, indem die `OnSetFocus`, `OnHScroll`, und `OnVScroll` Funktionen `CWnd`, werden von delegiert eine `CFrameWnd` Rahmenfenster, die derzeit aktive Ansicht.

- Die derzeit aktive Ansicht (oder den derzeit aktiven untergeordneten MDI-Rahmenfenster im Falle einer MDI-Frame) kann dazu führen, dass die Beschriftung des Rahmenfensters bestimmen. Dieses Feature kann deaktiviert werden, durch das FWS_ADDTOTITLE-Formatbit des Rahmenfensters deaktivieren.

- Ein `CFrameWnd` Rahmenfenster verwaltet die Positionierung der Schiebeleisten-Steuerelemente, Ansichten und andere untergeordnete Fenster im Clientbereich des Rahmenfensters. Ein Rahmenfenster führt auch die Zeit im Leerlauf zu aktualisieren, der Symbolleiste und die anderen Schaltflächen Steuerleiste. Ein `CFrameWnd` Rahmenfenster verfügt auch über standardimplementierungen von Befehlen zum Umschalten von ein- und Ausschalten der Symbolleiste und Statusleiste.

- Ein `CFrameWnd` Rahmenfenster verwaltet die Hauptmenüleiste. Wenn ein Popup-Menü angezeigt wird, verwendet das Rahmenfenster den wähle ich UPDATE_COMMAND_UI-Mechanismus, um zu bestimmen, welche Menüelemente aktiviert, deaktiviert oder aktiviert werden sollte. Wenn der Benutzer ein Menüelement auswählt, aktualisiert das Rahmenfenster die Statusleiste mit die Meldungszeichenfolge für diesen Befehl an.

- Ein `CFrameWnd` Rahmenfenster ist eine optionale Zugriffstastentabelle, die automatisch Zugriffstasten übersetzt.

- Ein `CFrameWnd` Rahmenfenster ist eine optionale Hilfe-ID mit `LoadFrame` , die für die kontextbezogene Hilfe verwendet wird. Ein Rahmenfenster ist die wichtigste Orchestrator halbmodaler Zustand wie Print-Modus "und" kontextbezogene Hilfe (UMSCHALT + F1).

- Ein `CFrameWnd` Rahmenfenster öffnet eine Datei aus dem Datei-Manager Drag & Drop in das Rahmenfenster. Wenn eine Erweiterung registriert und mit der Anwendung verknüpft wird, reagiert das Rahmenfenster auf die dynamischen Datenaustausch (DDE) öffnen datenanforderungen, das auftritt, wenn der Benutzer eine Datei im Datei-Manager geöffnet wird, oder wenn die `ShellExecute` Windows-Funktion wird aufgerufen.

- Wenn das Rahmenfenster Hauptfensters der Anwendung ist (d. h. `CWinThread::m_pMainWnd`), wenn der Benutzer die Anwendung schließt das Rahmenfenster der Benutzer aufgefordert, alle geänderten Dokumente speichern (für `OnClose` und `OnQueryEndSession`).

- Wenn das Rahmenfenster, das Hauptanwendungsfenster ist, ist das Rahmenfenster der Kontext für die Ausführung von WinHelp aus. Schließen das Rahmenfenster WINHELP heruntergefahren wird. EXE-Datei, wenn sie Hilfe für diese Anwendung gestartet wurde.

Verwenden Sie nicht die C++ **löschen** Operator, um ein Rahmenfenster zu zerstören. Verwenden Sie stattdessen `CWnd::DestroyWindow`. Die `CFrameWnd` Implementierung `PostNcDestroy` löscht das C++-Objekt aus, wenn das Fenster zerstört wird. Der Benutzer schließt das Rahmenfenster, der Standardwert `OnClose` Handler ruft `DestroyWindow`.

Weitere Informationen zu `CFrameWnd`, finden Sie unter [Frame Windows](../../mfc/frame-windows.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CFrameWnd`

## <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

##  <a name="activateframe"></a>  CFrameWnd::ActivateFrame

Rufen Sie diese Memberfunktion zum Aktivieren und das Rahmenfenster wiederherstellen, sodass sie für den Benutzer sichtbar und verfügbar ist.

```
virtual void ActivateFrame(int nCmdShow = -1);
```

### <a name="parameters"></a>Parameter

*nCmdShow*<br/>
Gibt die Parameter zum Übergeben an [ShowWindow](../../mfc/reference/cwnd-class.md#showwindow). Standardmäßig wird der Frame dargestellt und ordnungsgemäß wiederhergestellt.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion wird normalerweise aufgerufen, nachdem ein Benutzeroberfläche-Ereignis, z. B. eine DDE, OLE, oder ein anderes Ereignis, das das Rahmenfenster oder dessen Inhalt an dem Benutzer angezeigt werden kann.

Die standardmäßige Implementierung den Frame aktiviert und können sie Sie am Anfang der Z-Reihenfolge und bei Bedarf führt die gleichen Schritte für das Hauptrahmenfenster der Anwendung.

Überschreiben Sie diese Memberfunktion zum Ändern, wie ein Frame aktiviert wird. Beispielsweise können Sie untergeordnete MDI-Fenster, das maximiert werden erzwingen. Fügen Sie die entsprechende Funktionalität hinzu, und klicken Sie dann die Basisklassenversion mit einem expliziten Aufrufen *nCmdShow*.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#1](../../mfc/reference/codesnippet/cpp/cframewnd-class_1.cpp)]

##  <a name="beginmodalstate"></a>  CFrameWnd::BeginModalState

Rufen Sie diese Memberfunktion auf, um ein Framefenster modal zu machen.

```
virtual void BeginModalState();
```

##  <a name="cframewnd"></a>  CFrameWnd::CFrameWnd

Erstellt eine `CFrameWnd` Objekt, aber erstellt keine sichtbare Rahmenfenster.

```
CFrameWnd();
```

### <a name="remarks"></a>Hinweise

Rufen Sie `Create` zum Erstellen des Fensters sichtbar.

##  <a name="create"></a>  CFrameWnd::Create

Aufrufen zum Erstellen und initialisieren das zugeordnete Windows-Rahmenfenster der `CFrameWnd` Objekt.

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

*"lpszclassname"*<br/>
Verweist auf eine Null-terminierte Zeichenfolge, die Namen die Windows-Klasse. Der Klassenname kann einen beliebigen Namen registriert werden die `AfxRegisterWndClass` globale Funktion oder die `RegisterClass` Windows-Funktion. Wenn der Wert NULL ist, verwendet den vordefinierten Standardwert `CFrameWnd` Attribute.

*lpszWindowName*<br/>
Verweist auf eine Null-terminierte Zeichenfolge, die den Fensternamen darstellt. Als Text verwendet der Titelleiste.

*dwStyle*<br/>
Gibt das Zeitfenster [Stil](../../mfc/reference/styles-used-by-mfc.md#window-styles) Attribute. Fügen Sie den FWS_ADDTOTITLE-Stil, wenn Sie möchten, dass die Titelleiste, um automatisch den Namen des Dokuments dargestellt im Fenster anzuzeigen.

*Rect*<br/>
Gibt an, die Größe und Position des Fensters. Die *RectDefault* Wert ermöglicht Windows die Größe und Position des neuen Fensters an.

*pParentWnd*<br/>
Gibt an, das übergeordnete Fenster des dieses Rahmenfenster. Dieser Parameter sollte NULL für Rahmenfenster der obersten Ebene sein.

*lpszMenuName*<br/>
Identifiziert den Namen der Menüressource mit dem Fenster verwendet werden. Verwenden Sie MAKEINTRESOURCE aus, wenn Sie im Menü eine ganzzahlige ID anstelle einer Zeichenfolge hat. Dieser Parameter kann NULL sein.

*dwExStyle*<br/>
Gibt an, das erweiterte Fenster [Stil](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles) Attribute.

*"pContext"*<br/>
Gibt einen Zeiger auf eine [CCreateContext](../../mfc/reference/ccreatecontext-structure.md) Struktur. Dieser Parameter kann NULL sein.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn die Initialisierung erfolgreich ist; andernfalls 0.

### <a name="remarks"></a>Hinweise

Erstellen einer `CFrameWnd` Objekt in zwei Schritten. Zuerst Aufrufen des Konstruktors, der erstellt die `CFrameWnd` Objekt aus, und rufen Sie anschließend `Create`, die das Windows-Rahmenfenster erstellt, und fügt es der `CFrameWnd` Objekt. `Create` Initialisiert den Namen des Fensters-Klasse und Fenstername und Standardwerte für die Art, übergeordneten und zugeordnete Speisekarte registriert.

Verwendung `LoadFrame` statt `Create` das Rahmenfenster von einer Ressource anstatt Argumente zu laden.

##  <a name="createview"></a>  CFrameWnd::CreateView

Rufen Sie `CreateView` So erstellen Sie eine Ansicht innerhalb eines Rahmens.

```
CWnd* CreateView(
    CCreateContext* pContext,
    UINT nID = AFX_IDW_PANE_FIRST);
```

### <a name="parameters"></a>Parameter

*"pContext"*<br/>
Gibt den Typ der Ansicht und des Dokuments.

*nID*<br/>
Die ID einer Ansicht.

### <a name="return-value"></a>Rückgabewert

Zeiger auf eine `CWnd` -Objekt, wenn erfolgreich; andernfalls NULL.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Memberfunktion, die nicht zum Erstellen von "Ansichten" `CView`-abgeleitet, die innerhalb eines Rahmens. Nach dem Aufruf `CreateView`, müssen Sie manuell die Ansicht auf aktiv festgelegt und sichtbar sein; diese Aufgaben werden nicht automatisch vom ausgeführt `CreateView`.

##  <a name="dockcontrolbar"></a>  CFrameWnd:: DockControlBar

Bewirkt, dass eine Steuerleiste, die an das Rahmenfenster angedockt werden.

```
void DockControlBar(
    CControlBar* pBar,
    UINT nDockBarID = 0,
    LPCRECT lpRect = NULL);
```

### <a name="parameters"></a>Parameter

*pBar*<br/>
Zeigt auf der Steuerleiste angedockt werden.

*nDockBarID*<br/>
Bestimmt, welche Seiten des Rahmenfensters Andocken berücksichtigen. Er kann 0 (null) oder eine oder mehrere der folgenden sein:

- AFX_IDW_DOCKBAR_TOP andocken, am oberen Rand des Rahmenfensters.

- An der Unterseite des Rahmenfensters AFX_IDW_DOCKBAR_BOTTOM-andocken.

- An der linken Seite des Rahmenfensters AFX_IDW_DOCKBAR_LEFT-andocken.

- An der rechten Seite des Rahmenfensters AFX_IDW_DOCKBAR_RIGHT-andocken.

Bei 0 kann eine Seite, die für die in der Ziel-Rahmenfenster Andocken aktiviert die Steuerleiste angedockt werden.

*lpRect*<br/>
Bestimmt, in Bildschirmkoordinaten, der im Clientbereich eines Rahmenfensters das Ziel, in dem die Steuerleiste angedockt wird.

### <a name="remarks"></a>Hinweise

Auf eine der Seiten des Rahmenfensters angegeben, die in den Aufrufen auf die Steuerleiste angedockt [CControlBar:: EnableDocking](../../mfc/reference/ccontrolbar-class.md#enabledocking) und [EnableDocking](#enabledocking). Das ausgewählte Seite richtet sich nach *nDockBarID*.

##  <a name="enabledocking"></a>  EnableDocking

Mit dieser Funktion können andockbaren Steuerleisten in einem Rahmenfenster zu aktivieren.

```
void EnableDocking(DWORD dwDockStyle);
```

### <a name="parameters"></a>Parameter

*dwDockStyle*<br/>
Gibt an, welche Seiten des Rahmenfensters dienen können, wie Websites für Schiebeleisten-Steuerelemente andocken. Sie können eine oder mehrere der folgenden sein:

- CBRS_ALIGN_TOP ermöglicht das Andocken am oberen Rand des Clientbereichs.

- CBRS_ALIGN_BOTTOM ermöglicht das Andocken am unteren Rand des Clientbereichs.

- CBRS_ALIGN_LEFT können auf der linken Seite des Clientbereichs andocken.

- CBRS_ALIGN_RIGHT können auf der rechten Seite des Clientbereichs andocken.

- CBRS_ALIGN_ANY ermöglicht das Andocken an jede Seite des Clientbereichs.

### <a name="remarks"></a>Hinweise

In der Standardeinstellung Schiebeleisten-Steuerelemente auf einer Seite des Fensters "Frame" in der folgenden Reihenfolge angedockt: oben, unten, links, rechts.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [Symbolleistenformate](../../mfc/reference/ctoolbar-class.md#create).

##  <a name="endmodalstate"></a>  CFrameWnd::EndModalState

Rufen Sie diese Memberfunktion auf, um ein Framefenster von einem modalen in einen Status ohne Modus zu ändern.

```
virtual void EndModalState();
```

### <a name="remarks"></a>Hinweise

`EndModalState` aktiviert alle deaktiviert Windows [BeginModalState](#beginmodalstate).

##  <a name="floatcontrolbar"></a>  CFrameWnd::FloatControlBar

Mit dieser Funktion können dazu führen, dass eine Steuerleiste, die nicht an das Rahmenfenster angedockt werden.

```
void FloatControlBar(
    CControlBar* pBar,
    CPoint point,
    DWORD dwStyle = CBRS_ALIGN_TOP);
```

### <a name="parameters"></a>Parameter

*pBar*<br/>
Zeigt auf der Steuerleiste abgedockt werden.

*Zeigen Sie*<br/>
Der Speicherort, in Bildschirmkoordinaten, in der oberen linken Ecke der Steuerleiste platziert werden.

*dwStyle*<br/>
Gibt an, ob die Steuerleiste im zugehörigen neuen Rahmenfenster horizontal oder vertikal ausrichten. Sie können eine der folgenden sein:

- CBRS_ALIGN_TOP wird die Steuerleiste vertikal ausgerichtet.

- CBRS_ALIGN_BOTTOM wird die Steuerleiste vertikal ausgerichtet.

- CBRS_ALIGN_LEFT wird die Steuerleiste horizontal ausgerichtet.

- CBRS_ALIGN_RIGHT wird die Steuerleiste horizontal ausgerichtet.

Wenn Stile horizontale und vertikale Ausrichtung angeben übergeben werden, wird die Symbolleiste horizontal ausgerichtet werden.

### <a name="remarks"></a>Hinweise

In der Regel beim Start der Anwendung geschieht dies, wenn das Programm aus der vorherigen Ausführung Prozess ist.

Diese Funktion wird vom Framework aufgerufen, wenn der Benutzer führt dazu, dass es sich bei einen Drop-Vorgang durch die Freigabe der linke Maustaste gedrückt, während Sie mit der Steuerleiste auf einen Speicherort an, der für das Andocken nicht verfügbar ist.

##  <a name="getactivedocument"></a>  CFrameWnd::GetActiveDocument

Rufen Sie diese Memberfunktion, um einen Zeiger auf den aktuellen erhalten `CDocument` angefügt, die zurzeit aktive Sicht.

```
virtual CDocument* GetActiveDocument();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die aktuelle [CDocument](../../mfc/reference/cdocument-class.md). Wenn keine Aktuelles Dokument vorhanden ist, gibt NULL zurück.

##  <a name="getactiveframe"></a>  CFrameWnd::GetActiveFrame

Rufen Sie diese Memberfunktion, um einem Zeiger auf das aktive Fenster multiple Document Interface (MDI) untergeordnetes Element von einem MDI-Rahmenfenster zu erhalten.

```
virtual CFrameWnd* GetActiveFrame();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die aktiven untergeordneten MDI-Fensters. Wenn die Anwendung einer SDI-Anwendung oder das MDI-Rahmenfenster kein aktives Dokument, das implizite ist **dies** Zeiger zurückgegeben werden.

### <a name="remarks"></a>Hinweise

Wenn es keine aktive untergeordnete MDI-Element oder die Anwendung eine Einzeldokumentoberfläche (SDI), den impliziten ist **dies** Zeiger zurückgegeben.

##  <a name="getactiveview"></a>  CFrameWnd::GetActiveView

Rufen Sie diese Memberfunktion, um einen Zeiger auf die aktive Ansicht (sofern vorhanden) angefügt, um ein Framefenster abrufen ( `CFrameWnd`).

```
CView* GetActiveView() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die aktuelle [CView](../../mfc/reference/cview-class.md). Wenn keine aktuelle Ansicht vorhanden ist, gibt NULL zurück.

### <a name="remarks"></a>Hinweise

Diese Funktion gibt NULL, wenn für eine MDI-Hauptrahmenfenster aufgerufen ( `CMDIFrameWnd`). In einer MDI-Anwendung muss das untergeordnete MDI-Hauptrahmenfenster keine Ansicht zugeordnet. Stattdessen jedes einzelne untergeordnete Fenster ( `CMDIChildWnd`) verfügt über eine oder mehrere zugeordnete Sichten. Die aktive Ansicht in einer MDI-Anwendung kann zunächst der aktiven untergeordneten MDI-Fensters und suchen die aktive Ansicht klicken Sie dann für diese untergeordnete Fenster abgerufen werden. Die aktiven untergeordneten MDI-Fensters finden Sie durch Aufrufen der Funktion `MDIGetActive` oder `GetActiveFrame` wie im folgenden gezeigt:

[!code-cpp[NVC_MFCWindowing#2](../../mfc/reference/codesnippet/cpp/cframewnd-class_2.cpp)]

##  <a name="getcontrolbar"></a>  CFrameWnd::GetControlBar

Rufen Sie `GetControlBar` für den Zugriff auf die Steuerleiste, die mit der ID verknüpft ist

```
CControlBar* GetControlBar(UINT nID);
```

### <a name="parameters"></a>Parameter

*nID*<br/>
Die ID einer Steuerleiste.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die Steuerleiste, die mit der ID verknüpft ist

### <a name="remarks"></a>Hinweise

Die *nID* Parameter verweist auf den eindeutigen Bezeichner, die an die `Create` Methode der Steuerleiste. Weitere Informationen zu Schiebeleisten-Steuerelemente, finden Sie unter dem Thema [Steuerleisten](../../mfc/control-bars.md).

`GetControlBar` Gibt die Steuerleiste zurück, auch wenn es unverankert ist, und daher nicht gerade ein untergeordnetes Fenster des Frames ist.

##  <a name="getdockstate"></a>  CFrameWnd::GetDockState

Rufen Sie diese Memberfunktion zum Speichern von Zustandsinformationen über das Rahmenfenster Steuerleisten in einem `CDockState` Objekt.

```
void GetDockState(CDockState& state) const;
```

### <a name="parameters"></a>Parameter

*state*<br/>
Enthält den aktuellen Zustand des Schiebeleisten-Steuerelemente das Rahmenfenster bei der Rückgabe an.

### <a name="remarks"></a>Hinweise

Anschließend können Sie den Inhalt der schreiben `CDockState` -Speicher mithilfe `CDockState::SaveState` oder `Serialize`. Wenn Sie später die Steuerleisten in einem vorherigen Zustand wiederherstellen möchten, laden Sie den Status mit `CDockState::LoadState` oder `Serialize`, rufen Sie anschließend `SetDockState` Schiebeleisten-Steuerelemente das Rahmenfenster den vorherigen Status zuweisen.

##  <a name="getmenubarstate"></a>  CFrameWnd::GetMenuBarState

Ruft den Anzeigezustand des Menüs in der aktuellen MFC-Anwendung ab.

```
virtual DWORD GetMenuBarState();
```

### <a name="return-value"></a>Rückgabewert

Der Rückgabewert kann es sich um die folgenden Werte aufweisen:

- AFX_MBS_VISIBLE (0 x 01) – wird das Menü angezeigt.

- AFX_MBS_HIDDEN (0 x 02) – klicken Sie im Menü ausgeblendet ist.

### <a name="remarks"></a>Hinweise

Wenn ein Laufzeitfehler auftritt, wird diese Methode Assert-Vorgänge im Debugmodus befinden, und löst eine Ausnahme, abgeleitet aus den [CException](../../mfc/reference/cexception-class.md) Klasse.

##  <a name="getmenubarvisibility"></a>  CFrameWnd::GetMenuBarVisibility

Gibt an, ob der Standardzustand des Menüs in der aktuellen MFC-Anwendung ausgeblendet oder sichtbar ist.

```
virtual DWORD CFrameWnd::GetMenuBarVisibility();
```

### <a name="return-value"></a>Rückgabewert

Diese Methode gibt einen der folgenden Werte zurück:

- AFX_MBV_KEEPVISIBLE (0 x 01) – klicken Sie im Menü wird angezeigt, auf allen Zeiten und von Standard verfügt nicht über den Fokus.

- AFX_MBV_DISPLAYONFOCUS (0 x 02) – klicken Sie im Menü ist standardmäßig ausgeblendet. Wenn Sie im Menü ausgeblendet ist, drücken Sie ALT gedrückt, um das Menü anzuzeigen, und geben Sie ihm den Fokus. Wenn Sie im Menü angezeigt wird, drücken Sie die ALT-Taste oder die ESC-Taste, um es auszublenden.

- AFX_MBV_ DISPLAYONFOCUS (0 x 02) &#124; AFX_MBV_DISPLAYONF10 (0 x 04) (bitweise Kombination (OR)) – klicken Sie im Menü ist standardmäßig ausgeblendet. Wenn Sie im Menü ausgeblendet ist, drücken Sie die Taste F10, um das Menü anzuzeigen, und geben Sie ihm den Fokus. Wenn Sie im Menü angezeigt wird, drücken Sie die Taste F10, um den Fokus aktivieren oder deaktivieren Sie im Menü zu wechseln. Klicken Sie im Menü wird angezeigt, bis Sie der ALT-Taste oder die ESC-Taste drücken, um es auszublenden.

### <a name="remarks"></a>Hinweise

Wenn ein Laufzeitfehler auftritt, wird diese Methode Assert-Vorgänge im Debugmodus befinden, und löst eine Ausnahme, abgeleitet aus den [CException](../../mfc/reference/cexception-class.md) Klasse.

##  <a name="getmessagebar"></a>  CFrameWnd::GetMessageBar

Rufen Sie diese Memberfunktion zum Abrufen eines Zeigers auf der Statusleiste angezeigt.

```
virtual CWnd* GetMessageBar();
```

### <a name="return-value"></a>Rückgabewert

Zeiger auf das Fenster mit der Statusleiste.

##  <a name="getmessagestring"></a>  CFrameWnd::GetMessageString

Überschreiben Sie diese Funktion zum Bereitstellen von benutzerdefinierter Zeichenfolgen für Befehls-IDs.

```
virtual void GetMessageString(
    UINT nID,
    CString& rMessage) const;
```

### <a name="parameters"></a>Parameter

*nID*<br/>
Ressourcen-ID, der die gewünschte Nachricht.

*rMessage*<br/>
`CString` Objekt in der die Nachricht platziert werden soll.

### <a name="remarks"></a>Hinweise

Die standardmäßige Implementierung einfach lädt die angegebenen Zeichenfolge *nID* aus der Ressourcendatei. Diese Funktion wird vom Framework aufgerufen, wenn die Meldungszeichenfolge in der Statusleiste aktualisieren benötigt.

##  <a name="gettitle"></a>  CFrameWnd::GetTitle

Ruft den Titel des Window-Objekts ab.

```
CString GetTitle() const;
```

### <a name="return-value"></a>Rückgabewert

Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) -Objekt, das den aktuellen Titel des Window-Objekts enthält.

##  <a name="initialupdateframe"></a>  CFrameWnd::InitialUpdateFrame

Rufen Sie `IntitialUpdateFrame` nach dem Erstellen eines neuen Frames mit `Create`.

```
void InitialUpdateFrame(
    CDocument* pDoc,
    BOOL bMakeVisible);
```

### <a name="parameters"></a>Parameter

*pDoc*<br/>
Verweist auf das Dokument, das das Rahmenfenster zugeordnet ist. NULL kann sein.

*bMakeVisible*<br/>
TRUE gibt an, dass der Rahmen sichtbar und aktiv werden sollten. Wenn "FALSE" sind keine abhängigen Elemente sichtbar gemacht.

### <a name="remarks"></a>Hinweise

In diesem Fall würde allen Ansichten, Rahmenfenster erhalten ihre `OnInitialUpdate` aufrufen.

Darüber hinaus war es nicht bereits eine aktive Ansicht, die primäre Ansicht des Rahmenfensters active erfolgt. Die primäre Ansicht ist eine Ansicht mit einem untergeordneten Element-ID des AFX_IDW_PANE_FIRST. Zum Schluss das Rahmenfenster sichtbar gemacht wird Wenn *bMakeVisible* ungleich NULL ist. Wenn *bMakeVisible* gleich 0 ist, die aktueller Fokus und der sichtbare Zustand des Rahmenfensters bleiben unverändert. Es ist nicht notwendig, diese Funktion aufrufen, wenn mit der Implementierung des Frameworks neue Datei und die Datei öffnen.

##  <a name="inmodalstate"></a>  CFrameWnd::InModalState

Rufen Sie diese Memberfunktion, um festzustellen, ob ein Rahmenfenster gebunden oder ungebunden ist.

```
BOOL InModalState() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn dies der Fall; andernfalls 0.

##  <a name="istracking"></a>  CFrameWnd::IsTracking

Rufen Sie diese Memberfunktion, um festzustellen, ob die Teilerleiste im Fenster gerade verschoben wird.

```
BOOL IsTracking() const;
```

### <a name="return-value"></a>Rückgabewert

Legen Sie ungleich NULL, wenn es sich bei ein Splitter-Vorgang ausgeführt wird; andernfalls 0.

##  <a name="loadacceltable"></a>  CFrameWnd::LoadAccelTable

Rufen Sie zum Laden der Tabelle angegebenen Beschleuniger.

```
BOOL LoadAccelTable(LPCTSTR lpszResourceName);
```

### <a name="parameters"></a>Parameter

*lpszResourceName*<br/>
Identifiziert den Namen der Zugriffstastenressource. Verwenden Sie MAKEINTRESOURCE, wenn die Ressource mit einer ganzzahligen ID identifiziert wird

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Zugriffstastentabelle erfolgreich geladen wurde; andernfalls 0.

### <a name="remarks"></a>Hinweise

Nur eine Tabelle kann gleichzeitig geladen werden.

Zugriffstastentabellen aus Ressourcen geladen werden automatisch freigegeben, wenn die Anwendung beendet wird.

Wenn Sie aufrufen `LoadFrame` um das Rahmenfenster zu erstellen, lädt das Framework einer Zugriffstastentabelle zusammen mit den Ressourcen im Menü "und" Symbol und ein nachfolgender Aufruf von dieser Memberfunktion ist dann nicht erforderlich.

##  <a name="loadbarstate"></a>  CFrameWnd:: LoadBarState

Rufen Sie diese Funktion, um die Einstellungen der jede Steuerleiste, die im Besitz von Rahmenfenster wiederherzustellen.

```
void LoadBarState(LPCTSTR lpszProfileName);
```

### <a name="parameters"></a>Parameter

*lpszProfileName*<br/>
Name des einen Abschnitt in der Initialisierungsdatei (INI) oder einen Schlüssel in der Windows-Registrierung, in dem Statusinformationen gespeichert ist.

### <a name="remarks"></a>Hinweise

Informationen, die wiederhergestellt umfassen Sichtbarkeit, horizontaler/vertikaler Ausrichtung, Andockstatus und Position der Steuerleiste.

Die Einstellungen, die Sie wiederherstellen möchten müssen in der Registrierung geschrieben werden, vor dem Aufruf `LoadBarState`. Schreiben Sie die Informationen in die Registrierung durch den Aufruf [CWinApp::SetRegistryKey](../../mfc/reference/cwinapp-class.md#setregistrykey). Die Informationen in der INI-Datei zu schreiben, durch den Aufruf [SaveBarState](#savebarstate).

##  <a name="loadframe"></a>  CFrameWnd::LoadFrame

Aufruf, um ein Framefenster von Ressourceninformationen dynamisch zu erstellen.

```
virtual BOOL LoadFrame(
    UINT nIDResource,
    DWORD dwDefaultStyle = WS_OVERLAPPEDWINDOW | FWS_ADDTOTITLE,
    CWnd* pParentWnd = NULL,
    CCreateContext* pContext = NULL);
```

### <a name="parameters"></a>Parameter

*nIDResource*<br/>
Die ID des freigegebenen Ressourcen, die das Rahmenfenster zugeordnet.

*dwDefaultStyle*<br/>
Des Frames [Stil](../../mfc/reference/styles-used-by-mfc.md#window-styles). Fügen Sie den FWS_ADDTOTITLE-Stil, wenn Sie möchten, dass die Titelleiste, um automatisch den Namen des Dokuments dargestellt im Fenster anzuzeigen.

*pParentWnd*<br/>
Ein Zeiger auf den Rand des übergeordneten.

*"pContext"*<br/>
Ein Zeiger auf eine [CCreateContext](../../mfc/reference/ccreatecontext-structure.md) Struktur. Dieser Parameter kann NULL sein.

### <a name="remarks"></a>Hinweise

Erstellen einer `CFrameWnd` Objekt in zwei Schritten. Rufen Sie zunächst den Konstruktor, der erstellt die `CFrameWnd` Objekt aus, und rufen Sie dann `LoadFrame`, der lädt, den Windows-Rahmenfenster und die zugeordneten Ressourcen, und fügt das Rahmenfenster auf die `CFrameWnd` Objekt. Die *nIDResource* Parameter gibt an, klicken Sie im Menü, die Zugriffstastentabelle, das Symbol und die Zeichenfolgenressource, der den Titel für das Rahmenfenster.

Verwenden der `Create` Memberfunktion statt `LoadFrame` Wenn Sie alle Parameter für das Rahmenfenster angeben möchten.

Das Framework ruft `LoadFrame` bei einem Rahmenfenster, die Verwendung eines Dokumentobjekts-Vorlage erstellen.

Das Framework verwendet die *"pContext"* Argument an die Objekte an das Rahmenfenster, einschließlich aller verbunden sein enthaltenen Objekte anzeigen. Sie können festlegen, die *"pContext"* Argument auf NULL, wenn Sie aufrufen `LoadFrame`.

##  <a name="m_bautomenuenable"></a>  CFrameWnd::m_bAutoMenuEnable

Wenn dieses Datenelement aktiviert ist (der Standardwert ist), werden Menüelemente, die keine ON_UPDATE_COMMAND_UI oder ON_COMMAND-Handler, wenn der Benutzer ein Menü als Dropdown betätigt automatisch deaktiviert.

```
BOOL m_bAutoMenuEnable;
```

### <a name="remarks"></a>Hinweise

Menüelemente, die einen Handler für ON_COMMAND aber kein ON_UPDATE_COMMAND_UI-Handler werden automatisch aktiviert werden.

Wenn dieses Datenelement festgelegt ist, werden Menüelemente automatisch auf die gleiche Weise aktiviert werden, die Symbolleisten-Schaltflächen aktiviert sind.

> [!NOTE]
> `m_bAutoMenuEnable` hat keine Auswirkungen auf die Menüelemente der obersten Ebene.

Dieses Datenelement vereinfacht die Implementierung von optionale Befehle, die basierend auf der aktuellen Auswahl und verringert den Bedarf an ON_UPDATE_COMMAND_UI-Handler für das Aktivieren und Deaktivieren von Menüelementen zu schreiben.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#3](../../mfc/reference/codesnippet/cpp/cframewnd-class_3.cpp)]

##  <a name="negotiateborderspace"></a>  CFrameWnd::NegotiateBorderSpace

Rufen Sie diese Memberfunktion zum Rahmenbereichs in einem Rahmenfenster während der Aktivierung der OLE-Inplace aushandeln.

```
virtual BOOL NegotiateBorderSpace(
    UINT nBorderCmd,
    LPRECT lpRectBorder);
```

### <a name="parameters"></a>Parameter

*nBorderCmd*<br/>
Enthält einen der folgenden Werte aus der `enum BorderCmd`:

- `borderGet` = 1

- `borderRequest` = 2

- `borderSet` = 3

*lpRectBorder*<br/>
Zeiger auf eine [RECT](../../mfc/reference/rect-structure1.md) Struktur oder ein [CRect](../../atl-mfc-shared/reference/crect-class.md) -Objekt, das die Koordinaten des Rahmens angibt.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Diese Memberfunktion wird die `CFrameWnd` Implementierung von OLE Rahmen Speicherplatz Aushandlung.

##  <a name="onbarcheck"></a>  CFrameWnd::OnBarCheck

Aufgerufen, wenn eine Aktion für die angegebene Steuerleiste ausgeführt wird.

```
afx_msg BOOL OnBarCheck(UINT nID);
```

### <a name="parameters"></a>Parameter

*nID*<br/>
Die ID des Steuerelements Leiste angezeigt wird.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn die Steuerleiste vorhanden; andernfalls 0.

##  <a name="oncontexthelp"></a>  CFrameWnd::OnContextHelp

Verarbeitet die UMSCHALT + F1-Hilfe für ein direktes Elemente.

```
afx_msg void OnContextHelp();
```

### <a name="remarks"></a>Hinweise

Um kontextbezogene Hilfe zu aktivieren, müssen Sie fügen ein

[!code-cpp[NVC_MFCDocViewSDI#16](../../mfc/codesnippet/cpp/cframewnd-class_4.cpp)]

Anweisung, um Ihre `CFrameWnd` meldungszuordnung Klasse und einen Zugriffstastentabellen-Eintrag in der Regel UMSCHALT + F1 sind, aktivieren Sie diese Memberfunktion hinzufügen.

Wenn Ihre Anwendung mit einem OLE-Container ist `OnContextHelp` setzt alle in-Place-Elemente, die innerhalb der Frame-Window-Objekt in den Hilfemodus. Des Elementtextes ändert sich durch einen Pfeil und Fragezeichen gebildet und der Benutzer können dann zeigen Sie auf und drücken Sie die linke Maustaste gedrückt, um ein Dialogfeld, Fenster, Menü oder Befehlsschaltfläche auszuwählen. Diese Memberfunktion Ruft die Windows-Funktion `WinHelp` mit dem Hilfekontext des Objekts, unter dem Cursor.

##  <a name="oncreateclient"></a>  CFrameWnd::OnCreateClient

Vom Framework aufgerufen, während der Ausführung des `OnCreate`.

```
virtual BOOL OnCreateClient(
    LPCREATESTRUCT lpcs,
    CCreateContext* pContext);
```

### <a name="parameters"></a>Parameter

*LPCs*<br/>
Ein Zeiger auf ein Windows [CREATESTRUCT](../../mfc/reference/createstruct-structure.md) Struktur.

*"pContext"*<br/>
Ein Zeiger auf eine [CCreateContext](../../mfc/reference/ccreatecontext-structure.md) Struktur.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Rufen Sie diese Funktion nicht.

Die Standardimplementierung dieser Funktion erstellt eine `CView` Objekt aus den Angaben im *"pContext"*, sofern möglich.

Überschreiben Sie diese Funktion, um die übergebenen Werte außer Kraft setzen der `CCreateContext` Objekt oder So ändern Sie die Anzeige von Steuerelementen im Clientbereich des Rahmenfensters main erstellt werden. Die `CCreateContext` Mitglieder, die Sie überschreiben können, werden in beschrieben die [CCreateContext](../../mfc/reference/ccreatecontext-structure.md) Klasse.

> [!NOTE]
>  Nicht durch die übergebenen Werte ersetzen die `CREATESTRUCT` Struktur. Sie sind nur zu Informationszwecken. Wenn Sie das Fenster mit der Erstkonfiguration Rechteck außer Kraft setzen möchten, z. B. überschreiben die `CWnd` Memberfunktion [PreCreateWindow](../../mfc/reference/cwnd-class.md#precreatewindow).

##  <a name="onhidemenubar"></a>  CFrameWnd::OnHideMenuBar

Diese Funktion wird aufgerufen, wenn das System zum Ausblenden der Menüleiste in der aktuellen MFC-Anwendung ist.

```
virtual void OnHideMenuBar();
```

### <a name="remarks"></a>Hinweise

Dieser Ereignishandler kann es sich um die Anwendung aus, um benutzerdefinierte Aktionen auszuführen, wenn das System Begriff ist, klicken Sie im Menü ausgeblendet. Sie können nicht verhindern, dass Sie im Menü ausgeblendet, aber Sie können z. B. andere Methoden zum Abrufen von den Menüstil "oder" aufrufen.

##  <a name="onsetpreviewmode"></a>  CFrameWnd:: Onsetpreviewmode

Rufen Sie diese Memberfunktion auf, um für das Hauptrahmenfenster den Seitenansichtmodus zu aktivieren oder zu deaktivieren.

```
virtual void OnSetPreviewMode(
    BOOL bPreview,
    CPrintPreviewState* pState);
```

### <a name="parameters"></a>Parameter

*bPreview*<br/>
Gibt an, ob die Anwendung in den Seitenansicht-Modus zu platzieren. Festgelegt auf "true" in der Seitenansicht "false" zum Abbrechen der Vorschaumodus zu platzieren.

*pState*<br/>
Ein Zeiger auf eine `CPrintPreviewState` Struktur.

### <a name="remarks"></a>Hinweise

Die Standardimplementierung deaktiviert alle Standardsymbolleisten und blendet Sie aus dem Hauptmenü und des hauptclientfensters. Dadurch wird die MDI-Rahmenfenster in temporären SDI-Rahmenfenster.

Überschreiben Sie diese Memberfunktion zum Anpassen des ausblenden und die Anzeige des Schiebeleisten-Steuerelemente und andere Teile der Frame-Fensters der Seitenansicht an. Rufen Sie die basisklassenimplementierung von innerhalb der außer Kraft gesetzte Version.

##  <a name="onshowmenubar"></a>  CFrameWnd::OnShowMenuBar

Diese Funktion wird aufgerufen, wenn das System zum Anzeigen der Menüleiste in der aktuellen MFC-Anwendung ist.

```
virtual void OnShowMenuBar();
```

### <a name="remarks"></a>Hinweise

Dieser Ereignishandler kann es sich um die Anwendung aus, um benutzerdefinierte Aktionen auszuführen, bevor das Menü angezeigt wird. Sie können nicht verhindern, dass Sie im Menü angezeigt wird, aber Sie können z. B. andere Methoden zum Abrufen von den Menüstil "oder" aufrufen.

##  <a name="onupdatecontrolbarmenu"></a>  CFrameWnd::OnUpdateControlBarMenu

Vom Framework aufgerufen, wenn das zugeordnete Menü aktualisiert wird.

```
afx_msg void OnUpdateControlBarMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>Parameter

*nämlich pCmdUI*<br/>
Ein Zeiger auf eine [CCmdUI](../../mfc/reference/ccmdui-class.md) Objekt, das das Menü, das die Update-Befehl generiert darstellt. Ruft das Update der [aktivieren](../../mfc/reference/ccmdui-class.md#enable) Memberfunktion die `CCmdUI` -Objekt über *nämlich pCmdUI* zum Aktualisieren der Benutzeroberfläche.

##  <a name="recalclayout"></a>  CFrameWnd::RecalcLayout

Vom Framework aufgerufen, wenn die standardmäßige Steuerleisten ein- oder ausgeschaltet sind oder das Rahmenfenster geändert wird.

```
virtual void RecalcLayout(BOOL bNotify = TRUE);
```

### <a name="parameters"></a>Parameter

*bNotify*<br/>
Bestimmt, ob das aktive direkte-Element für das Rahmenfenster Benachrichtigung von der layoutänderung empfängt. Das Element wird benachrichtigt, wenn "true"; andernfalls "false".

### <a name="remarks"></a>Hinweise

Ruft die standardmäßige Implementierung von dieser Memberfunktion die `CWnd` Memberfunktion `RepositionBars` um die Steuerleisten im Frame sowie des hauptclientfensters neu (in der Regel eine `CView` oder MDICLIENT).

Überschreiben Sie diese Memberfunktion zum steuern das Aussehen und Verhalten von Steuerleisten, nachdem das Layout des Rahmenfensters geändert wurde. Rufen Sie es z. B. beim Aktivieren oder Deaktivieren von Steuerleisten oder beim Hinzufügen einer anderen Steuerleiste.

##  <a name="rectdefault"></a>  CFrameWnd::rectDefault

Übergeben Sie diese statische `CRect` als Parameter beim Erstellen eines Fensters, um Windows auf der anfänglichen Größe und Position des Fensters zu ermöglichen.

```
static AFX_DATA const CRect rectDefault;
```

##  <a name="savebarstate"></a>  SaveBarState

Rufen Sie diese Funktion zum Speichern von Informationen über jede Steuerleiste, die das Rahmenfenster gehören.

```
void SaveBarState(LPCTSTR lpszProfileName) const;
```

### <a name="parameters"></a>Parameter

*lpszProfileName*<br/>
Name des einen Abschnitt in der Initialisierungsdatei oder einen Schlüssel in der Windows-Registrierung, in dem Statusinformationen gespeichert ist.

### <a name="remarks"></a>Hinweise

Diese Informationen kann gelesen werden, aus der Initialisierung mithilfe [LoadBarState](#loadbarstate). Gespeicherten Informationen zählen die Sichtbarkeit, horizontaler/vertikaler Ausrichtung, andocken, Status und die Position des Steuerelements Leiste.

##  <a name="setactivepreviewview"></a>  CFrameWnd::SetActivePreviewView

Legt fest, die angegebene Ansicht die aktive Ansicht for Rich Preview sein.

```
void SetActivePreviewView(CView* pViewNew);
```

### <a name="parameters"></a>Parameter

*pViewNew*<br/>
Ein Zeiger auf eine Ansicht aktiviert werden.

### <a name="remarks"></a>Hinweise

##  <a name="setactiveview"></a>  CFrameWnd::SetActiveView

Rufen Sie diese Memberfunktion, um die aktive Ansicht festzulegen.

```
void SetActiveView(
    CView* pViewNew,
    BOOL bNotify = TRUE);
```

### <a name="parameters"></a>Parameter

*pViewNew*<br/>
Gibt einen Zeiger auf eine [CView](../../mfc/reference/cview-class.md) -Objekt oder NULL für nicht aktive Ansicht.

*bNotify*<br/>
Gibt an, ob die Ansicht der Aktivierung benachrichtigt zu werden. True gibt an, `OnActivateView` wird für die neue Sicht; aufgerufen, wenn es sich bei "false", es nicht ist.

### <a name="remarks"></a>Hinweise

Das Framework ruft diese Funktion automatisch wie der Benutzer den Fokus auf eine Ansicht innerhalb der Frame-Fensters ändert. Sie können explizit aufrufen, `SetActiveView` so ändern Sie den Fokus auf die angegebene Ansicht.

##  <a name="setdockstate"></a>  CFrameWnd::SetDockState

Rufen Sie diese Memberfunktion zum Anwenden von Zustandsinformationen, die in gespeicherten eine `CDockState` Objekt, das Rahmenfenster Schiebeleisten-Steuerelemente.

```
void SetDockState(const CDockState& state);
```

### <a name="parameters"></a>Parameter

*state*<br/>
Wenden Sie den gespeicherten Zustand, auf das Rahmenfenster Steuerleisten.

### <a name="remarks"></a>Hinweise

Um einen früheren Zustand der Steuerleisten wiederherzustellen, können Sie den gespeicherten Zustand laden `CDockState::LoadState` oder `Serialize`, verwenden Sie dann `SetDockState` für Schiebeleisten-Steuerelemente das Rahmenfenster übernehmen. Der vorherige Status befindet sich in der `CDockState` Objekt mit `GetDockState`

##  <a name="setmenubarstate"></a>  CFrameWnd::SetMenuBarState

Legt den Anzeigezustand des Menüs in der aktuellen MFC-Anwendung, die ausgeblendet oder angezeigt.

```
virtual BOOL SetMenuBarState(DWORD nState);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*nState*|[in] Gibt an, ob die Menü anzeigen oder ausblenden. Die *nState* Parameter kann die folgenden Werte aufweisen:<br /><br /> -AFX_MBS_VISIBLE (0 x 01) – zeigt das Menü an, wenn es ausgeblendet ist, aber Sie hat keine Auswirkungen, wenn es sichtbar ist.<br />-AFX_MBS_HIDDEN (0 x 02) – Blendet das Menü aus, wenn es sichtbar ist, aber Sie hat keine Auswirkungen, wenn es ausgeblendet ist.|

### <a name="return-value"></a>Rückgabewert

True, wenn diese Methode erfolgreich der Menü-Zustand ändert. andernfalls "false".

### <a name="remarks"></a>Hinweise

Wenn ein Laufzeitfehler auftritt, wird diese Methode Assert-Vorgänge im Debugmodus befinden, und löst eine Ausnahme, abgeleitet aus den [CException](../../mfc/reference/cexception-class.md) Klasse.

##  <a name="setmenubarvisibility"></a>  CFrameWnd::SetMenuBarVisibility

Legt das Standardverhalten des Menüs in der aktuellen MFC-Anwendung entweder ausgeblendet oder sichtbar sein.

```
virtual void SetMenuBarVisibility(DWORD nStyle);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*nStyle*|[in] Gibt an, ob im Menü standardmäßig ausgeblendet ist oder sichtbar ist und den Fokus besitzt. Die *nStyle* Parameter kann die folgenden Werte aufweisen:<br /><br /> -AFX_MBV_KEEPVISIBLE (0 X 01 –)<br />     Klicken Sie im Menü angezeigt wird, jederzeit und standardmäßig verfügt nicht über den Fokus.<br />-AFX_MBV_DISPLAYONFOCUS (0 X 02):<br />     Klicken Sie im Menü ist standardmäßig ausgeblendet. Wenn Sie im Menü ausgeblendet ist, drücken Sie ALT gedrückt, um das Menü anzuzeigen, und geben Sie ihm den Fokus. Wenn Sie im Menü angezeigt wird, drücken Sie die ALT-Taste oder die ESC-Taste So blenden Sie im Menü aus.<br />-AFX_MBV_ DISPLAYONFOCUS (0 x 02) &#124; AFX_MBV_DISPLAYONF10 (0 x 04)<br />     (bitweise Kombination (OR)) – klicken Sie im Menü ist standardmäßig ausgeblendet. Wenn Sie im Menü ausgeblendet ist, drücken Sie die Taste F10, um das Menü anzuzeigen, und geben Sie ihm den Fokus. Wenn Sie im Menü angezeigt wird, drücken Sie die Taste F10, um den Fokus aktivieren oder deaktivieren Sie im Menü zu wechseln. Klicken Sie im Menü wird angezeigt, bis Sie der ALT-Taste oder die ESC-Taste drücken, um es auszublenden.|

### <a name="remarks"></a>Hinweise

Wenn der Wert des der *nStyle* Parameter ungültig ist, im Debugmodus befindet und löst diese Methode bestätigt [CInvalidArgException](../../mfc/reference/cinvalidargexception-class.md) im Releasemodus. Bei andere Laufzeitfehler, diese Methode Assertionen im Debugmodus befindet und löst eine Ausnahme, abgeleitet aus den [CException](../../mfc/reference/cexception-class.md) Klasse.

Diese Methode wirkt sich auf den Zustand des Menüs in Anwendungen für Windows Vista und höher.

##  <a name="setmessagetext"></a>  CFrameWnd::SetMessageText

Rufen Sie diese Funktion, um eine Zeichenfolge in der Statusleiste zu platzieren, das eine ID von 0 hat.

```
void SetMessageText(LPCTSTR lpszText);
void SetMessageText(UINT nID);
```

### <a name="parameters"></a>Parameter

*lpszText*<br/>
Verweist auf die Zeichenfolge, die auf der Statusleiste platziert werden.

*nID*<br/>
Zeichenfolgenressourcen Sie-ID der Zeichenfolge auf der Statusleiste platziert werden.

### <a name="remarks"></a>Hinweise

Dies ist normalerweise der Bereich ganz links und am längsten, der Statusleiste.

##  <a name="setprogressbarposition"></a>  CFrameWnd::SetProgressBarPosition

Legt fest, die aktuelle Position für die Windows 7-Statusanzeige auf der Taskleiste angezeigt.

```
void SetProgressBarPosition(int nProgressPos);
```

### <a name="parameters"></a>Parameter

*nProgressPos*<br/>
Gibt die Position fest. Es muss sich innerhalb des Bereichs festlegen, indem `SetProgressBarRange`.

### <a name="remarks"></a>Hinweise

##  <a name="setprogressbarrange"></a>  CFrameWnd::SetProgressBarRange

Legt fest, den Bereich für die Windows 7-Statusanzeige auf der Taskleiste angezeigt.

```
void SetProgressBarRange(
    int nRangeMin,
    int nRangeMax);
```

### <a name="parameters"></a>Parameter

*nRangeMin*<br/>
Mindestwert.

*nRangeMax*<br/>
Dies ist die maximale Wert.

### <a name="remarks"></a>Hinweise

##  <a name="setprogressbarstate"></a>  CFrameWnd::SetProgressBarState

Legt fest, Typ und Status der Statusanzeige in der Taskleistenschaltfläche angezeigt.

```
void SetProgressBarState(TBPFLAG tbpFlags);
```

### <a name="parameters"></a>Parameter

*tbpFlags*<br/>
Flags, die den aktuellen Zustand der Schaltfläche des Vorgangs zu steuern. Geben Sie nur eine der folgenden flags, da alle Zustände gegenseitig: TBPF_NOPROGRESS, TBPF_INDETERMINATE, TBPF_NORMAL, TBPF_ERROR, TBPF_PAUSED.

### <a name="remarks"></a>Hinweise

##  <a name="settaskbaroverlayicon"></a>  CFrameWnd::SetTaskbarOverlayIcon

Überladen. Gilt eine Überlagerung auf eine Taskleistenschaltfläche um Status der Anwendung oder den Benutzer zu benachrichtigen.

```
BOOL SetTaskbarOverlayIcon(
    UINT nIDResource,
    LPCTSTR lpcszDescr);


BOOL SetTaskbarOverlayIcon(
    HICON hIcon,
    LPCTSTR lpcszDescr);
```

### <a name="parameters"></a>Parameter

*nIDResource*<br/>
Gibt an, die Ressourcen-ID eines Symbols als das Overlay verwendet. Siehe Beschreibung für *hIcon* Details.

*lpcszDescr*<br/>
Ein Zeiger auf eine Zeichenfolge, die eine Alt-Text-Version von das Overlay an, aus Gründen der Barrierefreiheit Menüsteuerelementen übermittelte Informationen bereitstellt.

*hIcon*<br/>
Das Handle eines Symbols als das Overlay verwendet werden soll. Dies sollte ein kleines Symbol, das Messen von 16 x 16 Pixel bei 96 dpi (Dots per Inch) sein. Wenn ein Überlagerungssymbol, das bereits auf die Schaltfläche "Taskleiste" angewendet wird, wird diese vorhandenen Überlagerung ersetzt. Dieser Wert kann NULL sein. Wie ein NULL-Wert behandelt wird, hängt davon ab, ob die Taskleistenschaltfläche für ein einziges Fenster oder eine Gruppe von Windows darstellt. Es liegt in der Verantwortung der aufrufenden Anwendung freigeben *hIcon* Wenn es nicht mehr benötigt wird.

### <a name="return-value"></a>Rückgabewert

True, wenn erfolgreich; "False", wenn Version des Betriebssystems kleiner als Windows 7 ist, oder wenn ein Fehler auftritt, Festlegen des Symbols.

### <a name="remarks"></a>Hinweise

##  <a name="settitle"></a>  CFrameWnd::SetTitle

Legt den Titel des Window-Objekts fest.

```
void SetTitle(LPCTSTR lpszTitle);
```

### <a name="parameters"></a>Parameter

*lpszTitle*<br/>
Ein Zeiger auf eine Zeichenfolge, die mit dem Titel des Window-Objekts.

##  <a name="showcontrolbar"></a>  CFrameWnd::ShowControlBar

Rufen Sie diese Memberfunktion zum Anzeigen oder Ausblenden der Steuerleiste.

```
void ShowControlBar(
    CControlBar* pBar,
    BOOL bShow,
    BOOL bDelay);
```

### <a name="parameters"></a>Parameter

*pBar*<br/>
Zeiger auf der Steuerleiste angezeigt oder ausgeblendet werden.

*bShow*<br/>
Wenn "true" gibt an, dass die Steuerleiste angezeigt werden. Wenn "FALSE" gibt an, dass die Steuerleiste ausgeblendet werden.

*bDelay*<br/>
True gibt an, verzögern Sie die Steuerleiste angezeigt. False gibt an, zeigen Sie die Steuerleiste sofort.

##  <a name="showownedwindows"></a>  CFrameWnd::ShowOwnedWindows

Rufen Sie diese Memberfunktion, um alle Fenster anzuzeigen, die Nachfolger der `CFrameWnd` Objekt.

```
void ShowOwnedWindows(BOOL bShow);
```

### <a name="parameters"></a>Parameter

*bShow*<br/>
Gibt an, ob die im Besitz des Benutzers Fenster sind, angezeigt oder ausgeblendet werden.

## <a name="see-also"></a>Siehe auch

[CWnd-Klasse](../../mfc/reference/cwnd-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CWnd-Klasse](../../mfc/reference/cwnd-class.md)<br/>
[CMDIFrameWnd-Klasse](../../mfc/reference/cmdiframewnd-class.md)<br/>
[CMDIChildWnd-Klasse](../../mfc/reference/cmdichildwnd-class.md)<br/>
[CView-Klasse](../../mfc/reference/cview-class.md)<br/>
[CDocTemplate-Klasse](../../mfc/reference/cdoctemplate-class.md)<br/>
[CRuntimeClass-Struktur](../../mfc/reference/cruntimeclass-structure.md)

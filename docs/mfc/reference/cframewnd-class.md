---
title: CFrameWnd-Klasse
ms.date: 11/04/2016
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
ms.openlocfilehash: d2e043c8c9f4ad86636cd0e9ea7d695826b6c8fb
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69506961"
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
|[CFrameWnd::ActivateFrame](#activateframe)|Macht den Frame sichtbar und ist für den Benutzer verfügbar.|
|[CFrameWnd::BeginModalState](#beginmodalstate)|Legt das Rahmen Fenster auf Modal fest.|
|[CFrameWnd::Create](#create)|Rufen Sie auf, um das dem- `CFrameWnd` Objekt zugeordnete Windows-Rahmen Fenster zu erstellen und zu initialisieren.|
|[CFrameWnd::CreateView](#createview)|Erstellt eine Ansicht innerhalb eines Frames, der nicht von `CView`abgeleitet ist.|
|[CFrameWnd::DockControlBar](#dockcontrolbar)|Dockt eine Steuerleiste an.|
|[CFrameWnd::EnableDocking](#enabledocking)|Ermöglicht, dass eine Steuerleiste angedockt wird.|
|[CFrameWnd::EndModalState](#endmodalstate)|Beendet den modalen Zustand des Rahmen Fensters. Aktiviert alle Fenster, die von deaktiviert `BeginModalState`werden.|
|[CFrameWnd::FloatControlBar](#floatcontrolbar)|Schwebt eine Steuerleiste.|
|[CFrameWnd::GetActiveDocument](#getactivedocument)|Gibt das aktive `CDocument` -Objekt zurück.|
|[CFrameWnd::GetActiveFrame](#getactiveframe)|Gibt das aktive `CFrameWnd` -Objekt zurück.|
|[CFrameWnd::GetActiveView](#getactiveview)|Gibt das aktive `CView` -Objekt zurück.|
|[CFrameWnd::GetControlBar](#getcontrolbar)|Ruft die Steuerleiste ab.|
|[CFrameWnd::GetDockState](#getdockstate)|Ruft den Andock Zustand eines Rahmen Fensters ab.|
|[CFrameWnd::GetMenuBarState](#getmenubarstate)|Ruft den Anzeige Zustand des Menüs in der aktuellen MFC-Anwendung ab.|
|[CFrameWnd::GetMenuBarVisibility](#getmenubarvisibility)|Gibt an, ob das Standardverhalten des Menüs in der aktuellen MFC-Anwendung entweder ausgeblendet oder sichtbar ist.|
|[CFrameWnd::GetMessageBar](#getmessagebar)|Gibt einen Zeiger auf die Statusleiste zurück, die zum Rahmen Fenster gehört.|
|[CFrameWnd::GetMessageString](#getmessagestring)|Ruft eine Meldung ab, die einer Befehls-ID entspricht.|
|[CFrameWnd::GetTitle](#gettitle)|Ruft den Titel der zugehörigen Steuerleiste ab.|
|[CFrameWnd::InitialUpdateFrame](#initialupdateframe)|Bewirkt, `OnInitialUpdate` dass die Member-Funktion, die zu allen Ansichten im Rahmen Fenster gehört, aufgerufen wird.|
|[CFrameWnd::InModalState](#inmodalstate)|Gibt einen Wert zurück, der angibt, ob sich ein Rahmen Fenster in einem modalen Zustand befindet.|
|[CFrameWnd:: istracking](#istracking)|Bestimmt, ob die Splitter Leiste gerade verschoben wird.|
|[CFrameWnd::LoadAccelTable](#loadacceltable)|Ruft auf, um eine Zugriffstasten Tabelle zu laden.|
|[CFrameWnd::LoadBarState](#loadbarstate)|Ruft auf, um die Einstellungen der Steuerleiste wiederherzustellen.|
|[CFrameWnd::LoadFrame](#loadframe)|Rufen Sie auf, um ein Rahmen Fenster dynamisch aus den Ressourcen Informationen zu erstellen.|
|[CFrameWnd::NegotiateBorderSpace](#negotiateborderspace)|Aushandiert den Rahmen Bereich im Rahmen Fenster.|
|[CFrameWnd::OnBarCheck](#onbarcheck)|Wird aufgerufen, wenn eine Aktion auf der angegebenen Steuerleiste ausgeführt wird.|
|[CFrameWnd::OnContextHelp](#oncontexthelp)|Behandelt die UMSCHALT + F1-Hilfe für direkte Elemente.|
|[CFrameWnd::OnSetPreviewMode](#onsetpreviewmode)|Legt das Hauptrahmen Fenster der Anwendung in den Druck-/ansichtenmodus fest.|
|[CFrameWnd::OnUpdateControlBarMenu](#onupdatecontrolbarmenu)|Wird von Framework aufgerufen, wenn das zugehörige Menü aktualisiert wird.|
|[CFrameWnd::RecalcLayout](#recalclayout)|Positioniert die Steuer leisten des `CFrameWnd` -Objekts neu.|
|[CFrameWnd::SaveBarState](#savebarstate)|Ruft auf, um Steuer leisten Einstellungen zu speichern.|
|[CFrameWnd::SetActivePreviewView](#setactivepreviewview)|Legt die angegebene Ansicht als aktive Ansicht für die umfangreiche Vorschau fest.|
|[CFrameWnd::SetActiveView](#setactiveview)|Legt das aktive `CView` -Objekt fest.|
|[CFrameWnd::SetDockState](#setdockstate)|Ruft auf, um das Rahmen Fenster im Hauptfenster anzudocken.|
|[CFrameWnd::SetMenuBarState](#setmenubarstate)|Legt den Anzeige Zustand des Menüs in der aktuellen MFC-Anwendung auf ausgeblendet oder angezeigt fest.|
|[CFrameWnd::SetMenuBarVisibility](#setmenubarvisibility)|Legt das Standardverhalten des Menüs in der aktuellen MFC-Anwendung als ausgeblendet oder sichtbar fest.|
|[CFrameWnd::SetMessageText](#setmessagetext)|Legt den Text einer Standardstatus Leiste fest.|
|[CFrameWnd::SetProgressBarPosition](#setprogressbarposition)|Legt die aktuelle Position für die Windows 7-Statusanzeige auf der Taskleiste fest.|
|[CFrameWnd::SetProgressBarRange](#setprogressbarrange)|Legt den Bereich für die auf der Taskleiste angezeigte Statusleiste von Windows 7 fest.|
|[CFrameWnd::SetProgressBarState](#setprogressbarstate)|Legt den Typ und den Zustand der Statusanzeige fest, die auf einer Task leisten Schaltfläche angezeigt wird.|
|[CFrameWnd::SetTaskbarOverlayIcon](#settaskbaroverlayicon)|Überladen. Wendet ein Overlay auf eine Task leisten Schaltfläche an, um den Anwendungs Status oder eine Benachrichtigung an den Benutzer anzugeben.|
|[CFrameWnd::SetTitle](#settitle)|Legt den Titel der zugehörigen Steuerleiste fest.|
|[CFrameWnd::ShowControlBar](#showcontrolbar)|Ruft auf, um die Steuerleiste anzuzeigen.|
|[CFrameWnd::ShowOwnedWindows](#showownedwindows)|Zeigt alle Fenster an, die Nachfolger des `CFrameWnd` -Objekts sind.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CFrameWnd::OnCreateClient](#oncreateclient)|Erstellt ein Client Fenster für den Frame.|
|[CFrameWnd::OnHideMenuBar](#onhidemenubar)|Wird aufgerufen, bevor das Menü in der aktuellen MFC-Anwendung ausgeblendet wird.|
|[CFrameWnd::OnShowMenuBar](#onshowmenubar)|Wird aufgerufen, bevor das Menü in der aktuellen MFC-Anwendung angezeigt wird.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CFrameWnd::m_bAutoMenuEnable](#m_bautomenuenable)|Steuert die automatische Aktivierung und Deaktivierung von Menü Elementen.|
|[CFrameWnd::rectDefault](#rectdefault)|Übergeben Sie dieses `CRect` static als Parameter, wenn Sie `CFrameWnd` ein-Objekt erstellen, damit Windows die anfängliche Größe und Position des Fensters auswählen kann.|

## <a name="remarks"></a>Hinweise

Um ein nützliches Rahmen Fenster für die Anwendung zu erstellen, leiten Sie eine `CFrameWnd`Klasse von ab. Fügen Sie der abgeleiteten Klasse Element Variablen hinzu, um Daten zu speichern, die für Ihre Anwendung spezifisch sind. Implementieren Sie Meldungshandler-Memberfunktionen und eine Meldungszuordnung in der abgeleiteten Klasse, um anzugeben, was passiert, wenn Meldungen an das Fenster weitergeleitet werden.

Es gibt drei Möglichkeiten, ein Rahmen Fenster zu erstellen:

- Erstellen Sie diese mithilfe von [Create](#create)direkt.

- Erstellen Sie es direkt mithilfe von [LoadFrame](#loadframe).

- Erstellen Sie es indirekt mit einer Dokument Vorlage.

Vor dem Abrufen `Create` von oder `LoadFrame`müssen Sie das Rahmen Fenster Objekt auf dem Heap mit dem C++ **New** -Operator erstellen. Vor dem `Create`Aufrufen von können Sie auch eine Fenster Klasse mit der globalen Funktion [AfxRegisterWndClass](../../mfc/reference/application-information-and-management.md#afxregisterwndclass) registrieren, um das Symbol und die Klassen Stile für den Frame festzulegen.

Verwenden Sie `Create` die Member-Funktion, um die Erstellungs Parameter des Frames als unmittelbare Argumente zu übergeben.

`LoadFrame`erfordert weniger Argumente als `Create`und ruft stattdessen die meisten Standardwerte aus Ressourcen ab, einschließlich der Beschriftung, des Symbols, der Zugriffstasten Tabelle und des Menüs des Frames. Um auf zugreifen zu `LoadFrame`können, müssen alle diese Ressourcen dieselbe Ressourcen-ID aufweisen (z. b. IDR_MAINFRAME).

Wenn ein `CFrameWnd` -Objekt Sichten und Dokumente enthält, werden diese indirekt durch das Framework anstatt direkt vom Programmierer erstellt. Das `CDocTemplate` -Objekt orchestriert die Erstellung des Frames, die Erstellung der enthaltenden Sichten und die Verbindung der Ansichten mit dem entsprechenden Dokument. Die Parameter des `CDocTemplate` -Konstruktors geben den `CRuntimeClass` der drei beteiligten Klassen an (Dokument, Rahmen und Ansicht). Ein `CRuntimeClass` -Objekt wird vom Framework verwendet, um neue Frames dynamisch zu erstellen, wenn Sie vom Benutzer angegeben werden (z. b. mit dem Befehl Datei New oder dem MDI-Fenster (Multiple Document Interface) neu).

Eine von `CFrameWnd` abgeleitete Frame-Window-Klasse muss mit DECLARE_DYNCREATE deklariert werden, damit der obige RUNTIME_CLASS-Mechanismus ordnungsgemäß funktioniert.

Ein `CFrameWnd` enthält Standard Implementierungen, mit denen die folgenden Funktionen eines Hauptfensters in einer typischen Anwendung für Windows durchgeführt werden können:

- Ein `CFrameWnd` Rahmen Fenster verfolgt eine derzeit aktive Ansicht, die vom aktiven Windows-Fenster oder dem aktuellen Eingabefokus unabhängig ist. Wenn der Frame reaktiviert wird, wird die aktive Ansicht durch Aufrufen `CView::OnActivateView`von benachrichtigt.

- Befehlsnachrichten und viele allgemeine Frame Benachrichtigungs Meldungen, einschließlich derjenigen, die von `OnSetFocus`den `OnHScroll`Funktionen, `OnVScroll` und von `CWnd`verarbeitet werden, werden von `CFrameWnd` einem Rahmen Fenster an die derzeit aktive Ansicht delegiert.

- Die derzeit aktive Ansicht (oder derzeit aktives untergeordnetes MDI-Rahmen Fenster im Fall eines MDI-Frames) kann die Beschriftung des Rahmen Fensters bestimmen. Diese Funktion kann deaktiviert werden, indem Sie das FWS_ADDTOTITLE-Stilbit des Rahmen Fensters ausschalten.

- Ein `CFrameWnd` Rahmen Fenster verwaltet die Positionierung der Steuer leisten, Ansichten und anderen untergeordneten Fenster im Client Bereich des Rahmen Fensters. Ein Rahmen Fenster führt außerdem eine Leerlaufzeit Aktualisierung der Symbolleiste und anderer Steuer leisten Schaltflächen aus. Ein `CFrameWnd` Rahmen Fenster verfügt auch über Standard Implementierungen von Befehlen zum Umschalten und Deaktivieren der Symbolleiste und der Statusleiste.

- Ein `CFrameWnd` Rahmen Fenster verwaltet die Hauptmenüleiste. Wenn ein Popup Menü angezeigt wird, verwendet das Rahmen Fenster den UPDATE_COMMAND_UI-Mechanismus, um zu bestimmen, welche Menü Elemente aktiviert, deaktiviert oder aktiviert werden sollen. Wenn der Benutzer ein Menü Element auswählt, aktualisiert das Rahmen Fenster die Statusleiste mit der Meldungs Zeichenfolge für diesen Befehl.

- Ein `CFrameWnd` Rahmen Fenster verfügt über eine optionale Zugriffstasten Tabelle, mit der Tastaturbeschleuniger automatisch übersetzt werden.

- Ein `CFrameWnd` Rahmen Fenster verfügt über eine optionale Hilfe-ID `LoadFrame` , die für die kontextbezogene Hilfe verwendet wird. Ein Rahmen Fenster ist der hauptorchestrator von semimodalen Zuständen, z. b. kontextabhängige Hilfe (UMSCHALT + F1) und Druck-Vorschau-Modi.

- Ein `CFrameWnd` Rahmen Fenster öffnet eine aus dem Datei-Manager gezogene Datei und wird im Rahmen Fenster abgelegt. Wenn eine Dateierweiterung registriert und der Anwendung zugeordnet ist, antwortet das Rahmen Fenster auf die Anforderung zum Öffnen von dynamischem Datenaustausch (DDE), die auftritt, wenn der Benutzer eine Datendatei im Datei-Manager `ShellExecute` öffnet oder wenn die Windows-Funktion aufgerufen wird.

- Wenn das Rahmen Fenster das Hauptanwendungsfenster ( `CWinThread::m_pMainWnd`d. h.) ist und der Benutzer die Anwendung schließt, wird der Benutzer vom Rahmen Fenster aufgefordert, geänderte Dokumente (für `OnClose` und `OnQueryEndSession`) zu speichern.

- Wenn das Rahmen Fenster das Hauptanwendungsfenster ist, ist das Rahmen Fenster der Kontext zum Ausführen von WinHelp. Wenn Sie das Rahmen Fenster schließen, wird WinHelp heruntergefahren. EXE, wenn es für die Hilfe für diese Anwendung gestartet wurde.

Verwenden Sie nicht den C++ **Delete** -Operator, um ein Rahmen Fenster zu zerstören. Verwenden Sie stattdessen `CWnd::DestroyWindow`. Die `CFrameWnd` Implementierung von `PostNcDestroy` löscht das C++ -Objekt, wenn das Fenster zerstört wird. Wenn der Benutzer das Rahmen Fenster schließt, ruft `OnClose` `DestroyWindow`der Standard Handler auf.

Weitere Informationen zu `CFrameWnd`finden Sie unter [Rahmen Fenster](../../mfc/frame-windows.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CFrameWnd`

## <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

##  <a name="activateframe"></a>CFrameWnd:: activateframe

Mit dieser Member-Funktion können Sie das Rahmen Fenster aktivieren und wiederherstellen, sodass es für den Benutzer sichtbar und verfügbar ist.

```
virtual void ActivateFrame(int nCmdShow = -1);
```

### <a name="parameters"></a>Parameter

*nCmdShow*<br/>
Gibt den Parameter an, der an [CWnd:: ShowWindow](../../mfc/reference/cwnd-class.md#showwindow)übergeben werden soll. Standardmäßig wird der Frame angezeigt und ordnungsgemäß wieder hergestellt.

### <a name="remarks"></a>Hinweise

Diese Member-Funktion wird in der Regel nach einem nicht-Benutzeroberflächen Ereignis aufgerufen, z. b. einem DDE-, OLE-oder anderen Ereignis, das das Rahmen Fenster oder seinen Inhalt für den Benutzer anzeigen kann.

Die Standard Implementierung aktiviert den Frame und bringt ihn am Anfang der Z-Reihenfolge und bei Bedarf die gleichen Schritte für das Hauptrahmen Fenster der Anwendung aus.

Überschreiben Sie diese Member-Funktion, um zu ändern, wie ein Frame aktiviert wird. Beispielsweise können Sie erzwingen, dass untergeordnete MDI-Fenster maximiert werden. Fügen Sie die entsprechende Funktionalität hinzu, und nennen Sie dann die Basisklassen Version mit einem expliziten *nCmdShow*.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#1](../../mfc/reference/codesnippet/cpp/cframewnd-class_1.cpp)]

##  <a name="beginmodalstate"></a>CFrameWnd:: beginmodalstate

Rufen Sie diese Memberfunktion auf, um ein Framefenster modal zu machen.

```
virtual void BeginModalState();
```

##  <a name="cframewnd"></a>CFrameWnd:: CFrameWnd

Erstellt ein `CFrameWnd` -Objekt, erstellt jedoch nicht das sichtbare Rahmen Fenster.

```
CFrameWnd();
```

### <a name="remarks"></a>Hinweise

Rufen `Create` Sie auf, um das sichtbare Fenster zu erstellen.

##  <a name="create"></a>CFrameWnd:: Create

Rufen Sie auf, um das dem- `CFrameWnd` Objekt zugeordnete Windows-Rahmen Fenster zu erstellen und zu initialisieren.

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

*lpszClassName*<br/>
Verweist auf eine mit NULL endenden Zeichenfolge, die die Windows-Klasse benennt. Der Klassenname kann ein beliebiger Name sein, `AfxRegisterWndClass` der bei der globalen `RegisterClass` Funktion oder der Windows-Funktion registriert ist. Wenn NULL, verwendet die vordefinierten Standard `CFrameWnd` Attribute.

*lpszWindowName*<br/>
Verweist auf eine mit NULL endenden Zeichenfolge, die den Fensternamen darstellt. Wird als Text für die Titelleiste verwendet.

*dwStyle*<br/>
Gibt die Fenster [Stil](../../mfc/reference/styles-used-by-mfc.md#window-styles) Attribute an. Fügen Sie den FWS_ADDTOTITLE-Stil ein, wenn in der Titelleiste automatisch der Name des Dokuments angezeigt werden soll, das im Fenster dargestellt wird.

*Rect*<br/>
Gibt die Größe und Position des Fensters an. Der *rectdefault* -Wert ermöglicht es Windows, die Größe und Position des neuen Fensters anzugeben.

*pParentWnd*<br/>
Gibt das übergeordnete Fenster dieses Rahmen Fensters an. Dieser Parameter sollte für Rahmen Fenster der obersten Ebene Null sein.

*lpszMenuName*<br/>
Identifiziert den Namen der Menü Ressource, die mit dem Fenster verwendet werden soll. Verwenden Sie makeintresource, wenn das Menü eine ganzzahlige ID anstelle einer Zeichenfolge aufweist. Dieser Parameter kann NULL sein.

*dwExStyle*<br/>
Gibt das Fenster Erweiterte [Stil](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles) Attribute an.

*pContext*<br/>
Gibt einen Zeiger auf eine [ckreatecontext](../../mfc/reference/ccreatecontext-structure.md) -Struktur an. Dieser Parameter kann NULL sein.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Initialisierung erfolgreich ist. andernfalls 0.

### <a name="remarks"></a>Hinweise

Erstellen Sie `CFrameWnd` ein-Objekt in zwei Schritten. Rufen Sie zuerst den-Konstruktor auf, der `CFrameWnd` das-Objekt erstellt, `Create`und rufen Sie dann auf, wodurch das Windows-Rahmen Fenster `CFrameWnd` erstellt und an das-Objekt angefügt wird. `Create`Initialisiert den Klassennamen und den Fensternamen des Fensters und registriert die Standardwerte für den Stil, das übergeordnete Element und das zugehörige Menü.

Verwenden `LoadFrame`Sieanstellevon ,umdasRahmenFensterauseinerRessourcezuladen,anstattderenArgumenteanzugeben.`Create`

##  <a name="createview"></a>CFrameWnd:: ansichtsansicht

Rufen `CreateView` Sie auf, um eine Ansicht innerhalb eines Frames zu erstellen.

```
CWnd* CreateView(
    CCreateContext* pContext,
    UINT nID = AFX_IDW_PANE_FIRST);
```

### <a name="parameters"></a>Parameter

*pContext*<br/>
Gibt den Typ der Ansicht und des Dokuments an.

*nID*<br/>
Die ID-Nummer einer Ansicht.

### <a name="return-value"></a>Rückgabewert

Zeiger auf ein `CWnd` -Objekt, wenn erfolgreich; andernfalls NULL.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Member-Funktion, um Ansichten zu erstellen, `CView`die nicht innerhalb eines Frames abgeleitet werden. Nachdem Sie `CreateView`aufgerufen haben, müssen Sie die Ansicht manuell auf "aktiv" festlegen und Sie als sichtbar festlegen. diese Aufgaben werden von `CreateView`nicht automatisch ausgeführt.

##  <a name="dockcontrolbar"></a>CFrameWnd::D ockcontrolbar

Bewirkt, dass eine Steuerleiste an das Rahmen Fenster angedockt wird.

```
void DockControlBar(
    CControlBar* pBar,
    UINT nDockBarID = 0,
    LPCRECT lpRect = NULL);
```

### <a name="parameters"></a>Parameter

*pBar*<br/>
Zeigt auf die Steuerleiste, die angedockt werden soll.

*nDockBarID*<br/>
Bestimmt, welche Seiten des Rahmen Fensters zum Andocken zu beachten sind. Der Wert kann 0 oder eine oder mehrere der folgenden sein:

- AFX_IDW_DOCKBAR_TOP Andocken an der oberen Seite des Rahmen Fensters.

- AFX_IDW_DOCKBAR_BOTTOM an die untere Seite des Rahmen Fensters andocken.

- AFX_IDW_DOCKBAR_LEFT Andocken auf der linken Seite des Rahmen Fensters.

- AFX_IDW_DOCKBAR_RIGHT Andocken an der rechten Seite des Rahmen Fensters.

Wenn der Wert 0 ist, kann die Steuerleiste an jede beliebige Seite angedockt werden, die im Zielrahmen Fenster Andocken aktiviert ist.

*lpRect*<br/>
Bestimmt in Bildschirm Koordinaten, wo die Steuerleiste im nicht-Client Bereich des Zielrahmen Fensters angedockt wird.

### <a name="remarks"></a>Hinweise

Die Steuerleiste wird an eine der Seiten des Rahmen Fensters angedockt, das in den Aufrufen von [CControlBar:: EnableDocking](../../mfc/reference/ccontrolbar-class.md#enabledocking) und [CFrameWnd:: EnableDocking](#enabledocking)angegeben ist. Die gewählte Seite wird von *ndockbarid*bestimmt.

##  <a name="enabledocking"></a>CFrameWnd:: EnableDocking

Diese Funktion wird aufgerufen, um andockbare Steuer leisten in einem Rahmen Fenster zu aktivieren.

```
void EnableDocking(DWORD dwDockStyle);
```

### <a name="parameters"></a>Parameter

*dwDockStyle*<br/>
Gibt an, welche Seiten des Rahmen Fensters als andockbare Standorte für Steuer leisten fungieren können. Dabei kann es sich um eine oder mehrere der folgenden handeln:

- CBRS_ALIGN_TOP ermöglicht das Andocken am oberen Rand des Client Bereichs.

- CBRS_ALIGN_BOTTOM ermöglicht das Andocken am unteren Rand des Client Bereichs.

- CBRS_ALIGN_LEFT ermöglicht das Andocken auf der linken Seite des Client Bereichs.

- CBRS_ALIGN_RIGHT ermöglicht das Andocken auf der rechten Seite des Client Bereichs.

- CBRS_ALIGN_ANY ermöglicht das Andocken auf einer beliebigen Seite des Client Bereichs.

### <a name="remarks"></a>Hinweise

Standardmäßig werden Steuer leisten an eine Seite des Rahmen Fensters in der folgenden Reihenfolge angedockt: oben, unten, Links, rechts.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [CToolBar:: Create](../../mfc/reference/ctoolbar-class.md#create).

##  <a name="endmodalstate"></a>CFrameWnd:: endmodalstate

Rufen Sie diese Memberfunktion auf, um ein Framefenster von einem modalen in einen Status ohne Modus zu ändern.

```
virtual void EndModalState();
```

### <a name="remarks"></a>Hinweise

`EndModalState`aktiviert alle Fenster, die von [beginmodalstate](#beginmodalstate)deaktiviert werden.

##  <a name="floatcontrolbar"></a>CFrameWnd:: FloatControlBar

Mit dieser Funktion können Sie bewirken, dass eine Steuerleiste nicht an das Rahmen Fenster angedockt wird.

```
void FloatControlBar(
    CControlBar* pBar,
    CPoint point,
    DWORD dwStyle = CBRS_ALIGN_TOP);
```

### <a name="parameters"></a>Parameter

*pBar*<br/>
Zeigt auf die zu verwendende Steuerleiste.

*point*<br/>
Die Position in Bildschirm Koordinaten, an der die linke obere Ecke der Steuerleiste platziert wird.

*dwStyle*<br/>
Gibt an, ob die Steuerleiste horizontal oder vertikal innerhalb des neuen Rahmen Fensters ausgerichtet werden soll. Dabei kann es sich um einen der folgenden handeln:

- CBRS_ALIGN_TOP orientiert die Steuerleiste vertikal.

- CBRS_ALIGN_BOTTOM orientiert die Steuerleiste vertikal.

- CBRS_ALIGN_LEFT orientiert die Steuerleiste horizontal an.

- CBRS_ALIGN_RIGHT orientiert die Steuerleiste horizontal an.

Wenn Stile an die horizontale und vertikale Ausrichtung übermittelt werden, wird die Symbolleiste horizontal ausgerichtet.

### <a name="remarks"></a>Hinweise

Dies erfolgt in der Regel beim Starten der Anwendung, wenn das Programmeinstellungen aus der vorherigen Ausführung wiederherstellt.

Diese Funktion wird vom Framework aufgerufen, wenn der Benutzer einen Drop-Vorgang auslöst, indem die linke Maustaste losgelassen wird, während die Steuerleiste über einen Speicherort, der nicht zum Andocken verfügbar ist, gezogen wird.

##  <a name="getactivedocument"></a>CFrameWnd:: GetActiveDocument

Rufen Sie diese Member-Funktion auf, um einen Zeiger `CDocument` auf den aktuellen zu erhalten, der der aktuellen aktiven Ansicht zugeordnet ist.

```
virtual CDocument* GetActiveDocument();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das aktuelle [CDocument](../../mfc/reference/cdocument-class.md). Wenn kein Aktuelles Dokument vorhanden ist, wird NULL zurückgegeben.

##  <a name="getactiveframe"></a>CFrameWnd:: GetActiveFrame

Rufen Sie diese Member-Funktion auf, um einen Zeiger auf das aktive untergeordnete MDI-Fenster (Multiple Document Interface) eines MDI-Rahmen Fensters zu erhalten.

```
virtual CFrameWnd* GetActiveFrame();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das aktive untergeordnete MDI-Fenster. Wenn es sich bei der Anwendung um eine SDI-Anwendung handelt oder das MDI-Rahmen Fenster kein aktives Dokument enthält, wird der implizite **this** -Zeiger zurückgegeben.

### <a name="remarks"></a>Hinweise

Wenn kein aktives untergeordnetes MDI-Element vorhanden ist oder es sich bei der Anwendung um eine Single Document Interface (SDI) handelt, wird der implizite **this** -Zeiger zurückgegeben.

##  <a name="getactiveview"></a>CFrameWnd:: GetActiveView

Rufen Sie diese Member-Funktion auf, um einen Zeiger auf die aktive Ansicht (sofern vorhanden) zu erhalten, `CFrameWnd`die an ein Rahmen Fenster () angefügt ist.

```
CView* GetActiveView() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die aktuelle [CView](../../mfc/reference/cview-class.md). Wenn keine aktuelle Ansicht vorhanden ist, wird NULL zurückgegeben.

### <a name="remarks"></a>Hinweise

Diese Funktion gibt NULL zurück, wenn Sie für ein MDI-Haupt `CMDIFrameWnd`Rahmen Fenster () aufgerufen wird. In einer MDI-Anwendung ist dem MDI-Hauptrahmen Fenster keine Ansicht zugeordnet. Stattdessen verfügt jedes einzelne untergeordnete Fenster `CMDIChildWnd`() über eine oder mehrere zugeordnete Sichten. Die aktive Ansicht in einer MDI-Anwendung kann abgerufen werden, indem Sie zuerst das aktive untergeordnete MDI-Fenster Suchen und dann die aktive Ansicht für dieses untergeordnete Fenster suchen. Das aktive untergeordnete MDI-Fenster kann gefunden werden, indem `MDIGetActive` Sie `GetActiveFrame` die-Funktion aufrufen oder wie im folgenden gezeigt:

[!code-cpp[NVC_MFCWindowing#2](../../mfc/reference/codesnippet/cpp/cframewnd-class_2.cpp)]

##  <a name="getcontrolbar"></a>CFrameWnd:: getcontrolbar

Aufrufen `GetControlBar` , um Zugriff auf die Steuerleiste zu erhalten, die mit der ID verknüpft ist.

```
CControlBar* GetControlBar(UINT nID);
```

### <a name="parameters"></a>Parameter

*nID*<br/>
Die ID-Nummer einer Steuerleiste.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die Steuerleiste, die der ID zugeordnet ist.

### <a name="remarks"></a>Hinweise

Der *NID* -Parameter verweist auf den eindeutigen Bezeichner, `Create` der an die-Methode der Steuerleiste übergeben wird. Weitere Informationen zu Steuer leisten finden Sie im Thema [Steuer leisten](../../mfc/control-bars.md).

`GetControlBar`Gibt die Steuerleiste zurück, auch wenn Sie unverankert ist und daher derzeit kein untergeordnetes Fenster des Frames ist.

##  <a name="getdockstate"></a>CFrameWnd:: getdockstate

Mit dieser Member-Funktion werden Zustandsinformationen zu den Steuer leisten des Rahmen Fensters in einem `CDockState` -Objekt gespeichert.

```
void GetDockState(CDockState& state) const;
```

### <a name="parameters"></a>Parameter

*state*<br/>
Enthält den aktuellen Zustand der Steuer leisten des Rahmen Fensters bei der Rückgabe.

### <a name="remarks"></a>Hinweise

Anschließend können Sie den Inhalt von mithilfe `CDockState` `CDockState::SaveState` von oder `Serialize`in den Speicher schreiben. Wenn Sie die Steuer leisten später in einem vorherigen Zustand wiederherstellen möchten, laden Sie den Zustand `CDockState::LoadState` mit `Serialize`oder, und `SetDockState` wenden Sie dann an, um den vorherigen Zustand auf die Steuer leisten des Rahmen Fensters anzuwenden.

##  <a name="getmenubarstate"></a>CFrameWnd:: getmenubarstate

Ruft den Anzeige Zustand des Menüs in der aktuellen MFC-Anwendung ab.

```
virtual DWORD GetMenuBarState();
```

### <a name="return-value"></a>Rückgabewert

Der Rückgabewert kann die folgenden Werte aufweisen:

- AFX_MBS_VISIBLE (0x01): das Menü ist sichtbar.

- AFX_MBS_HIDDEN (0x02): das Menü ist ausgeblendet.

### <a name="remarks"></a>Hinweise

Wenn ein Laufzeitfehler auftritt, wird diese Methode im Debugmodus bestätigt und löst eine Ausnahme aus, die von der [CException](../../mfc/reference/cexception-class.md) -Klasse abgeleitet wird.

##  <a name="getmenubarvisibility"></a>CFrameWnd:: getmenubarvisibility

Gibt an, ob der Standardzustand des Menüs in der aktuellen MFC-Anwendung ausgeblendet oder sichtbar ist.

```
virtual DWORD CFrameWnd::GetMenuBarVisibility();
```

### <a name="return-value"></a>Rückgabewert

Diese Methode gibt einen der folgenden Werte zurück:

- AFX_MBV_KEEPVISIBLE (0x01): das Menü wird immer angezeigt, und der Fokus ist standardmäßig nicht vorhanden.

- AFX_MBV_DISPLAYONFOCUS (0x02): das Menü ist standardmäßig ausgeblendet. Wenn das Menü ausgeblendet ist, drücken Sie die Alt-Taste, um das Menü anzuzeigen, und weisen Sie ihm den Fokus zu. Wenn das Menü angezeigt wird, drücken Sie die alt-oder ESC-Taste, um es auszublenden.

- AFX_MBV_ displayonfocus (0x02) &#124; AFX_MBV_DISPLAYONF10 (0x04) (bitweise Kombination (oder)): das Menü ist standardmäßig ausgeblendet. Wenn das Menü ausgeblendet ist, drücken Sie die Taste F10, um das Menü anzuzeigen, und weisen Sie dem Fokus den Fokus zu. Wenn das Menü angezeigt wird, drücken Sie die Taste F10, um den Fokus auf das Menü zu schalten oder zu deaktivieren. Das Menü wird angezeigt, bis Sie die alt-oder ESC-Taste drücken, um es auszublenden.

### <a name="remarks"></a>Hinweise

Wenn ein Laufzeitfehler auftritt, wird diese Methode im Debugmodus bestätigt und löst eine Ausnahme aus, die von der [CException](../../mfc/reference/cexception-class.md) -Klasse abgeleitet wird.

##  <a name="getmessagebar"></a>CFrameWnd:: getmessagebar

Mit dieser Member-Funktion können Sie einen Zeiger auf die Statusleiste abrufen.

```
virtual CWnd* GetMessageBar();
```

### <a name="return-value"></a>Rückgabewert

Zeiger auf das Fenster der Statusleiste.

##  <a name="getmessagestring"></a>CFrameWnd:: GetMessageString

Überschreiben Sie diese Funktion, um benutzerdefinierte Zeichen folgen für Befehls-IDs anzugeben

```
virtual void GetMessageString(
    UINT nID,
    CString& rMessage) const;
```

### <a name="parameters"></a>Parameter

*nID*<br/>
Die Ressourcen-ID der gewünschten Nachricht.

*rmessage*<br/>
`CString`das Objekt, in das die Nachricht platziert werden soll.

### <a name="remarks"></a>Hinweise

Die Standard Implementierung lädt einfach die durch *NID* angegebene Zeichenfolge aus der Ressourcen Datei. Diese Funktion wird von Framework aufgerufen, wenn die Meldungs Zeichenfolge in der Statusleiste aktualisiert werden muss.

##  <a name="gettitle"></a>CFrameWnd:: getTitle

Ruft den Titel des Fenster Objekts ab.

```
CString GetTitle() const;
```

### <a name="return-value"></a>Rückgabewert

Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) -Objekt, das den aktuellen Titel des Fenster Objekts enthält.

##  <a name="initialupdateframe"></a>CFrameWnd:: initialupdateframe

Wird `IntitialUpdateFrame` aufgerufen, nachdem ein neuer Frame `Create`mit erstellt wurde.

```
void InitialUpdateFrame(
    CDocument* pDoc,
    BOOL bMakeVisible);
```

### <a name="parameters"></a>Parameter

*pDoc*<br/>
Verweist auf das Dokument, dem das Rahmen Fenster zugeordnet ist. Kann NULL sein.

*bMakeVisible*<br/>
TRUE gibt an, dass der Frame sichtbar und aktiv werden soll. Wenn der Wert false ist, werden keine Nachfolger sichtbar gemacht.

### <a name="remarks"></a>Hinweise

Dies bewirkt, dass alle Sichten in diesem Rahmen Fenster Ihre `OnInitialUpdate` Aufrufe empfangen.

Wenn zuvor noch keine aktive Ansicht vorhanden war, wird die primäre Ansicht des Rahmen Fensters aktiviert. Die primäre Ansicht ist eine Ansicht mit der untergeordneten ID AFX_IDW_PANE_FIRST. Zum Schluss wird das Rahmen Fenster sichtbar gemacht, wenn *bmakevisible* ungleich 0 (null) ist. Wenn *bmakevisible* gleich 0 ist, bleiben der aktuelle Fokus und der sichtbare Zustand des Rahmen Fensters unverändert. Es ist nicht erforderlich, diese Funktion aufzurufen, wenn Sie die Implementierung des Frameworks von Datei New und Datei Open verwenden.

##  <a name="inmodalstate"></a>CFrameWnd:: inmodalstate

Mit dieser Member-Funktion können Sie überprüfen, ob ein Rahmen Fenster modal oder nicht modelliert ist.

```
BOOL InModalState() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn ja; andernfalls 0.

##  <a name="istracking"></a>CFrameWnd:: istracking

Mit dieser Member-Funktion können Sie ermitteln, ob die Splitter Leiste im Fenster gerade verschoben wird.

```
BOOL IsTracking() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn ein Splitter Vorgang ausgeführt wird. andernfalls 0.

##  <a name="loadacceltable"></a>CFrameWnd:: loadacceltable

Ruft auf, um die angegebene Zugriffstasten Tabelle zu laden.

```
BOOL LoadAccelTable(LPCTSTR lpszResourceName);
```

### <a name="parameters"></a>Parameter

*lpszResourceName*<br/>
Identifiziert den Namen der Zugriffstasten Ressource. Verwenden Sie makeintresource, wenn die Ressource mit einer ganzzahligen ID identifiziert wird.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn die Zugriffstasten Tabelle erfolgreich geladen wurde. andernfalls 0.

### <a name="remarks"></a>Hinweise

Es kann jeweils nur eine Tabelle geladen werden.

Aus Ressourcen geladene Zugriffstasten Tabellen werden automatisch freigegeben, wenn die Anwendung beendet wird.

Wenn Sie zum `LoadFrame` Erstellen des Rahmen Fensters aufzurufen, lädt das Framework eine Zugriffstasten Tabelle zusammen mit den Menü-und Symbol Ressourcen, und ein nachfolgende Rückruf dieser Member-Funktion ist dann nicht erforderlich.

##  <a name="loadbarstate"></a>CFrameWnd:: LoadBarState

Mit dieser Funktion können Sie die Einstellungen für jede Steuerleiste wiederherstellen, deren Besitzer das Rahmen Fenster ist.

```
void LoadBarState(LPCTSTR lpszProfileName);
```

### <a name="parameters"></a>Parameter

*lpszProfileName*<br/>
Name eines Abschnitts in der Initialisierungsdatei (INI-Datei) oder ein Schlüssel in der Windows-Registrierung, in dem Zustandsinformationen gespeichert werden.

### <a name="remarks"></a>Hinweise

Zu den wiederhergestellten Informationen zählen Sichtbarkeit, horizontale/vertikale Ausrichtung, Andock Zustand und Position der Steuerleiste.

Die Einstellungen, die Sie wiederherstellen möchten, müssen in die Registrierung geschrieben werden `LoadBarState`, bevor Sie den Befehl ausführen. Schreiben Sie die Informationen in die Registrierung, indem Sie [CWinApp:: settregistrykey](../../mfc/reference/cwinapp-class.md#setregistrykey)aufrufen. Schreiben Sie die Informationen in die INI-Datei, indem Sie [SaveBarState](#savebarstate)aufrufen.

##  <a name="loadframe"></a>CFrameWnd:: LoadFrame

Rufen Sie auf, um ein Rahmen Fenster dynamisch aus den Ressourcen Informationen zu erstellen.

```
virtual BOOL LoadFrame(
    UINT nIDResource,
    DWORD dwDefaultStyle = WS_OVERLAPPEDWINDOW | FWS_ADDTOTITLE,
    CWnd* pParentWnd = NULL,
    CCreateContext* pContext = NULL);
```

### <a name="parameters"></a>Parameter

*nIDResource*<br/>
Die ID der freigegebenen Ressourcen, die dem Rahmen Fenster zugeordnet sind.

*dwDefaultStyle*<br/>
Der [Stil](../../mfc/reference/styles-used-by-mfc.md#window-styles)des Frames. Fügen Sie den FWS_ADDTOTITLE-Stil ein, wenn in der Titelleiste automatisch der Name des Dokuments angezeigt werden soll, das im Fenster dargestellt wird.

*pParentWnd*<br/>
Ein Zeiger auf das übergeordnete Element des Frames.

*pContext*<br/>
Ein Zeiger auf eine [ckreatecontext](../../mfc/reference/ccreatecontext-structure.md) -Struktur. Dieser Parameter kann NULL sein.

### <a name="remarks"></a>Hinweise

Erstellen Sie `CFrameWnd` ein-Objekt in zwei Schritten. Rufen Sie zuerst den-Konstruktor auf, der `CFrameWnd` das-Objekt erstellt, `LoadFrame`und rufen Sie dann auf, das das Windows-Rahmen Fenster und zugehörige Ressourcen lädt `CFrameWnd` und das Rahmen Fenster an das-Objekt bindet. Der Parameter " *nidresource* " gibt das Menü, die Zugriffstasten Tabelle, das Symbol und die Zeichen folgen Ressource des Titels für das Rahmen Fenster an.

Verwenden Sie `Create` die Member-Funktion `LoadFrame` statt, wenn Sie alle Erstellungs Parameter des Frame Fensters angeben möchten.

Das Framework ruft `LoadFrame` auf, wenn ein Rahmen Fenster mithilfe eines Dokumentvorlagen Objekts erstellt wird.

Das Framework verwendet das *pContext* -Argument, um die Objekte anzugeben, die mit dem Rahmen Fenster verbunden werden sollen, einschließlich aller enthaltenen Ansichts Objekte. Sie können das *pContext* -Argument auf NULL festlegen, wenn `LoadFrame`Sie aufzurufen.

##  <a name="m_bautomenuenable"></a>CFrameWnd:: m_bAutoMenuEnable

Wenn dieser Datenmember aktiviert ist (Standardeinstellung), werden Menü Elemente, die keine ON_UPDATE_COMMAND_UI-oder ON_COMMAND-Handler aufweisen, automatisch deaktiviert, wenn der Benutzer ein Menü abruft.

```
BOOL m_bAutoMenuEnable;
```

### <a name="remarks"></a>Hinweise

Menü Elemente, die über einen ON_COMMAND-Handler, aber keinen ON_UPDATE_COMMAND_UI-Handler verfügen, werden automatisch aktiviert.

Wenn dieses Datenmember festgelegt ist, werden Menü Elemente automatisch auf die gleiche Weise aktiviert, wie Symbolleisten Schaltflächen aktiviert werden.

> [!NOTE]
> `m_bAutoMenuEnable`hat keine Auswirkung auf Menü Elemente der obersten Ebene.

Dieser Datenmember vereinfacht die Implementierung Optionaler Befehle auf der Grundlage der aktuellen Auswahl und reduziert das Schreiben von ON_UPDATE_COMMAND_UI-Handlern zum Aktivieren und Deaktivieren von Menü Elementen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#3](../../mfc/reference/codesnippet/cpp/cframewnd-class_3.cpp)]

##  <a name="negotiateborderspace"></a>CFrameWnd:: aushandateborderspace

Mit dieser Member-Funktion können Sie während der OLE-Aktivierung einen Rahmen Bereich in einem Rahmen Fenster aushandeln.

```
virtual BOOL NegotiateBorderSpace(
    UINT nBorderCmd,
    LPRECT lpRectBorder);
```

### <a name="parameters"></a>Parameter

*nBorderCmd*<br/>
Enthält einen der folgenden Werte aus `enum BorderCmd`:

- `borderGet` = 1

- `borderRequest` = 2

- `borderSet` = 3

*lpRectBorder*<br/>
Ein Zeiger auf eine [Rect](/windows/win32/api/windef/ns-windef-rect) -Struktur oder ein [CRect](../../atl-mfc-shared/reference/crect-class.md) -Objekt, das die Koordinaten des Rahmens angibt.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Diese Member-Funktion ist `CFrameWnd` die Implementierung der OLE-Border-Space-Aushandlung.

##  <a name="onbarcheck"></a>CFrameWnd:: onbarcheck

Wird aufgerufen, wenn eine Aktion auf der angegebenen Steuerleiste ausgeführt wird.

```
afx_msg BOOL OnBarCheck(UINT nID);
```

### <a name="parameters"></a>Parameter

*nID*<br/>
Die ID der angezeigten Steuerleiste.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Steuerleiste vorhanden war. andernfalls 0.

##  <a name="oncontexthelp"></a>CFrameWnd:: oncontexthelp

Behandelt die UMSCHALT + F1-Hilfe für direkte Elemente.

```
afx_msg void OnContextHelp();
```

### <a name="remarks"></a>Hinweise

Um die kontextbezogene Hilfe zu aktivieren, müssen Sie ein

[!code-cpp[NVC_MFCDocViewSDI#16](../../mfc/codesnippet/cpp/cframewnd-class_4.cpp)]

-Anweisung für `CFrameWnd` die Klassen Meldungs Zuordnung und auch einen Zugriffstasten-Tabelleneintrag hinzufügen, normalerweise UMSCHALT + F1, um diese Element Funktion zu aktivieren.

Wenn es sich bei der Anwendung um einen `OnContextHelp` OLE-Container handelt, werden alle direkten Elemente, die im Rahmen Fenster Objekt enthalten sind, in den Hilfe Modus eingefügt. Der Cursor wechselt zu einem Pfeil und einem Fragezeichen, und der Benutzer kann dann den Mauszeiger bewegen und die linke Maustaste drücken, um ein Dialogfeld, ein Fenster, ein Menü oder eine Befehls Schaltfläche auszuwählen. Diese Member-Funktion Ruft die Windows `WinHelp` -Funktion mit dem Hilfe Kontext des-Objekts unter dem Cursor auf.

##  <a name="oncreateclient"></a>CFrameWnd:: onkreateclient

Wird von Framework während der Ausführung von `OnCreate`aufgerufen.

```
virtual BOOL OnCreateClient(
    LPCREATESTRUCT lpcs,
    CCreateContext* pContext);
```

### <a name="parameters"></a>Parameter

*lpcs*<br/>
Ein Zeiger auf eine Windows-Struktur vom Typ " [kreatestruct](/windows/win32/api/winuser/ns-winuser-createstructw) ".

*pContext*<br/>
Ein Zeiger auf eine [ckreatecontext](../../mfc/reference/ccreatecontext-structure.md) -Struktur.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Diese Funktion niemals aufruft.

Die Standard Implementierung dieser Funktion erstellt ein `CView` -Objekt aus den Informationen, die in *pContext*bereitgestellt werden, sofern möglich.

Überschreiben Sie diese Funktion, um die im `CCreateContext` -Objekt übergebenen Werte zu überschreiben oder die Art und Weise zu ändern, in der Steuerelemente im Haupt Client Bereich des Rahmen Fensters erstellt werden Die `CCreateContext` Elemente, die Sie überschreiben können, werden in der [ckreatecontext](../../mfc/reference/ccreatecontext-structure.md) -Klasse beschrieben.

> [!NOTE]
>  Ersetzen Sie keine Werte, die in `CREATESTRUCT` der Struktur übermittelt werden. Sie dienen nur zur Informations Verwendung. Wenn Sie das anfängliche Fenster Rechteck außer Kraft setzen möchten, überschreiben Sie z `CWnd` . b. die Element Funktion [prekreatewindow](../../mfc/reference/cwnd-class.md#precreatewindow).

##  <a name="onhidemenubar"></a>CFrameWnd:: onhidemenubar

Diese Funktion wird aufgerufen, wenn das System im Begriff ist, die Menüleiste in der aktuellen MFC-Anwendung auszublenden.

```
virtual void OnHideMenuBar();
```

### <a name="remarks"></a>Hinweise

Dieser Ereignishandler ermöglicht der Anwendung, benutzerdefinierte Aktionen auszuführen, wenn das System im Begriff ist, das Menü auszublenden. Sie können nicht verhindern, dass das Menü ausgeblendet wird. Sie können z. b. andere Methoden aufrufen, um den Menü Stil oder-Zustand abzurufen.

##  <a name="onsetpreviewmode"></a>CFrameWnd:: onsetpreviewmode

Rufen Sie diese Memberfunktion auf, um für das Hauptrahmenfenster den Seitenansichtmodus zu aktivieren oder zu deaktivieren.

```
virtual void OnSetPreviewMode(
    BOOL bPreview,
    CPrintPreviewState* pState);
```

### <a name="parameters"></a>Parameter

*bPreview*<br/>
Gibt an, ob die Anwendung im Druckvorschau Modus platziert werden soll. Legen Sie diese Einstellung auf "true" fest, um die Seitenansicht zu platzieren.

*pState*<br/>
Ein Zeiger auf eine `CPrintPreviewState` -Struktur.

### <a name="remarks"></a>Hinweise

Die Standard Implementierung deaktiviert alle Standard Symbolleisten und blendet das Hauptmenü und das Haupt Client Fenster aus. Dadurch werden MDI-Rahmen Fenster in temporäre SDI-Rahmen Fenster verwandelt.

Überschreiben Sie diese Member-Funktion, um das Ausblenden und Anzeigen von Steuer leisten und anderen Rahmen Fenster teilen während der Seitenansicht anzupassen. Ruft die Basisklassen Implementierung innerhalb der überschriebenen Version auf.

##  <a name="onshowmenubar"></a>CFrameWnd:: onshowmenubar

Diese Funktion wird aufgerufen, wenn das System im Begriff ist, die Menüleiste in der aktuellen MFC-Anwendung anzuzeigen.

```
virtual void OnShowMenuBar();
```

### <a name="remarks"></a>Hinweise

Dieser Ereignishandler ermöglicht der Anwendung, benutzerdefinierte Aktionen auszuführen, wenn das Menü angezeigt wird. Sie können nicht verhindern, dass das Menü angezeigt wird. Sie können z. b. andere Methoden aufrufen, um den Menü Stil oder-Zustand abzurufen.

##  <a name="onupdatecontrolbarmenu"></a>CFrameWnd:: onupdatecontrolbarmenu

Wird von Framework aufgerufen, wenn das zugehörige Menü aktualisiert wird.

```
afx_msg void OnUpdateControlBarMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>Parameter

*pCmdUI*<br/>
Ein Zeiger auf ein [CCmdUI](../../mfc/reference/ccmdui-class.md) -Objekt, das das Menü darstellt, das den Update-Befehl generiert hat. Der Update Handler Ruft die [enable](../../mfc/reference/ccmdui-class.md#enable) Member-Funktion des `CCmdUI` -Objekts über *pCmdUI* auf, um die Benutzeroberfläche zu aktualisieren.

##  <a name="recalclayout"></a>CFrameWnd:: Neuberechnen

Wird von Framework aufgerufen, wenn die Standard Steuer leisten ein-oder ausgeschaltet werden oder wenn die Größe des Rahmen Fensters geändert wird.

```
virtual void RecalcLayout(BOOL bNotify = TRUE);
```

### <a name="parameters"></a>Parameter

*bNotify*<br/>
Bestimmt, ob das aktive direkte Element für das Rahmen Fenster eine Benachrichtigung über die Layoutänderung empfängt. TRUE gibt an, dass das Element benachrichtigt wird. andernfalls false.

### <a name="remarks"></a>Hinweise

Die Standard Implementierung dieser Member-Funktion Ruft die `CWnd` -Member `RepositionBars` -Funktion auf, um alle Steuer leisten im Frame und im Haupt Client Fenster (normalerweise a `CView` oder MdiClient) neu zu positionieren.

Überschreiben Sie diese Member-Funktion, um die Darstellung und das Verhalten von Steuer leisten zu steuern, nachdem sich das Layout des Rahmen Fensters geändert hat. Beispielsweise, wenn Sie Steuer leisten ein-oder ausschalten oder eine weitere Steuerleiste hinzufügen.

##  <a name="rectdefault"></a>CFrameWnd:: rectdefault

Übergeben Sie dieses `CRect` static als Parameter, wenn Sie ein Fenster erstellen, damit Windows die anfängliche Größe und Position des Fensters auswählen kann.

```
static AFX_DATA const CRect rectDefault;
```

##  <a name="savebarstate"></a>CFrameWnd:: SaveBarState

Mit dieser Funktion werden Informationen zu den einzelnen Steuer leisten im Besitz des Rahmen Fensters gespeichert.

```
void SaveBarState(LPCTSTR lpszProfileName) const;
```

### <a name="parameters"></a>Parameter

*lpszProfileName*<br/>
Name eines Abschnitts in der Initialisierungsdatei oder ein Schlüssel in der Windows-Registrierung, in dem Zustandsinformationen gespeichert werden.

### <a name="remarks"></a>Hinweise

Diese Informationen können mithilfe von [LoadBarState](#loadbarstate)aus der Initialisierungsdatei gelesen werden. Zu den gespeicherten Informationen zählen Sichtbarkeit, horizontale/vertikale Ausrichtung, Andock Zustand und Position der Steuerleiste.

##  <a name="setactivepreviewview"></a>CFrameWnd:: abviewview

Legt die angegebene Ansicht als aktive Ansicht für die umfangreiche Vorschau fest.

```
void SetActivePreviewView(CView* pViewNew);
```

### <a name="parameters"></a>Parameter

*pViewNew*<br/>
Ein Zeiger auf eine Ansicht, die aktiviert werden soll.

### <a name="remarks"></a>Hinweise

##  <a name="setactiveview"></a>CFrameWnd:: abtativeview

Mit dieser Member-Funktion können Sie die aktive Ansicht festlegen.

```
void SetActiveView(
    CView* pViewNew,
    BOOL bNotify = TRUE);
```

### <a name="parameters"></a>Parameter

*pViewNew*<br/>
Gibt einen Zeiger auf ein [CView](../../mfc/reference/cview-class.md) -Objekt oder NULL für keine aktive Ansicht an.

*bNotify*<br/>
Gibt an, ob die Ansicht über die Aktivierung benachrichtigt werden soll. TRUE gibt an `OnActivateView` , dass für die neue Ansicht aufgerufen wird; wenn false, ist dies nicht der Fall.

### <a name="remarks"></a>Hinweise

Das Framework ruft diese Funktion automatisch auf, wenn der Benutzer den Fokus auf eine Ansicht innerhalb des Rahmen Fensters ändert. Sie können explizit aufzurufen `SetActiveView` , um den Fokus auf die angegebene Ansicht zu ändern.

##  <a name="setdockstate"></a>CFrameWnd:: setdockstate

Mit dieser Member-Funktion können Sie in einem `CDockState` -Objekt gespeicherte Zustandsinformationen auf die Steuer leisten des Rahmen Fensters anwenden.

```
void SetDockState(const CDockState& state);
```

### <a name="parameters"></a>Parameter

*state*<br/>
Anwenden des gespeicherten Zustands auf die Steuer leisten des Rahmen Fensters.

### <a name="remarks"></a>Hinweise

Wenn Sie einen früheren Zustand der Steuer leisten wiederherstellen möchten, können Sie den gespeicherten Zustand `CDockState::LoadState` mit `Serialize`oder laden und `SetDockState` dann mithilfe von auf die Steuer leisten des Rahmen Fensters anwenden. Der vorherige Zustand wird im `CDockState` -Objekt gespeichert.`GetDockState`

##  <a name="setmenubarstate"></a>CFrameWnd:: setmenubarstate

Legt den Anzeige Zustand des Menüs in der aktuellen MFC-Anwendung auf ausgeblendet oder angezeigt fest.

```
virtual BOOL SetMenuBarState(DWORD nState);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*nState*|in Gibt an, ob das Menü angezeigt oder ausgeblendet werden soll. Der *nState* -Parameter kann die folgenden Werte aufweisen:<br /><br />-AFX_MBS_VISIBLE (0x01): zeigt das Menü an, wenn es ausgeblendet ist, aber keine Auswirkung hat, wenn es sichtbar ist.<br />-AFX_MBS_HIDDEN (0x02): Blendet das Menü aus, wenn es sichtbar ist, aber keine Auswirkung hat, wenn es ausgeblendet ist.|

### <a name="return-value"></a>Rückgabewert

TRUE, wenn diese Methode den Menü Zustand erfolgreich ändert. andernfalls false.

### <a name="remarks"></a>Hinweise

Wenn ein Laufzeitfehler auftritt, wird diese Methode im Debugmodus bestätigt und löst eine Ausnahme aus, die von der [CException](../../mfc/reference/cexception-class.md) -Klasse abgeleitet wird.

##  <a name="setmenubarvisibility"></a>CFrameWnd:: SetMenuBarVisibility

Legt das Standardverhalten des Menüs in der aktuellen MFC-Anwendung als ausgeblendet oder sichtbar fest.

```
virtual void SetMenuBarVisibility(DWORD nStyle);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*nStyle*|in Gibt an, ob das Menü standardmäßig ausgeblendet ist, oder ist sichtbar und hat den Fokus. Der *nstyle* -Parameter kann die folgenden Werte aufweisen:<br /><br />-AFX_MBV_KEEPVISIBLE (0x01)-<br />     Das Menü wird jederzeit angezeigt, und der Fokus ist standardmäßig nicht vorhanden.<br />- AFX_MBV_DISPLAYONFOCUS (0x02) -<br />     Das Menü ist standardmäßig ausgeblendet. Wenn das Menü ausgeblendet ist, drücken Sie die Alt-Taste, um das Menü anzuzeigen, und weisen Sie ihm den Fokus zu. Wenn das Menü angezeigt wird, drücken Sie die Alt-Taste oder ESC-Taste, um das Menü auszublenden.<br />- AFX_MBV_ DISPLAYONFOCUS (0x02) &#124; AFX_MBV_DISPLAYONF10 (0x04)<br />     (bitweise Kombination (oder)): das Menü ist standardmäßig ausgeblendet. Wenn das Menü ausgeblendet ist, drücken Sie die Taste F10, um das Menü anzuzeigen, und weisen Sie dem Fokus den Fokus zu. Wenn das Menü angezeigt wird, drücken Sie die Taste F10, um den Fokus auf das Menü zu schalten oder zu deaktivieren. Das Menü wird angezeigt, bis Sie die alt-oder ESC-Taste drücken, um es auszublenden.|

### <a name="remarks"></a>Hinweise

Wenn der Wert des *nstyle* -Parameters ungültig ist, bestätigt diese Methode im Debugmodus und löst [cinvalidargexception](../../mfc/reference/cinvalidargexception-class.md) im Releasemodus aus. Bei anderen Laufzeitfehlern bestätigt diese Methode im Debugmodus und löst eine Ausnahme aus, die von der [CException](../../mfc/reference/cexception-class.md) -Klasse abgeleitet wird.

Diese Methode wirkt sich auf den Zustand von Menüs in Anwendungen aus, die für Windows Vista und höher geschrieben wurden.

##  <a name="setmessagetext"></a>CFrameWnd:: ab.

Mit dieser Funktion können Sie eine Zeichenfolge im Status Leistenbereich mit der ID 0 platzieren.

```
void SetMessageText(LPCTSTR lpszText);
void SetMessageText(UINT nID);
```

### <a name="parameters"></a>Parameter

*lpszText*<br/>
Zeigt auf die Zeichenfolge, die auf der Statusleiste platziert werden soll.

*nID*<br/>
Zeichen folgen Ressourcen-ID der Zeichenfolge, die auf der Statusleiste platziert werden soll.

### <a name="remarks"></a>Hinweise

Dabei handelt es sich in der Regel um den am weitesten links stehenden und längsten Bereich der Statusleiste.

##  <a name="setprogressbarposition"></a>CFrameWnd:: setprogressbarposition

Legt die aktuelle Position für die Windows 7-Statusanzeige fest, die auf der Taskleiste angezeigt wird.

```
void SetProgressBarPosition(int nProgressPos);
```

### <a name="parameters"></a>Parameter

*nProgressPos*<br/>
Gibt die festzulegende Position an. Sie muss innerhalb des Bereichs liegen, der `SetProgressBarRange`von festgelegt wird.

### <a name="remarks"></a>Hinweise

##  <a name="setprogressbarrange"></a>CFrameWnd:: setprogressbarrange

Legt den Bereich für die Windows 7-Statusanzeige fest, der auf der Taskleiste angezeigt wird.

```
void SetProgressBarRange(
    int nRangeMin,
    int nRangeMax);
```

### <a name="parameters"></a>Parameter

*nRangeMin*<br/>
Minimal Wert.

*nRangeMax*<br/>
Maximaler Wert.

### <a name="remarks"></a>Hinweise

##  <a name="setprogressbarstate"></a>CFrameWnd:: setprogressbarstate

Legt den Typ und den Zustand der Statusanzeige fest, die auf einer Task leisten Schaltfläche angezeigt wird.

```
void SetProgressBarState(TBPFLAG tbpFlags);
```

### <a name="parameters"></a>Parameter

*tbpFlags*<br/>
Flags, die den aktuellen Zustand der Fortschritts Schaltfläche steuern. Geben Sie nur eines der folgenden Flags an, da sich alle Zustände gegenseitig ausschließen: TBPF_NOPROGRESS, TBPF_INDETERMINATE, TBPF_NORMAL, TBPF_ERROR, TBPF_PAUSED.

### <a name="remarks"></a>Hinweise

##  <a name="settaskbaroverlayicon"></a>CFrameWnd:: settaskbaroverlayicon

Überladen. Wendet ein Overlay auf eine Task leisten Schaltfläche an, um den Anwendungs Status anzugeben oder um den Benutzer zu benachrichtigen.

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
Gibt die Ressourcen-ID eines Symbols an, das als Overlay verwendet werden soll. Weitere Informationen finden Sie in der Beschreibung für *HICON* .

*lpcszDescr*<br/>
Ein Zeiger auf eine Zeichenfolge, die eine alt-Textversion der von der Überlagerung übermittelten Informationen zu Barrierefreiheits Zwecken bereitstellt.

*hIcon*<br/>
Das Handle eines Symbols, das als Overlay verwendet werden soll. Dabei sollte es sich um ein kleines Symbol handeln, das 16x16 Pixel bei 96 Punkten pro Zoll (dpi) misst. Wenn ein Überlagerungs Symbol bereits auf die Task leisten Schaltfläche angewendet wird, wird dieses vorhandene Overlay ersetzt. Dieser Wert kann NULL sein. Wie ein NULL-Wert behandelt wird, hängt davon ab, ob die Task leisten Schaltfläche ein einzelnes Fenster oder eine Gruppe von Fenstern darstellt. Es liegt in der Verantwortung der aufrufenden Anwendung, *HICON* freizugeben, wenn es nicht mehr benötigt wird.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn erfolgreich; FALSE, wenn die Betriebssystemversion kleiner als Windows 7 ist oder wenn ein Fehler auftritt, wenn das Symbol festgelegt wird.

### <a name="remarks"></a>Hinweise

##  <a name="settitle"></a>CFrameWnd:: SetTitle

Legt den Titel des Fenster Objekts fest.

```
void SetTitle(LPCTSTR lpszTitle);
```

### <a name="parameters"></a>Parameter

*lpszTitle*<br/>
Ein Zeiger auf eine Zeichenfolge, die den Titel des Fenster Objekts enthält.

##  <a name="showcontrolbar"></a>CFrameWnd:: showcontrolbar

Mit dieser Member-Funktion können Sie die Steuerleiste anzeigen oder ausblenden.

```
void ShowControlBar(
    CControlBar* pBar,
    BOOL bShow,
    BOOL bDelay);
```

### <a name="parameters"></a>Parameter

*pBar*<br/>
Ein Zeiger auf die Steuerleiste, die angezeigt oder ausgeblendet werden soll.

*bShow*<br/>
Wenn der Wert true ist, wird angegeben, dass die Steuerleiste angezeigt werden soll. Wenn der Wert false ist, wird angegeben, dass die Steuerleiste ausgeblendet werden soll.

*bDelay*<br/>
Wenn true, wird die Steuerleiste verzögert angezeigt. Wenn der Wert false ist, wird die Steuerleiste sofort angezeigt.

##  <a name="showownedwindows"></a>CFrameWnd:: showownedwindows

Diese Member-Funktion wird aufgerufen, um alle Fenster anzuzeigen, die `CFrameWnd` Nachfolger des-Objekts sind.

```
void ShowOwnedWindows(BOOL bShow);
```

### <a name="parameters"></a>Parameter

*bShow*<br/>
Gibt an, ob die eigenen Fenster angezeigt oder ausgeblendet werden sollen.

## <a name="see-also"></a>Siehe auch

[CWnd-Klasse](../../mfc/reference/cwnd-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CWnd-Klasse](../../mfc/reference/cwnd-class.md)<br/>
[CMDIFrameWnd-Klasse](../../mfc/reference/cmdiframewnd-class.md)<br/>
[CMDIChildWnd-Klasse](../../mfc/reference/cmdichildwnd-class.md)<br/>
[CView-Klasse](../../mfc/reference/cview-class.md)<br/>
[CDocTemplate-Klasse](../../mfc/reference/cdoctemplate-class.md)<br/>
[CRuntimeClass-Struktur](../../mfc/reference/cruntimeclass-structure.md)

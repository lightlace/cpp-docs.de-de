---
title: CPropertySheet-Klasse
ms.date: 11/04/2016
f1_keywords:
- CPropertySheet
- AFXDLGS/CPropertySheet
- AFXDLGS/CPropertySheet::CPropertySheet
- AFXDLGS/CPropertySheet::AddPage
- AFXDLGS/CPropertySheet::Construct
- AFXDLGS/CPropertySheet::Create
- AFXDLGS/CPropertySheet::DoModal
- AFXDLGS/CPropertySheet::EnableStackedTabs
- AFXDLGS/CPropertySheet::EndDialog
- AFXDLGS/CPropertySheet::GetActiveIndex
- AFXDLGS/CPropertySheet::GetActivePage
- AFXDLGS/CPropertySheet::GetPage
- AFXDLGS/CPropertySheet::GetPageCount
- AFXDLGS/CPropertySheet::GetPageIndex
- AFXDLGS/CPropertySheet::GetTabControl
- AFXDLGS/CPropertySheet::MapDialogRect
- AFXDLGS/CPropertySheet::OnInitDialog
- AFXDLGS/CPropertySheet::PressButton
- AFXDLGS/CPropertySheet::RemovePage
- AFXDLGS/CPropertySheet::SetActivePage
- AFXDLGS/CPropertySheet::SetFinishText
- AFXDLGS/CPropertySheet::SetTitle
- AFXDLGS/CPropertySheet::SetWizardButtons
- AFXDLGS/CPropertySheet::SetWizardMode
- AFXDLGS/CPropertySheet::m_psh
helpviewer_keywords:
- CPropertySheet [MFC], CPropertySheet
- CPropertySheet [MFC], AddPage
- CPropertySheet [MFC], Construct
- CPropertySheet [MFC], Create
- CPropertySheet [MFC], DoModal
- CPropertySheet [MFC], EnableStackedTabs
- CPropertySheet [MFC], EndDialog
- CPropertySheet [MFC], GetActiveIndex
- CPropertySheet [MFC], GetActivePage
- CPropertySheet [MFC], GetPage
- CPropertySheet [MFC], GetPageCount
- CPropertySheet [MFC], GetPageIndex
- CPropertySheet [MFC], GetTabControl
- CPropertySheet [MFC], MapDialogRect
- CPropertySheet [MFC], OnInitDialog
- CPropertySheet [MFC], PressButton
- CPropertySheet [MFC], RemovePage
- CPropertySheet [MFC], SetActivePage
- CPropertySheet [MFC], SetFinishText
- CPropertySheet [MFC], SetTitle
- CPropertySheet [MFC], SetWizardButtons
- CPropertySheet [MFC], SetWizardMode
- CPropertySheet [MFC], m_psh
ms.assetid: 8461ccff-d14f-46e0-a746-42ad642ef94e
ms.openlocfilehash: 0e5194a356684f2ff86d74a0ed1f37f332bcffeb
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58781652"
---
# <a name="cpropertysheet-class"></a>CPropertySheet-Klasse

Stellt Eigenschaftenblätter dar, auch als "Dialogfelder im Registerformat" bezeichnet.

## <a name="syntax"></a>Syntax

```
class CPropertySheet : public CWnd
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CPropertySheet::CPropertySheet](#cpropertysheet)|Erstellt ein `CPropertySheet`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CPropertySheet::AddPage](#addpage)|Fügt dem Eigenschaftsblatt eine Seite hinzu.|
|[CPropertySheet::Construct](#construct)|Erstellt ein `CPropertySheet`-Objekt.|
|[CPropertySheet::Create](#create)|Zeigt die eines nicht modalen Eigenschaftenblatts an.|
|[CPropertySheet::DoModal](#domodal)|Zeigt ein modales Eigenschaftsblatt an.|
|[CPropertySheet::EnableStackedTabs](#enablestackedtabs)|Gibt an, ob das Eigenschaftenblatt gestapelte oder einen Scrollcursor Registerkarten verwendet.|
|[CPropertySheet::EndDialog](#enddialog)|Das Eigenschaftenblatt wird beendet.|
|[CPropertySheet::GetActiveIndex](#getactiveindex)|Ruft den Index der aktiven Seite des Eigenschaftenblatts ab.|
|[CPropertySheet::GetActivePage](#getactivepage)|Gibt das aktive Seite zurück.|
|[CPropertySheet::GetPage](#getpage)|Ruft einen Zeiger auf die angegebene Seite ab.|
|[CPropertySheet::GetPageCount](#getpagecount)|Ruft die Anzahl der Seiten im Eigenschaftenblatt.|
|[CPropertySheet::GetPageIndex](#getpageindex)|Ruft den Index der angegebenen Seite des Eigenschaftenblatts ab.|
|[CPropertySheet::GetTabControl](#gettabcontrol)|Ruft einen Zeiger auf ein Registerkarten-Steuerelement ab.|
|[CPropertySheet::MapDialogRect](#mapdialogrect)|Konvertiert die Dialogfeld-Einheiten eines Rechtecks Bildschirm Einheiten.|
|[CPropertySheet::OnInitDialog](#oninitdialog)|Überschreiben Sie, um das Blatt eigenschafteninitialisierung zu erweitern.|
|[CPropertySheet::PressButton](#pressbutton)|Simuliert die Auswahl der angegebenen Schaltfläche in einem Eigenschaftenblatt.|
|[CPropertySheet::RemovePage](#removepage)|Entfernt eine Seite aus dem Eigenschaftenblatt.|
|[CPropertySheet::SetActivePage](#setactivepage)|Programmgesteuert legt die aktive Seite-Objekt fest.|
|[CPropertySheet::SetFinishText](#setfinishtext)|Legt den Text für die Schaltfläche "Fertig stellen".|
|[CPropertySheet::SetTitle](#settitle)|Legt die Beschriftung des Eigenschaftenblatts an.|
|[CPropertySheet::SetWizardButtons](#setwizardbuttons)|Können die Schaltflächen des Assistenten.|
|[CPropertySheet::SetWizardMode](#setwizardmode)|Können den Assistentenmodus.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CPropertySheet::m_psh](#m_psh)|Die Windows [PROPSHEETHEADER](/windows/desktop/api/prsht/ns-prsht-_propsheetheadera_v2) Struktur. Bietet Zugriff auf dem Blatt "einfache Property"-Parameter an.|

## <a name="remarks"></a>Hinweise

Ein Eigenschaftenblatt besteht aus einem `CPropertySheet` Objekt und einer oder mehrerer [CPropertyPage](../../mfc/reference/cpropertypage-class.md) Objekte. Das Framework zeigt ein Eigenschaftenblatt, als ein Fenster mit einem Satz von Registerkartenindizes und ein Bereich, der die aktuell ausgewählte Seite enthält. Der Benutzer navigiert zu einer bestimmten Seite mithilfe der entsprechenden Registerkarte.

`CPropertySheet` bietet Unterstützung für den erweiterten [PROPSHEETHEADER](/windows/desktop/api/prsht/ns-prsht-_propsheetheadera_v2) Struktur, die in Windows 98 und Windows NT, 2000 eingeführt wurden. Die Struktur enthält die zusätzliche Flags und Member, die mithilfe einer Bitmap im Hintergrund "Wasserzeichens" zu unterstützen.

Um diese neue Images automatisch in Ihrer Eigenschaftenblattobjekt anzuzeigen, übergeben Sie gültige Werte für die Bitmap und Paletteninformationen Bilder im Aufruf von [CPropertySheet::Construct](#construct) oder [CPropertySheet::CPropertySheet](#cpropertysheet).

Obwohl `CPropertySheet` stammt nicht aus [CDialog](../../mfc/reference/cdialog-class.md), zum Verwalten von eine `CPropertySheet` Objekt ist, wie etwa die Verwaltung eine `CDialog` Objekt. Erstellen eines Eigenschaftenblatts erfordert z. B. mit dem zweiteiligen Konstruktion: Rufen Sie den Konstruktor, und rufen dann [DoModal](#domodal) für ein modales Eigenschaftsblatt oder [erstellen](#create) für eines nicht modalen Eigenschaftenblatts. `CPropertySheet` verfügt über zwei Arten von Konstruktoren: [CPropertySheet::Construct](#construct) und [CPropertySheet::CPropertySheet](#cpropertysheet).

Beim Erstellen einer `CPropertySheet` Objekt, einige [Window-Stile](../../mfc/reference/styles-used-by-mfc.md#window-styles) kann dazu führen, dass eine nicht abgefangene Ausnahme auftritt. Dadurch wird aus dem System, bei dem Versuch, den Stil des Eigenschaftenblatts zu ändern, bevor die Tabelle erstellt wird. Um diese Ausnahme zu vermeiden, stellen Sie sicher, dass Sie die folgenden Formate festlegen, bei der Erstellung Ihrer `CPropertySheet`:

- DS_3DLOOK

- DS_CONTROL

- WS_CHILD

- WS_TABSTOP

Die folgenden Stile sind optional, und führt nicht dazu, dass die abgefangene Ausnahme:

- DS_SHELLFONT

- DS_LOCALEDIT

- WS_CLIPCHILDREN

Alle anderen `Window Styles` sind unzulässig, und Sie sollten diese nicht aktivieren.

Austauschen von Daten zwischen einem `CPropertySheet` Objekt und ein externes Objekt ähnelt Austauschen von Daten mit einem `CDialog` Objekt. Der wichtige Unterschied besteht darin, dass die Einstellungen von einem Eigenschaftenblatt die Membervariablen des in der Regel sind die `CPropertyPage` Objekte und nicht die `CPropertySheet` Objekt selbst.

Sie können einen Typ von Tab-Dialogfeld wird aufgerufen, einen Assistenten, der besteht aus einem Eigenschaftenblatt mit einer Sequenz von Eigenschaftenseiten, die den Benutzer durch die Schritte eines Vorgangs, wie das Einrichten eines Geräts oder einen Newsletter erstellen. In einem Dialogfeld des Benutzens eines assistentartigen-Registerkarte die Eigenschaftenseiten müssen sich nicht auf die Registerkarten, und nur eine Eigenschaftenseite wird zu einem Zeitpunkt angezeigt. Außerdem statt **OK** und **jetzt übernehmen** Schaltflächen, um ein Dialogfeld im Registerformat des Benutzens eines assistentartigen hat eine **wieder** Schaltfläche eine **Weiter** oder  **Fertig stellen** Schaltfläche eine **Abbrechen** Schaltfläche und ein **Hilfe** Schaltfläche.

Um ein Dialogfeld des Benutzens eines assistentartigen zu erstellen, die gleichen Schritte, die Sie ausführen müssen, um das Erstellen eines standardmäßigen Eigenschaftenblatts Aufruf jedoch [SetWizardMode](#setwizardmode) vor dem Aufruf [DoModal](#domodal). Rufen Sie zum Aktivieren der Schaltflächen des Assistenten [SetWizardButtons](#setwizardbuttons), mit der Flags, deren Funktion und Darstellung anpassen. So aktivieren Sie die **Fertig stellen** Schaltfläche, rufen Sie [SetFinishText](#setfinishtext) , nachdem der Benutzer eine Aktion auf der letzten Seite des Assistenten vorgenommen hat.

Weitere Informationen zur Verwendung von `CPropertySheet` Objekte finden Sie im Artikel [Eigenschaftenblätter und Eigenschaftenseiten](../../mfc/property-sheets-and-property-pages-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CPropertySheet`

## <a name="requirements"></a>Anforderungen

**Header:** afxdlgs.h

##  <a name="addpage"></a>  CPropertySheet::AddPage

Fügt die angegebene Seite mit dem die Registerkarte ganz rechts im Eigenschaftenfenster an.

```
void AddPage(CPropertyPage* pPage);
```

### <a name="parameters"></a>Parameter

*pPage*<br/>
Zeigt auf der Seite, um das Eigenschaftenblatt hinzugefügt werden. Darf nicht NULL sein.

### <a name="remarks"></a>Hinweise

Hinzufügen von Seiten in dem Eigenschaftenblatt, in der links-nach-rechts-Reihenfolge, dass Sie angezeigt werden sollen.

`AddPage` Fügt der [CPropertyPage](../../mfc/reference/cpropertypage-class.md#cpropertypage) -Objekt an die `CPropertySheet` Objekt die Liste der Seiten, aber nicht tatsächlich im Fenster für die Seite erstellt. Das Framework stellt die Erstellung des Fensters für die Seite zurück, bis der Benutzer auf dieser Seite auswählt.

Beim Hinzufügen einer Eigenschaftenseite mithilfe `AddPage`, `CPropertySheet` ist das übergeordnete Element der `CPropertyPage`. Rufen Sie für den Zugriff auf dem Eigenschaftenblatt auf der Eigenschaftenseite [CWnd::GetParent](../../mfc/reference/cwnd-class.md#getparent).

Es ist nicht erforderlich ist, warten, bis die Erstellung des Fensters für das Eigenschaft aufrufen `AddPage`. Rufen Sie in der Regel `AddPage` vor dem Aufruf [DoModal](#domodal) oder [erstellen](#create).

Wenn Sie aufrufen `AddPage` die Registerkartenreihe spiegeln nach dem Anzeigen der Eigenschaftenseite, die neu hinzugefügte Seite.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#129](../../mfc/codesnippet/cpp/cpropertysheet-class_1.cpp)]

##  <a name="construct"></a>  CPropertySheet::Construct

Erstellt ein `CPropertySheet`-Objekt.

```
void Construct(
    UINT nIDCaption,
    CWnd* pParentWnd = NULL,
    UINT iSelectPage = 0);

void Construct(
    LPCTSTR pszCaption,
    CWnd* pParentWnd = NULL,
    UINT iSelectPage = 0);

void Construct(
    UINT nIDCaption,
    CWnd* pParentWnd,
    UINT iSelectPage,
    HBITMAP hbmWatermark,
    HPALETTE hpalWatermark = NULL,
    HBITMAP hbmHeader = NULL);

void Construct(
    LPCTSTR pszCaption,
    CWnd* pParentWnd,
    UINT iSelectPage,
    HBITMAP hbmWatermark,
    HPALETTE hpalWatermark = NULL,
    HBITMAP hbmHeader = NULL);
```

### <a name="parameters"></a>Parameter

*nIDCaption*<br/>
Die ID der Beschriftung für das Eigenschaftenblatt verwendet werden.

*pParentWnd*<br/>
Zeiger auf das übergeordnete Fenster des Eigenschaftenblatts. Wenn der Wert NULL ist, wird das übergeordnete Fenster das Hauptfenster der Anwendung sein.

*iSelectPage*<br/>
Der Index der Seite, die ursprünglich im Vordergrund. Standardmäßig ist die erste Seite in der Tabelle hinzugefügt.

*pszCaption*<br/>
Zeiger auf eine Zeichenfolge, enthält die Beschriftung für das Eigenschaftenblatt verwendet werden. Darf nicht NULL sein.

*hbmWatermark*<br/>
Handle für das Wasserzeichen-Bitmuster der Eigenschaftenseite.

*hpalWatermark*<br/>
Handle für die Palette der Bitmap für Wasserzeichen und/oder Header Bitmap.

*hbmHeader*<br/>
Handle für die Bitmap "Header" der Eigenschaftenseite.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Memberfunktion auf, wenn einer der Konstruktoren der Klasse nicht bereits aufgerufen wurde. Rufen Sie z. B. `Construct` beim Deklarieren oder Zuordnen von Arrays für `CPropertySheet` Objekte. Im Fall von Arrays, müssen Sie aufrufen `Construct` für jedes Element im Array.

Um das Eigenschaftenfenster anzuzeigen, rufen [DoModal](#domodal) oder [erstellen](#create). Die Zeichenfolge in den ersten Parameter werden in der Titelleiste für das Eigenschaftenblatt platziert werden.

Sie können Bilder von Wasserzeichen und/oder Headerparameter automatisch anzeigen, bei der Verwendung der dritten oder vierten Prototypes `Construct`oben aufgeführten und übergeben Sie gültige Werte für die *HbmWatermark*, *HpalWatermark* , und/oder *HbmHeader* Parameter.

### <a name="example"></a>Beispiel

Im folgende Beispiel wird veranschaulicht, unter welchen Sie Umständen würden Aufrufen `Construct`.

[!code-cpp[NVC_MFCDocView#130](../../mfc/codesnippet/cpp/cpropertysheet-class_2.cpp)]

##  <a name="cpropertysheet"></a>  CPropertySheet::CPropertySheet

Erstellt ein `CPropertySheet`-Objekt.

```
CPropertySheet();

explicit CPropertySheet(
    UINT nIDCaption,
    CWnd* pParentWnd = NULL,
    UINT iSelectPage = 0);

explicit CPropertySheet(
    LPCTSTR pszCaption,
    CWnd* pParentWnd = NULL,
    UINT iSelectPage = 0);

CPropertySheet(
    UINT nIDCaption,
    CWnd* pParentWnd,
    UINT iSelectPage,
    HBITMAP hbmWatermark,
    HPALETTE hpalWatermark = NULL,
    HBITMAP hbmHeader = NULL);

CPropertySheet(
    LPCTSTR pszCaption,
    CWnd* pParentWnd,
    UINT iSelectPage,
    HBITMAP hbmWatermark,
    HPALETTE hpalWatermark = NULL,
    HBITMAP hbmHeader = NULL);
```

### <a name="parameters"></a>Parameter

*nIDCaption*<br/>
Die ID der Beschriftung für das Eigenschaftenblatt verwendet werden.

*pParentWnd*<br/>
Zeigt für das übergeordnete Fenster des Eigenschaftenblatts. Wenn der Wert NULL ist, wird das übergeordnete Fenster das Hauptfenster der Anwendung sein.

*iSelectPage*<br/>
Der Index der Seite, die ursprünglich im Vordergrund. Standardmäßig ist die erste Seite in der Tabelle hinzugefügt.

*pszCaption*<br/>
Verweist auf eine Zeichenfolge, enthält die Beschriftung für das Eigenschaftenblatt verwendet werden. Darf nicht NULL sein.

*hbmWatermark*<br/>
Ein Handle für das Hintergrundbild des Eigenschaftenblatts.

*hpalWatermark*<br/>
Ein Handle für die Palette der Bitmap für Wasserzeichen und/oder Header Bitmap.

*hbmHeader*<br/>
Ein Handle für die Bitmap "Header" der Eigenschaftenseite.

### <a name="remarks"></a>Hinweise

Um das Eigenschaftenfenster anzuzeigen, rufen [DoModal](#domodal) oder [erstellen](#create). Die Zeichenfolge in den ersten Parameter werden in der Titelleiste für das Eigenschaftenblatt platziert werden.

Wenn Sie über mehrere Parameter (z. B., wenn Sie ein Array verwenden) verfügen, verwenden Sie [erstellen](#construct) anstelle von `CPropertySheet`.

Sie können Bilder von Wasserzeichen und/oder Headerparameter automatisch anzeigen, bei der Verwendung der dritten oder vierten Prototypes `CPropertySheet`weiter oben, und übergeben Sie gültige Werte für die *HbmWatermark*, *HpalWatermark*, und / oder *HbmHeader* Parameter.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#131](../../mfc/codesnippet/cpp/cpropertysheet-class_3.cpp)]

##  <a name="create"></a>  CPropertySheet::Create

Zeigt die eines nicht modalen Eigenschaftenblatts an.

```
virtual BOOL Create(CWnd* pParentWnd = NULL,
    DWORD dwStyle = (DWORD)-1,
    DWORD dwExStyle = 0);
```

### <a name="parameters"></a>Parameter

*pParentWnd*<br/>
Verweist auf das übergeordnete Fenster. Wenn NULL, ist der übergeordnete Element dem Desktop.

*dwStyle*<br/>
Window-Stile für Eigenschaftenblatt. Eine vollständige Liste der verfügbaren Formate, finden Sie unter [Window-Stile](../../mfc/reference/styles-used-by-mfc.md#window-styles).

*dwExStyle*<br/>
Erweiterte Fensterstile für Eigenschaftenblatt. Eine vollständige Liste der verfügbaren Formate, finden Sie unter [erweiterte Fensterstile](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles)

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn das Eigenschaftenblatt erfolgreich erstellt wurde; andernfalls 0.

### <a name="remarks"></a>Hinweise

Der Aufruf von `Create` kann innerhalb des Konstruktors oder können Sie ihn aufrufen, nachdem der Konstruktor aufgerufen wird.

Das Standardformat, ausgedrückt durch Übergabe von-1 als *DwStyle*, ist tatsächlich WS_SYSMENU&#124;WS_POPUP&#124;WS_CAPTION&#124;DS_MODALFRAME&#124;DS_CONTEXTHELP&#124;WS_VISIBLE. Der Standardwert erweiterten Fensterstil, übergeben Sie 0 als ausgedrückt *DwExStyle*, tatsächlich WS_EX_DLGMODALFRAME ist.

Die `Create` Memberfunktion zurückgegeben wird, sofort nach dem Erstellen des Eigenschaftenblatts. Aufrufen, um das Eigenschaftenblatt zu zerstören, [CWnd:: DestroyWindow](../../mfc/reference/cwnd-class.md#destroywindow).

Nicht modulare Eigenschaftenblätter angezeigt, die mit einem Aufruf von `Create` keine Schaltflächen OK, "Abbrechen", jetzt übernehmen und Hilfe wie modale Eigenschaftenblätter. Gewünschte Schaltflächen müssen vom Benutzer erstellt werden.

Um ein modales Eigenschaftsblatt anzuzeigen, rufen [DoModal](#domodal) stattdessen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#132](../../mfc/codesnippet/cpp/cpropertysheet-class_4.cpp)]

[!code-cpp[NVC_MFCDocView#133](../../mfc/codesnippet/cpp/cpropertysheet-class_5.cpp)]

##  <a name="domodal"></a>  CPropertySheet:: DoModal

Zeigt ein modales Eigenschaftsblatt an.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Rückgabewert

IDOK oder IDCANCEL, wenn die Funktion erfolgreich war; Andernfalls wird 0 oder -1. Wenn das Eigenschaftenfenster als Assistent eingerichtet wurde (finden Sie unter [SetWizardMode](#setwizardmode)), `DoModal` ID_WIZFINISH oder IDCANCEL zurückgibt.

### <a name="remarks"></a>Hinweise

Der zurückgegebene Wert entspricht der ID des Steuerelements, das das Eigenschaftenblatt zu schließen. Nachdem diese Funktion zurückgibt, werden eine Windows für das Eigenschaftenblatt, und alle Seiten zerstört wurden. Die Objekte selbst sind weiterhin vorhanden. In der Regel rufen Sie Daten aus der [CPropertyPage](../../mfc/reference/cpropertypage-class.md) Objekte nach `DoModal` IDOK zurückgibt.

Rufen Sie zum Anzeigen eines nicht modalen Eigenschaftenblatts [erstellen](#create) stattdessen.

Wenn eine Eigenschaftenseite aus der entsprechenden Dialog-Ressource erstellt wird, kann dies eine nicht abgefangene Ausnahme führen. Dies führt auf der Eigenschaftenseite ändern den Stil der Dialogfeldressource in das erforderliche Format, bevor die Seite erstellt wird. Da Ressourcen im Allgemeinen schreibgeschützt sind, wird dadurch eine Ausnahme aus. Das System die Ausnahme behandelt, und erstellt eine Kopie der geänderten Ressource. Die Ausnahme der ersten Chance kann daher ignoriert werden.

> [!NOTE]
>  Diese Ausnahme muss vom Betriebssystem behandelt werden, wenn Sie mit dem Modell für die asynchrone Ausnahmebehandlung kompilieren. Weitere Informationen über Modelle für die Ausnahmebehandlung finden Sie unter [/EH (Ausnahmebehandlungsmodell)](../../build/reference/eh-exception-handling-model.md). Umschließen Sie in diesem Fall keine Aufrufe von `CPropertySheet::DoModal` mit einem C++-Try / Catch-Block in dem Catch alle Ausnahmen verarbeitet, z. B. `catch (...)`. Dieser Block verarbeiten die Ausnahme, die für das Betriebssystem und die Ursache zu einem unvorhersehbaren Verhalten vorgesehen. Allerdings können Sie problemlos verwenden C++-Ausnahmebehandlung mit bestimmte Ausnahmetypen oder strukturierte Ausnahmebehandlung, in denen die Zugriffsverletzung-Ausnahme für das Betriebssystem über übergeben.

Um zu vermeiden, generiert dieser Ausnahme der ersten Chance, Sie können manuell sicherstellen, dass das Eigenschaftenblatt dem richtigen hat [Window-Stile](../../mfc/reference/styles-used-by-mfc.md#window-styles). Sie müssen die folgenden Formate für ein Eigenschaftenblatt festlegen:

- DS_3DLOOK

- DS_CONTROL

- WS_CHILD

- WS_TABSTOP

Sie können die folgenden optionalen Stile verwenden, ohne dass eine Ausnahme der ersten Chance:

- DS_SHELLFONT

- DS_LOCALEDIT

- WS_CLIPCHILDREN

Deaktivieren Sie alle anderen Windows-Stile, da sie nicht mit Eigenschaftenblättern kompatibel sind. Diese Empfehlung gilt nicht für erweiterte Stile. Dieser standard Stile entsprechend festlegen garantiert, dass das Eigenschaftenblatt muss nicht geändert werden und wird zu vermeiden, dass die Ausnahme der ersten Chance.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CPropertySheet::AddPage](#addpage).

##  <a name="enablestackedtabs"></a>  CPropertySheet::EnableStackedTabs

Gibt an, ob Zeilen mit Registerkarten in einem Eigenschaftenblatt Stapeln.

```
void EnableStackedTabs(BOOL bStacked);
```

### <a name="parameters"></a>Parameter

*bStacked*<br/>
Gibt an, ob es sich bei gestapelte Registerkarten im Eigenschaftenblatt aktiviert sind. Gestapelte Zeilen von Tags zu deaktivieren, indem *bStacked* auf "false".

### <a name="remarks"></a>Hinweise

Wenn ein Eigenschaftenblatt mehrere Registerkarten, die enthält als in einer einzelnen Zeile in der Breite des Eigenschaftenblatts, passen, werden standardmäßig die Registerkarten in mehreren Zeilen Stapeln. Rufen Sie zum Verwenden von fortlaufenden Registerkarten anstelle von Stapeln Registerkarten `EnableStackedTabs` mit *bStacked* auf "false" festgelegt werden, bevor [DoModal](#domodal) oder [erstellen](#create).

Rufen Sie `EnableStackedTabs` bei der Erstellung eines modalen oder eines nicht modalen Eigenschaftenblatts. Integrieren Sie dieses Format in eine `CPropertySheet`-abgeleitete Klasse sein, einen Meldungshandler für WM_CREATE schreiben. In der überschriebenen Version der [CWnd::OnCreate](../../mfc/reference/cwnd-class.md#oncreate), rufen Sie `EnableStackedTabs( FALSE )` vor der Implementierung der Basisklasse aufrufen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#134](../../mfc/codesnippet/cpp/cpropertysheet-class_6.cpp)]

##  <a name="enddialog"></a>  CPropertySheet::EndDialog

Das Eigenschaftenblatt wird beendet.

```
void EndDialog(int nEndID);
```

### <a name="parameters"></a>Parameter

*nEndID*<br/>
Der Bezeichner als Rückgabewert des Eigenschaftenblatts verwendet werden soll.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion wird von Framework aufgerufen, wenn es sich bei der OK, die "Abbrechen" oder die Schaltfläche "Schließen" gedrückt wird. Aufruf, dass diese Memberfunktion auf, wenn ein Ereignis auftritt, das Eigenschaftenfenster geschlossen werden soll.

Diese Memberfunktion wird nur ein modales Dialogfeld verwendet werden.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CPropertySheet::PressButton](#pressbutton).

##  <a name="getactiveindex"></a>  CPropertySheet::GetActiveIndex

Ruft die Indexnummer des Blatt im Eigenschaftsfenster der aktiven Seite und verwendet dann als Parameter für die Anzahl der zurückgegebenen Index `GetPage`.

```
int GetActiveIndex() const;
```

### <a name="return-value"></a>Rückgabewert

Die Indexnummer der aktiven Seite.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CPropertySheet::GetActivePage](#getactivepage).

##  <a name="getactivepage"></a>  CPropertySheet::GetActivePage

Ruft die Eigenschaftenblattfensters für das die aktive Seite ab.

```
CPropertyPage* GetActivePage() const;
```

### <a name="return-value"></a>Rückgabewert

Der Zeiger auf die aktive Seite.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Memberfunktion auf, um eine Aktion auszuführen, auf der aktiven Seite.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#135](../../mfc/codesnippet/cpp/cpropertysheet-class_7.cpp)]

##  <a name="getpage"></a>  CPropertySheet::GetPage

Gibt einen Zeiger auf die angegebene Seite in diesem Eigenschaftenblatt.

```
CPropertyPage* GetPage(int nPage) const;
```

### <a name="parameters"></a>Parameter

*nPage*<br/>
Der gewünschten Seite bei 0 beginnenden Index. Muss zwischen 0 und kleiner als die Anzahl der Seiten im Eigenschaftenblatt, einschließlich sein.

### <a name="return-value"></a>Rückgabewert

Der Zeiger auf der Seite entspricht der *. nSeite* Parameter.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CPropertyPage::OnWizardFinish](../../mfc/reference/cpropertypage-class.md#onwizardfinish).

##  <a name="getpagecount"></a>  CPropertySheet::GetPageCount

Bestimmt die Anzahl der Seiten, die derzeit im Eigenschaftenblatt.

```
int GetPageCount() const;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Seiten im Eigenschaftenblatt.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CPropertyPage::OnWizardFinish](../../mfc/reference/cpropertypage-class.md#onwizardfinish).

##  <a name="getpageindex"></a>  CPropertySheet::GetPageIndex

Ruft die Indexnummer der angegebenen Seite im Eigenschaftenfenster Eigenschaft ab.

```
int GetPageIndex(CPropertyPage* pPage);
```

### <a name="parameters"></a>Parameter

*pPage*<br/>
Zeigt auf der Seite mit dem Index gefunden werden. Darf nicht NULL sein.

### <a name="return-value"></a>Rückgabewert

Die Indexnummer von einer Seite.

### <a name="remarks"></a>Hinweise

Verwenden Sie z. B. `GetPageIndex` auf den Seitenindex zu erhalten, um verwenden [SetActivePage](#setactivepage) oder [GetPage](#getpage).

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CPropertySheet::GetActivePage](#getactivepage).

##  <a name="gettabcontrol"></a>  CPropertySheet::GetTabControl

Ruft einen Zeiger auf ein Registerkarten-Steuerelement, das Registerkarten-Steuerelement für bestimmte Aktionen ausführen müssen (d. h. keine der APIs im [CTabCtrl](../../mfc/reference/ctabctrl-class.md)).

```
CTabCtrl* GetTabControl() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf ein Registerkarten-Steuerelement.

### <a name="remarks"></a>Hinweise

Rufen Sie z. B. diese Memberfunktion auf, wenn Sie die Bitmaps auf den Registerkarten während der Initialisierung hinzufügen möchten.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#136](../../mfc/codesnippet/cpp/cpropertysheet-class_8.cpp)]

##  <a name="m_psh"></a>  CPropertySheet::m_psh

Eine Struktur, deren Mitglieder, die Merkmale des speichern [PROPSHEETHEADER](/windows/desktop/api/prsht/ns-prsht-_propsheetheadera_v2).

### <a name="remarks"></a>Hinweise

Diese Struktur verwenden, um die Darstellung des Eigenschaftenblatts zu initialisieren, sobald es erstellt wurde, aber bevor sie mit angezeigt wird der [DoModal](#domodal) Member-Funktion. Legen Sie z. B. die *DwSize* Mitglied `m_psh` auf die Größe, die Sie möchten des Eigenschaftenblatt zu haben.

Weitere Informationen zu dieser Struktur, einschließlich einer Liste der Member finden Sie unter PROPSHEETHEADER im Windows SDK.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#143](../../mfc/codesnippet/cpp/cpropertysheet-class_9.cpp)]

##  <a name="mapdialogrect"></a>  CPropertySheet::MapDialogRect

Konvertiert die Dialogfeld-Einheiten eines Rechtecks Bildschirm Einheiten.

```
void MapDialogRect(LPRECT lpRect) const;
```

### <a name="parameters"></a>Parameter

*lpRect*<br/>
Verweist auf eine [RECT](/previous-versions/dd162897\(v=vs.85\)) Struktur oder [CRect](../../atl-mfc-shared/reference/crect-class.md) -Objekt, das das Dialogfeld enthält koordiniert, konvertiert werden soll.

### <a name="remarks"></a>Hinweise

Dialogfeld-Einheiten sind im Hinblick auf die aktuellen Dialogfeld-Basiseinheit abgeleitet, die durchschnittliche Breite und Höhe der Zeichen in die Schriftart für Dialogfeld-Text angegeben. Eine horizontale Einheit ist ein Viertel der im Dialogfeld Basis-Width-Komponente und eine vertikale Einheit ist ein Achtel der Dialogfeld-Basis Height-Komponente.

Die [GetDialogBaseUnits](/windows/desktop/api/winuser/nf-winuser-getdialogbaseunits) Windows-Funktion gibt die Größeninformationen für die Systemschriftart, aber Sie können eine andere Schriftart für jedes Eigenschaftenblatt angeben, bei der Verwendung des DS_SETFONT-Stils in der Ressourcendefinition Datei. Die [MapDialogRect](/windows/desktop/api/winuser/nf-winuser-mapdialogrect) Windows-Funktion, beschrieben in das Windows SDK, verwendet die passende Schriftart für das Dialogfeld zu öffnen.

Die `MapDialogRect` Memberfunktion ersetzt die Dialogfeld-Einheiten in *LpRect* mit Bildschirm von Einheiten (in Pixel), damit das Rechteck verwendet werden kann, erstellen ein Dialogfeld oder ein Steuerelement innerhalb eines Felds zu positionieren.

##  <a name="oninitdialog"></a>  CPropertySheet:: OnInitDialog

Außerkraftsetzungen, um das Blatt eigenschafteninitialisierung zu erweitern.

```
virtual BOOL OnInitDialog();
```

### <a name="return-value"></a>Rückgabewert

Gibt an, ob die Anwendung den Eingabefokus auf eines der Steuerelemente im Eigenschaftenfenster Eigenschaft festgelegt wurde. Wenn `OnInitDialog` ungleich NULL zurückgegeben wird, wird Windows den Eingabefokus auf das erste Steuerelement im Eigenschaftenblatt. Die Anwendung kann 0 nur zurück, wenn sie explizit den Eingabefokus auf eines der Steuerelemente im Eigenschaftenfenster Eigenschaft festgelegt wurde.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion wird als Reaktion auf die WM_INITDIALOG-Meldung aufgerufen. Diese Nachricht wird gesendet, in dem Eigenschaftenblatt während der [erstellen](#create) oder [DoModal](#domodal) -Aufrufe, die auftreten, unmittelbar bevor die Eigenschaftenseite angezeigt wird.

Überschreiben Sie diese Memberfunktion auf, wenn müssen Sie durchführen, besondere Bearbeitung, wenn das Eigenschaftenblatt initialisiert wird. In der außer Kraft gesetzte Version, rufen Sie zuerst die Basisklasse `OnInitDialog` aber ignorieren Sie den Rückgabewert. Sie werden normalerweise von Ihrer Funktion überschriebenen Member "true" zurückgeben.

Sie benötigen für diese Member-Funktion keinen Meldungszuordnungseintrags.

##  <a name="pressbutton"></a>  CPropertySheet::PressButton

Simuliert die Auswahl der angegebenen Schaltfläche in einem Eigenschaftenblatt.

```
void PressButton(int nButton);
```

### <a name="parameters"></a>Parameter

*nButton*<br/>
Nschaltfläche: Identifiziert die Schaltfläche gedrückt wird. Dieser Parameter kann einen der folgenden Werte sein:

- PSBTN_BACK wählt die zurück-Taste.

- PSBTN_NEXT wählt die Schaltfläche "Weiter".

- PSBTN_FINISH wählt die Schaltfläche "Fertig stellen".

- PSBTN_OK wählt die Schaltfläche "OK".

- PSBTN_APPLYNOW wählt die Schaltfläche "jetzt übernehmen".

- Von PSBTN_CANCEL zurückgegeben wird, die Schaltfläche "Abbrechen".

- PSBTN_HELP wählt die Schaltfläche "Hilfe".

### <a name="remarks"></a>Hinweise

Finden Sie unter [PSM_PRESSBUTTON](/windows/desktop/Controls/psm-pressbutton) für Weitere Informationen über die Windows SDK Pressbutton-Meldung.

Ein Aufruf von `PressButton` sendet keinen der [PSN_APPLY](/windows/desktop/Controls/psn-apply) Benachrichtigung auf einer Eigenschaftenseite für das Framework. Rufen Sie zum Senden dieser Benachrichtigung [CPropertyPage::OnOK](../../mfc/reference/cpropertypage-class.md#onok).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#137](../../mfc/codesnippet/cpp/cpropertysheet-class_10.cpp)]

##  <a name="removepage"></a>  CPropertySheet::RemovePage

Entfernt eine Seite aus dem Eigenschaftenblatt, und löscht das zugeordnete Fenster.

```
void RemovePage(CPropertyPage* pPage);
void RemovePage(int nPage);
```

### <a name="parameters"></a>Parameter

*pPage*<br/>
Zeigt auf der Seite aus dem Eigenschaftenblatt entfernt werden soll. Darf nicht NULL sein.

*nPage*<br/>
Der Index der Seite entfernt werden soll. Muss zwischen 0 und kleiner als die Anzahl der Seiten im Eigenschaftenblatt, einschließlich sein.

### <a name="remarks"></a>Hinweise

Die [CPropertyPage](../../mfc/reference/cpropertypage-class.md) Objekt selbst wird nicht zerstört, bis der Besitzer des der `CPropertySheet` Fenster geschlossen wird.

##  <a name="setactivepage"></a>  CPropertySheet::SetActivePage

Ändert die aktive Seite an.

```
BOOL SetActivePage(int nPage);
BOOL SetActivePage(CPropertyPage* pPage);
```

### <a name="parameters"></a>Parameter

*nPage*<br/>
Der Index der Seite festlegen. Es muss zwischen 0 und kleiner als die Anzahl der Seiten im Eigenschaftenblatt, einschließlich sein.

*pPage*<br/>
Zeigt auf der Seite, um Sie im Eigenschaftenfenster festgelegt. Es darf nicht NULL sein.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn das Eigenschaftenblatt erfolgreich aktiviert wird; andernfalls 0.

### <a name="remarks"></a>Hinweise

Verwenden Sie z. B. `SetActivePage` Wenn die Aktion eines Benutzers auf einer Seite zur aktiven Seite wird eine andere Seite führen sollten.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CPropertySheet::GetActivePage](#getactivepage).

##  <a name="setfinishtext"></a>  CPropertySheet::SetFinishText

Legt den Text in die Schaltfläche "Fertig stellen".

```
void SetFinishText(LPCTSTR lpszText);
```

### <a name="parameters"></a>Parameter

*lpszText*<br/>
Zeigt auf den Text auf die Schaltfläche "Fertig stellen" angezeigt werden.

### <a name="remarks"></a>Hinweise

Rufen Sie `SetFinishText` zeigt den Text auf die Schaltfläche "Fertig stellen", und blenden die Schaltflächen Weiter und zurück, der Benutzer die Aktion auf der letzten Seite des Assistenten abgeschlossen hat.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#138](../../mfc/codesnippet/cpp/cpropertysheet-class_11.cpp)]

##  <a name="settitle"></a>  CPropertySheet::SetTitle

Gibt die Beschriftung für das Eigenschaftenblatt (der Text, der in der Titelleiste eines Fensters Rahmen angezeigt wird).

```
void SetTitle(
    LPCTSTR lpszText,
    UINT nStyle = 0);
```

### <a name="parameters"></a>Parameter

*nStyle*<br/>
Gibt an, der die Darstellung der Titel des Eigenschaftenblattes. Das Format muss 0 oder als PSH_PROPTITLE angegeben werden. Wenn das Format als PSH_PROPTITLE festgelegt ist, wird das Wort "Eigenschaften" nach dem Text, der als Beschriftung angegeben angezeigt. Zum Beispiel der Aufruf `SetTitle`("Einfach", PSH_PROPTITLE) führt zu einer Beschriftung Eigenschaft Blatt "Einfache Eigenschaften".

*lpszText*<br/>
Zeigt auf den Text als Beschriftung in der Titelleiste des Eigenschaftenblatts verwendet werden.

### <a name="remarks"></a>Hinweise

Standardmäßig verwendet ein Eigenschaftenblatt den Beschriftung-Parameter im Konstruktor Blatt Eigenschaft an.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#139](../../mfc/codesnippet/cpp/cpropertysheet-class_12.cpp)]

##  <a name="setwizardbuttons"></a>  CPropertySheet::SetWizardButtons

Aktiviert oder deaktiviert die Schaltfläche "zurück, Next oder Fertig stellen" in einem Eigenschaftenblatt für den Assistenten.

```
void SetWizardButtons(DWORD dwFlags);
```

### <a name="parameters"></a>Parameter

*dwFlags*<br/>
Ein Satz von Flags, die die Funktion und die Darstellung der Schaltflächen des Assistenten anpassen. Dieser Parameter kann eine Kombination der folgenden Werte sein:

- Die Schaltfläche PSWIZB_BACK zurück

- Schaltfläche "Weiter PSWIZB_NEXT"

- Schaltfläche "PSWIZB_FINISH Fertig stellen"

- Schaltfläche "PSWIZB_DISABLEDFINISH deaktiviert Fertig stellen"

### <a name="remarks"></a>Hinweise

Rufen Sie `SetWizardButtons` erst das Dialogfeld geöffnet ist Sie nicht aufrufen, `SetWizardButtons` vor dem Aufruf [DoModal](#domodal). Rufen Sie in der Regel `SetWizardButtons` aus [CPropertyPage::OnSetActive](../../mfc/reference/cpropertypage-class.md#onsetactive).

Wenn Sie zum Ändern des Texts auf die Schaltfläche "Fertig stellen", oder blenden die nächste und Back-nach des Benutzers Schaltflächen verfügt über den Assistenten abgeschlossen, Aufruf [SetFinishText](#setfinishtext). Beachten Sie, dass die gleiche Schaltfläche für "Finish" und weiter freigegeben ist. Sie können die Beendigung oder eine Schaltfläche "Weiter" gleichzeitig, aber nicht beides anzeigen.

### <a name="example"></a>Beispiel

Ein `CPropertySheet` verfügt über drei Seiten des Assistenten-Eigenschaft: `CStylePage`, `CColorPage`, und `CShapePage`.  Das folgende Codefragment zeigt, wie beim Aktivieren und Deaktivieren der **wieder** und **Weiter** Schaltflächen auf der Seite des Assistenten-Eigenschaft.

[!code-cpp[NVC_MFCDocView#140](../../mfc/codesnippet/cpp/cpropertysheet-class_13.cpp)]

[!code-cpp[NVC_MFCDocView#141](../../mfc/codesnippet/cpp/cpropertysheet-class_14.cpp)]

[!code-cpp[NVC_MFCDocView#138](../../mfc/codesnippet/cpp/cpropertysheet-class_11.cpp)]

##  <a name="setwizardmode"></a>  CPropertySheet::SetWizardMode

Stellt eine Eigenschaftenseite als Assistent her.

```
void SetWizardMode();
```

### <a name="remarks"></a>Hinweise

Ein Hauptmerkmal einer Assistentenseite für die Eigenschaft ist, dass der Benutzer navigiert, verwenden als Nächstes oder Fertig stellen, Sichern und Abbrechen (Schaltflächen) anstelle der Registerkarten.

Rufen Sie `SetWizardMode` vor dem Aufruf [DoModal](#domodal). Nach dem Aufruf von `SetWizardMode`, `DoModal` entweder ID_WIZFINISH (wenn der Benutzer mit der Schaltfläche "Fertig stellen" schließt) oder IDCANCEL zurück.

`SetWizardMode` Legt das Flag PSH_WIZARD fest.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#142](../../mfc/codesnippet/cpp/cpropertysheet-class_15.cpp)]

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel CMNCTRL1](../../overview/visual-cpp-samples.md)<br/>
[MFC-Beispiel CMNCTRL2](../../overview/visual-cpp-samples.md)<br/>
[MFC-Beispiel PROPDLG](../../overview/visual-cpp-samples.md)<br/>
[MFC-Beispiel SNAPVW](../../overview/visual-cpp-samples.md)<br/>
[CWnd-Klasse](../../mfc/reference/cwnd-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)

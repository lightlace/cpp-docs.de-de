---
title: CToolBar-Klasse
ms.date: 11/04/2016
f1_keywords:
- CToolBar
- AFXEXT/CToolBar
- AFXEXT/CToolBar::CToolBar
- AFXEXT/CToolBar::CommandToIndex
- AFXEXT/CToolBar::Create
- AFXEXT/CToolBar::CreateEx
- AFXEXT/CToolBar::GetButtonInfo
- AFXEXT/CToolBar::GetButtonStyle
- AFXEXT/CToolBar::GetButtonText
- AFXEXT/CToolBar::GetItemID
- AFXEXT/CToolBar::GetItemRect
- AFXEXT/CToolBar::GetToolBarCtrl
- AFXEXT/CToolBar::LoadBitmap
- AFXEXT/CToolBar::LoadToolBar
- AFXEXT/CToolBar::SetBitmap
- AFXEXT/CToolBar::SetButtonInfo
- AFXEXT/CToolBar::SetButtons
- AFXEXT/CToolBar::SetButtonStyle
- AFXEXT/CToolBar::SetButtonText
- AFXEXT/CToolBar::SetHeight
- AFXEXT/CToolBar::SetSizes
helpviewer_keywords:
- CToolBar [MFC], CToolBar
- CToolBar [MFC], CommandToIndex
- CToolBar [MFC], Create
- CToolBar [MFC], CreateEx
- CToolBar [MFC], GetButtonInfo
- CToolBar [MFC], GetButtonStyle
- CToolBar [MFC], GetButtonText
- CToolBar [MFC], GetItemID
- CToolBar [MFC], GetItemRect
- CToolBar [MFC], GetToolBarCtrl
- CToolBar [MFC], LoadBitmap
- CToolBar [MFC], LoadToolBar
- CToolBar [MFC], SetBitmap
- CToolBar [MFC], SetButtonInfo
- CToolBar [MFC], SetButtons
- CToolBar [MFC], SetButtonStyle
- CToolBar [MFC], SetButtonText
- CToolBar [MFC], SetHeight
- CToolBar [MFC], SetSizes
ms.assetid: e868da26-5e07-4607-9651-e2f863ad9059
ms.openlocfilehash: ee1820601f80ed270221b3186188793f7fdcbe08
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57301453"
---
# <a name="ctoolbar-class"></a>CToolBar-Klasse

Steuerleisten, die eine Zeile mit Bitmapschaltflächen und optionalen Trennzeichen enthalten.

## <a name="syntax"></a>Syntax

```
class CToolBar : public CControlBar
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CToolBar::CToolBar](#ctoolbar)|Erstellt ein `CToolBar`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CToolBar::CommandToIndex](#commandtoindex)|Gibt den Index einer Schaltfläche mit der angegebenen Befehls-ID.|
|[CToolBar::Create](#create)|Erstellt die Windows-Symbolleiste, und fügt es der `CToolBar` Objekt.|
|[CToolBar::CreateEx](#createex)|Erstellt eine `CToolBar` Objekt mit zusätzlichen Stilen für den eingebetteten `CToolBarCtrl` Objekt.|
|[CToolBar::GetButtonInfo](#getbuttoninfo)|Ruft ab, die ID, Stil und Image-Anzahl, der eine Schaltfläche.|
|[CToolBar::GetButtonStyle](#getbuttonstyle)|Ruft den Stil für eine Schaltfläche ab.|
|[CToolBar::GetButtonText](#getbuttontext)|Ruft den Text ab, der auf eine Schaltfläche angezeigt wird.|
|[CToolBar::GetItemID](#getitemid)|Gibt die Befehls-ID einer Schaltfläche oder ein Trennzeichen am angegebenen Index zurück.|
|[CToolBar::GetItemRect](#getitemrect)|Ruft das Anzeigerechteck für das Element am angegebenen Index ab.|
|[CToolBar::GetToolBarCtrl](#gettoolbarctrl)|Ermöglicht den direkten Zugriff auf die zugrunde liegende allgemeine-Steuerelement.|
|[CToolBar::LoadBitmap](#loadbitmap)|Lädt die Bitmap, die Bitmap-Schaltfläche Bilder enthält.|
|[CToolBar::LoadToolBar](#loadtoolbar)|Lädt eine Symbolleistenressource, die mit dem Ressourcen-Editor erstellt wurden.|
|[CToolBar::SetBitmap](#setbitmap)|Legt ein Bitmapbild fest.|
|[CToolBar::SetButtonInfo](#setbuttoninfo)|Legt fest, die ID, Stil und Image-Anzahl, der eine Schaltfläche.|
|[CToolBar::SetButtons](#setbuttons)|Legt die Schaltfläche-Stile und einen Index der Schaltflächenbilder innerhalb der Bitmap.|
|[CToolBar::SetButtonStyle](#setbuttonstyle)|Legt den Stil für eine Schaltfläche.|
|[CToolBar::SetButtonText](#setbuttontext)|Legt den Text, der angezeigt wird auf eine Schaltfläche fest.|
|[CToolBar::SetHeight](#setheight)|Legt die Höhe der Symbolleiste.|
|[CToolBar::SetSizes](#setsizes)|Legt die Größe der Schaltflächen und ihre Bitmaps fest.|

## <a name="remarks"></a>Hinweise

Die Schaltflächen können sich wie Druckknöpfe, Kontrollkästchen Schaltflächen oder Optionsfelder fungieren. `CToolBar` Objekte sind in der Regel eingebettete Elemente der Rahmenfenster Objekte, die von der Klasse abgeleitet [CFrameWnd](../../mfc/reference/cframewnd-class.md) oder [CMDIFrameWnd](../../mfc/reference/cmdiframewnd-class.md).

[GetToolBarCtrl](#gettoolbarctrl), eine Memberfunktion neue MFC 4.0, können Sie das allgemeine Windows-Steuerelement-Unterstützung für symbolleistenanpassung sowie zusätzliche Funktionen nutzen. `CToolBar` Member-Funktionen bieten Ihnen die meisten Funktionen der allgemeinen Windows-Steuerelemente; Wenn Sie jedoch aufrufen, `GetToolBarCtrl`, Sie können den Symbolleisten erteilen, sogar noch mehr Merkmale der Windows 95/98 Symbolleisten. Beim Aufruf `GetToolBarCtrl`, es gibt einen Verweis auf eine `CToolBarCtrl` Objekt. Finden Sie unter [CToolBarCtrl](../../mfc/reference/ctoolbarctrl-class.md) für Weitere Informationen zum Verwenden von Windows-Standardsteuerelementen Symbolleisten entwerfen. Weitere allgemeine Informationen über allgemeine Steuerelemente, finden Sie unter [Standardsteuerelementen](/windows/desktop/Controls/common-controls-intro) im Windows SDK.

Visual C++ bietet zwei Methoden zum Erstellen einer Symbolleiste. Gehen Sie folgendermaßen vor, um eine Symbolleistenressource, die mit dem Ressourcen-Editor zu erstellen:

1. Erstellen einer Symbolleistenressource.

1. Erstellen der `CToolBar` Objekt.

1. Rufen Sie die [erstellen](#create) (oder [CreateEx](#createex))-Funktion zum Erstellen Sie die Windows-Symbolleiste, und fügen Sie ihn auf die `CToolBar` Objekt.

1. Rufen Sie [LoadToolBar](#loadtoolbar) zum Laden der Symbolleistenressource.

Andernfalls gehen Sie folgendermaßen vor:

1. Erstellen der `CToolBar` Objekt.

1. Rufen Sie die [erstellen](#create) (oder [CreateEx](#createex))-Funktion zum Erstellen Sie die Windows-Symbolleiste, und fügen Sie ihn auf die `CToolBar` Objekt.

1. Rufen Sie [LoadBitmap](#loadbitmap) die Bitmap geladen, die die Symbolleisten-Schaltflächen enthält.

1. Rufen Sie [SetButtons](#setbuttons) auf die Schaltflächen-Formatvorlage festgelegt, und ordnen Sie jede Schaltfläche ein Bild in der Bitmap.

Die Schaltflächenbilder auf der Symbolleiste stammen aus einer einzigen Bitmap, ein Abbild für jede Schaltfläche enthalten muss. Alle Images müssen die gleiche Größe sein. Der Standardwert ist 16 Pixel breit und 15 Pixeln. Images müssen nebeneinander in der Bitmap sein.

Die `SetButtons` Funktion nimmt einen Zeiger auf ein Array von Steuerelement-IDs und eine ganze Zahl, die die Anzahl der Elemente im Array angibt. Die Funktion jeder Schaltfläche-ID auf den Wert des entsprechenden Elements des Arrays festgelegt und weist jede Schaltfläche einen Image-Index, der die Position der das Bild der Schaltfläche in der Bitmap angibt. Wenn ein Arrayelement ID_SEPARATOR Wert verfügt, wird kein Image Index zugewiesen.

Die Reihenfolge der Bilder in der Bitmap ist in der Regel die Reihenfolge, in dem sie auf dem Bildschirm gezeichnet werden, jedoch können Sie, die [SetButtonInfo](#setbuttoninfo) Funktion so ändern Sie die Beziehung zwischen den Image-Reihenfolge und die Zeichnungsreihenfolge.

Alle Schaltflächen einer Symbolleiste haben die gleiche Größe. Der Standardwert ist 24 x 22 Pixel, in Übereinstimmung mit *Richtlinien der Windows-Benutzeroberfläche für den Softwareentwurf*. Alle zusätzlichen Leerraum zwischen den Dimensionen-Image und die Schaltfläche wird verwendet, um einen Rahmen um das Image zu erstellen.

Jede Schaltfläche verfügt über ein Image. Die verschiedenen Zustände Schaltfläche und Stile (gedrückt, oben, unten, deaktiviert ist, deaktiviert unten, und unbestimmt) werden von diesem Image einen generiert. Obwohl Bitmaps auf eine beliebige Farbe sein kann, können Sie die besten Ergebnisse mit Bildern in Schwarz und grauschattierungen erreichen.

> [!WARNING]
> `CToolBar` unterstützt die Bitmaps mit maximal 16 Farben. Wenn Sie ein Bild in einem Symbolleisten-Editor laden, Visual Studio automatisch konvertiert das Bild in eine Bitmap 16 Farben, bei Bedarf, und eine Warnung angezeigt, wenn das Image konvertiert wurde. Wenn Sie ein Image mit mehr als 16 Farben (mit einem externen Editor so bearbeiten Sie das Bild) verwenden, kann die Anwendung unerwartet verhält.

Symbolleisten-Schaltflächen imitieren Druckknöpfe, in der Standardeinstellung. Schaltflächen der Symbolleiste können jedoch auch Schaltflächen mit Kontrollkästchen oder Optionsfelder imitieren. Kontrollkästchen-Einstellungen drei Status aufweisen: aktiviert, deaktiviert und unbestimmt. Optionsfelder nur zwei Zustände aufweisen: aktiviert und deaktiviert.

Rufen Sie zum Festlegen einer einzelnen Schaltfläche oder den Trennzeichenstil ohne verweist auf ein Array [GetButtonStyle](#getbuttonstyle) zum Abrufen des Stils, und rufen dann [SetButtonStyle](#setbuttonstyle) anstelle von `SetButtons`. `SetButtonStyle` ist besonders hilfreich, wenn Sie eine der Stil der Schaltfläche zur Laufzeit ändern möchten.

Aufrufen, um die Zuweisung von Text, der auf eine Schaltfläche angezeigt werden [GetButtonText](#getbuttontext) zum Abrufen des Texts auf der Schaltfläche angezeigt, und rufen Sie anschließend ["SetButtonText"](#setbuttontext) um den Text festzulegen.

Eine Kontrollkästchen-Schaltfläche "erstellen", weisen sie den Stil TBBS_CHECKBOX oder verwenden Sie eine `CCmdUI` des Objekts `SetCheck` Member-Funktion in einem ON_UPDATE_COMMAND_UI-Handler. Aufrufen von `SetCheck` Pushbutton in einem Kontrollkästchen-Schaltfläche aktiviert. Übergeben Sie `SetCheck` einem Argument von 0 für deaktiviert, 1 für die aktivierten oder 2 für unbestimmt.

Erstellen ein Optionsfeld, rufen eine [CCmdUI](../../mfc/reference/ccmdui-class.md) des Objekts [SetRadio](../../mfc/reference/ccmdui-class.md#setradio) Member-Funktion von einem ON_UPDATE_COMMAND_UI-Ereignishandler. Übergeben Sie `SetRadio` einem Argument von 0 deaktiviert oder ungleich NULL für überprüft. Um sich gegenseitig ausschließende Verhalten einer Optionsfeldgruppe zu gewährleisten, müssen Sie in der Gruppe ON_UPDATE_COMMAND_UI-Handler für alle Schaltflächen verfügen.

Weitere Informationen zur Verwendung von `CToolBar`, finden Sie im Artikel [Implementieren der MFC-Symbolleiste](../../mfc/mfc-toolbar-implementation.md) und [technischer Hinweis 31: Steuerleisten](../../mfc/tn031-control-bars.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CControlBar](../../mfc/reference/ccontrolbar-class.md)

`CToolBar`

## <a name="requirements"></a>Anforderungen

**Header:** afxext.h

##  <a name="commandtoindex"></a>  CToolBar::CommandToIndex

Diese Memberfunktion gibt den Index der ersten Symbolleisten-Schaltfläche, beginnend an Position 0 (null), dessen Befehls-ID entspricht zurück `nIDFind`.

```
int CommandToIndex(UINT nIDFind) const;
```

### <a name="parameters"></a>Parameter

*nIDFind*<br/>
Befehls-ID, der eine Symbolleisten-Schaltfläche.

### <a name="return-value"></a>Rückgabewert

Der Index der Schaltfläche oder -1, wenn keine Schaltfläche über die angegebenen Befehls-ID verfügt

##  <a name="create"></a>  Symbolleistenformate

Diese Memberfunktion erstellt eine Windows-Symbolleiste (ein untergeordnetes Fenster) und ordnet ihn dem `CToolBar` Objekt.

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_TOP,
    UINT nID = AFX_IDW_TOOLBAR);
```

### <a name="parameters"></a>Parameter

*pParentWnd*<br/>
Zeiger auf das Fenster, das Sie auf der Symbolleiste übergeordnet ist.

*dwStyle*<br/>
Der Stil für die Symbolleiste. Zusätzliche Toolbar-Stile, die unterstützt werden:

- CBRS_TOP Steuerleiste ist am oberen Rand des Fensters Frame.

- CBRS_BOTTOM Steuerleiste ist am unteren Rand der Frame-Fensters.

- CBRS_NOALIGN Steuerleiste ist nicht neu angeordnet, wenn das übergeordnete Element geändert wird.

- CBRS_TOOLTIPS-Steuerleiste werden QuickInfos angezeigt.

- CBRS_SIZE_DYNAMIC Steuerleiste ist dynamisch.

- CBRS_SIZE_FIXED Steuerleiste wurde behoben.

- CBRS_FLOATING Steuerleiste unverankert ist.

- CBRS_FLYBY-Statusleiste zeigt Informationen über die Schaltfläche.

- Steuerleiste CBRS_HIDE_INPLACE wird dem Benutzer nicht angezeigt.

*nID*<br/>
Der Symbolleiste auf die untergeordneten Fensters-ID.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Auch festgelegt die Höhe der Symbolleiste auf den Standardwert.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#179](../../mfc/codesnippet/cpp/ctoolbar-class_1.cpp)]

##  <a name="createex"></a>  CToolBar::CreateEx

Mit dieser Funktion können Sie zum Erstellen einer Windows-Symbolleiste (ein untergeordnetes Fenster), und ordnen Sie sie der `CToolBar` Objekt.

```
virtual BOOL CreateEx(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle = TBSTYLE_FLAT,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_ALIGN_TOP,
    CRect rcBorders = CRect(
    0,
    0,
    0,
    0),
    UINT nID = AFX_IDW_TOOLBAR);
```

### <a name="parameters"></a>Parameter

*pParentWnd*<br/>
Zeiger auf das Fenster, das Sie auf der Symbolleiste übergeordnet ist.

*dwCtrlStyle*<br/>
Weitere Formate für die Erstellung der eingebetteten [CToolBarCtrl](../../mfc/reference/ctoolbarctrl-class.md) Objekt. Standardmäßig ist dieser Wert auf TBSTYLE_FLAT festgelegt. Eine vollständige Liste der Toolbar-Stile, finden Sie unter *DwStyle*.

*dwStyle*<br/>
Der Stil für die Symbolleiste. Finden Sie unter [Toolbar-Steuerelement und Button-Stile](/windows/desktop/Controls/toolbar-control-and-button-styles) im Windows SDK für eine Liste der entsprechenden Formate.

*rcBorders*<br/>
Ein [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt, das die Breite der Symbolleiste im Fensterrahmen definiert. Dieser Rahmen werden um 0,0,0,0 standardmäßig in einem Symbolleistenfenster mit keine Rahmen Ergebnis festgelegt.

*nID*<br/>
Der Symbolleiste auf die untergeordneten Fensters-ID.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Auch festgelegt die Höhe der Symbolleiste auf den Standardwert.

Verwendung `CreateEx`, anstelle von [erstellen](#create), wenn bestimmte Formate während der Erstellung der eingebetteten ToolBar-Steuerelement vorhanden sein müssen. Legen Sie z. B. *DwCtrlStyle* zu TBSTYLE_FLAT &#124; TBSTYLE_TRANSPARENT zum Erstellen einer Symbolleiste, die die Internet Explorer 4 Symbolleisten ähnelt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#180](../../mfc/codesnippet/cpp/ctoolbar-class_2.cpp)]

##  <a name="ctoolbar"></a>  CToolBar::CToolBar

Diese Memberfunktion erstellt eine `CToolBar` -Objekt und legt die Standard-Größen.

```
CToolBar();
```

### <a name="remarks"></a>Hinweise

Rufen Sie die [erstellen](#create) Memberfunktion, um das Symbolleistenfenster zu erstellen.

##  <a name="getbuttoninfo"></a>  CToolBar::GetButtonInfo

Diese Memberfunktion Ruft die Steuerelement-ID, Stil und Bildindex des der Symbolleisten-Schaltfläche oder ein Trennzeichen, an dem vom angegebenen Speicherort *nIndex.*

```
void GetButtonInfo(
    int nIndex,
    UINT& nID,
    UINT& nStyle,
    int& iImage) const;
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Der Index des der Symbolleisten-Schaltfläche oder ein Trennzeichen ist, zu der Informationen abgerufen werden.

*nID*<br/>
Verweis auf eine "uint", die auf die Befehls-ID der Schaltfläche festgelegt wird.

*nStyle*<br/>
Verweis auf eine "uint", die den Stil der Schaltfläche festgelegt wird.

*iImage*<br/>
Verweis auf eine ganze Zahl, die auf den Index der das Bild der Schaltfläche innerhalb der Bitmap festgelegt ist.

### <a name="remarks"></a>Hinweise

Diese Werte werden zugewiesen, auf die verwiesen wird, indem Sie Variablen *nID*, *nStyle*, und *iImage*. Der Bildindex ist die Position des Bilds innerhalb der Bitmap, die Images für die Symbolleisten-Schaltflächen enthält. Das erste Bild wird an Position 0.

Wenn *nIndex* gibt ein Trennzeichen, *iImage* auf die trennzeichenbreite in Pixel festgelegt ist.

##  <a name="getbuttonstyle"></a>  CToolBar::GetButtonStyle

Rufen Sie diese Memberfunktion um den Stil einer Schaltfläche oder ein Trennzeichen auf der Symbolleiste abzurufen.

```
UINT GetButtonStyle(int nIndex) const;
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Der Index für den Symbolleisten-Schaltfläche oder ein Trennzeichen Stil abgerufen werden sollen.

### <a name="return-value"></a>Rückgabewert

Die Darstellung der Schaltfläche oder ein Trennzeichen, die anhand des *nIndex*.

### <a name="remarks"></a>Hinweise

Einer der Stil der Schaltfläche bestimmt, wie die Schaltfläche angezeigt wird und wie er auf Benutzereingaben reagiert. Finden Sie unter [SetButtonStyle](#setbuttonstyle) Beispiele für Button-Stile.

##  <a name="getbuttontext"></a>  CToolBar::GetButtonText

Rufen Sie diese Memberfunktion zum Abrufen des Texts, der auf eine Schaltfläche angezeigt wird.

```
CString GetButtonText(int nIndex) const;

void GetButtonText(
    int nIndex,
    CString& rString) const;
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Der Index des Texts abgerufen werden sollen.

*rString*<br/>
Ein Verweis auf eine [CString](../../atl-mfc-shared/reference/cstringt-class.md) Objekt, enthält den Text abgerufen werden sollen.

### <a name="return-value"></a>Rückgabewert

Ein `CString` -Objekt, das den Text der Schaltfläche enthält.

### <a name="remarks"></a>Hinweise

Die zweite Form dieses Members-Funktion füllt eine `CString` Objekt mit der Text der Zeichenfolge.

##  <a name="getitemid"></a>  CToolBar::GetItemID

Diese Memberfunktion gibt die Befehls-ID der Schaltfläche oder ein Trennzeichen, die anhand des *nIndex*.

```
UINT GetItemID(int nIndex) const;
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Der Index des Elements, dessen ID abgerufen werden sollen.

### <a name="return-value"></a>Rückgabewert

Die Befehls-ID der Schaltfläche oder ein Trennzeichen, die anhand des *nIndex*.

### <a name="remarks"></a>Hinweise

Trennzeichen zurück ID_SEPARATOR

##  <a name="getitemrect"></a>  CToolBar::GetItemRect

Diese Member-Funktion füllt die `RECT` Struktur, deren Adresse sich im befindet *LpRect* mit den Koordinaten der der Schaltfläche oder ein Trennzeichen, die anhand des *nIndex*.

```
virtual void GetItemRect(
    int nIndex,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Der Index des Elements (Schaltfläche oder ein Trennzeichen), dessen Rechteckkoordinaten sind, abgerufen werden sollen.

*lpRect*<br/>
Adresse von der [RECT](/windows/desktop/api/windef/ns-windef-tagrect) -Struktur, die Koordinaten für das Element enthält.

### <a name="remarks"></a>Hinweise

Koordinaten werden in Pixel relativ zur oberen linken Ecke der Symbolleiste.

Verwendung `GetItemRect` um die Koordinaten eines Trennzeichens erhalten Sie mit einem Kombinationsfeld oder ein anderes Steuerelement ersetzen möchten.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CToolBar::SetSizes](#setsizes).

##  <a name="gettoolbarctrl"></a>  GetToolBarCtrl

Diese Memberfunktion ermöglicht den direkten Zugriff auf die zugrunde liegende allgemeine-Steuerelement.

```
CToolBarCtrl& GetToolBarCtrl() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf ein `CToolBarCtrl`-Objekt.

### <a name="remarks"></a>Hinweise

Verwendung `GetToolBarCtrl` nutzen die Funktionalität des allgemeinen Windows Symbolleisten-Steuerelements, und die Unterstützung nutzen [CToolBarCtrl](../../mfc/reference/ctoolbarctrl-class.md) stellt zum Anpassen von Symbolleisten bereit.

Weitere Informationen zum Verwenden von allgemeinen Steuerelementen finden Sie im Artikel [Steuerelemente](../../mfc/controls-mfc.md) und [Standardsteuerelementen](/windows/desktop/Controls/common-controls-intro) im Windows SDK.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocViewSDI#15](../../mfc/codesnippet/cpp/ctoolbar-class_3.cpp)]

##  <a name="loadbitmap"></a>  CToolBar::LoadBitmap

Rufen Sie diese Memberfunktion zum Laden der Bitmap, die anhand des `lpszResourceName` oder `nIDResource`.

```
BOOL LoadBitmap(LPCTSTR lpszResourceName);
BOOL LoadBitmap(UINT nIDResource);
```

### <a name="parameters"></a>Parameter

*lpszResourceName*<br/>
Zeiger auf den Ressourcennamen der Bitmap geladen werden.

*nIDResource*<br/>
Ressourcen-ID der Bitmap geladen werden.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Die Bitmap muss es sich um ein Abbild für jede Symbolleisten-Schaltfläche enthalten. Wenn die Images nicht vom die Standardgröße (16 Pixel breit und 15 Pixeln) Aufruf [SetSizes](#setsizes) auf die Schaltfläche Größen und Images festlegen.

> [!WARNING]
> `CToolBar` unterstützt die Bitmaps mit maximal 16 Farben. Wenn Sie ein Bild in einem Symbolleisten-Editor laden, Visual Studio automatisch konvertiert das Bild in eine Bitmap 16 Farben, bei Bedarf, und eine Warnung angezeigt, wenn das Image konvertiert wurde. Wenn Sie ein Image mit mehr als 16 Farben (mit einem externen Editor so bearbeiten Sie das Bild) verwenden, kann die Anwendung unerwartet verhält.

##  <a name="loadtoolbar"></a>  CToolBar::LoadToolBar

Rufen Sie diese Memberfunktion zum Laden der Symbolleiste, die anhand des *LpszResourceName* oder *nIDResource*.

```
BOOL LoadToolBar(LPCTSTR lpszResourceName);
BOOL LoadToolBar(UINT nIDResource);
```

### <a name="parameters"></a>Parameter

*lpszResourceName*<br/>
Zeiger auf den Ressourcennamen der Symbolleiste geladen werden.

*nIDResource*<br/>
Ressourcen-ID der Symbolleiste geladen werden.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Finden Sie unter [Symbolleisten-Editor](../../windows/toolbar-editor.md) in Weitere Informationen zum Erstellen einer Symbolleistenressource.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CToolBar::CreateEx](#createex).

##  <a name="setbitmap"></a>  CToolBar::SetBitmap

Rufen Sie diese Memberfunktion, um das Bitmap-Bild für die Symbolleiste festzulegen.

```
BOOL SetBitmap(HBITMAP hbmImageWell);
```

### <a name="parameters"></a>Parameter

*hbmImageWell*<br/>
Handle einer Bitmap, die eine Symbolleiste zugeordnet ist.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Rufen Sie z. B. `SetBitmap` als Bitmap verfügbares Bild zu ändern, nachdem der Benutzer eine Aktion in einem Dokument ausführt, die die Aktion einer Schaltfläche ändert.

##  <a name="setbuttoninfo"></a>  CToolBar::SetButtonInfo

Rufen Sie diese Memberfunktion zum Festlegen der Befehls-ID, Stil und Image-Anzahl der Schaltfläche.

```
void SetButtonInfo(
    int nIndex,
    UINT nID,
    UINT nStyle,
    int iImage);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Nullbasierte Index der Schaltfläche oder ein Trennzeichen, die für den Informationen sind, festgelegt werden.

*nID*<br/>
Der Wert, der auf den Befehls-ID der Schaltfläche festgelegt ist.

*nStyle*<br/>
Die neue Schaltflächen-Formatvorlage. Die folgenden Button-Stile werden unterstützt:

- TBBS_BUTTON standardmäßige Pushbutton (Standard)

- TBBS_SEPARATOR Trennzeichen

- TBBS_CHECKBOX automatisch Kontrollkästchen Schaltfläche

- TBBS_GROUP kennzeichnet den Anfang einer Gruppe von Schaltflächen

- TBBS_CHECKGROUP kennzeichnet den Anfang einer Gruppe von Kontrollkästchen-Schaltflächen

- TBBS_DROPDOWN erstellt eine Dropdown-Listenfeld-Schaltfläche.

- TBBS_AUTOSIZE, die die Breite der Schaltfläche berechnet werden sollen, basierend auf den Text der Schaltfläche nicht auf die Größe des Bilds.

- TBBS_NOPREFIX müssen den Text der Schaltfläche kein Accelerator-Präfix zugeordnet.

*iImage*<br/>
Neue Index für das Bild der Schaltfläche innerhalb der Bitmap.

### <a name="remarks"></a>Hinweise

Diese Funktion legt für Trennzeichen, die den Stil TBBS_SEPARATOR verfügen, das Trennzeichen für die Breite in Pixel um den Wert, der in gespeicherten *iImage*.

> [!NOTE]
>  Sie können auch festlegen, Schaltflächenstatus mithilfe der *nStyle* Parameter, aber da Schaltflächenstatus von gesteuert werden die [ON_UPDATE_COMMAND_UI](message-map-macros-mfc.md#on_update_command_ui) Handler auf, einen Status Sie festlegen, über `SetButtonInfo` verloren während der Verarbeitung der nächsten im Leerlauf befindet. Finden Sie unter [Aktualisieren von Benutzeroberflächenobjekten](../../mfc/how-to-update-user-interface-objects.md) und [TN031: Steuerleisten](../../mfc/tn031-control-bars.md) für Weitere Informationen.

Informationen zu Schaltflächen und Bitmapbilder, finden Sie unter den [CToolBar](../../mfc/reference/ctoolbar-class.md) Übersicht und [CToolBar::LoadBitmap](#loadbitmap).

##  <a name="setbuttons"></a>  CToolBar::SetButtons

Diese Memberfunktion wird die Befehls-ID für jede der Symbolleisten-Schaltfläche auf den Wert, der durch das entsprechende Element des Arrays angegeben *LpIDArray*.

```
BOOL SetButtons(
    const UINT* lpIDArray,
    int nIDCount);
```

### <a name="parameters"></a>Parameter

*lpIDArray*<br/>
Zeiger auf ein Array mit Befehls-Ids. Es kann NULL, um leere Schaltflächen zugeordnet sein.

*nIDCount*<br/>
Anzahl der Elemente im Array zeigt *LpIDArray*.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Wenn ein Element des Arrays der Wert ID_SEPARATOR verfügt, wird eine Trennzeichen in der entsprechenden Position der Symbolleiste erstellt. Diese Funktion auch jede Schaltfläche-Formatvorlage TBBS_BUTTON und jede Trennzeichenstil zu TBBS_SEPARATOR, und jede Schaltfläche einen Bildindex zugewiesen. Der Bildindex gibt die Position der das Bild der Schaltfläche innerhalb der Bitmap an.

Sie müssen nicht für Trennzeichen in der Bitmap zu berücksichtigen, da diese Funktion nicht Bildindizes für Trennzeichen zuweist. Wenn eine Symbolleiste Schaltflächen an den Positionen 0 verfügt, werden 1 und 3 und ein Trennzeichen an Position 2, die Bilder an den Positionen, die in der Bitmap 0, 1 und 2 auf die Schaltflächen an den Positionen, 0, 1 und 3, zugewiesen.

Wenn *LpIDArray* NULL ist, weist diese Funktion Speicherplatz für die Anzahl der Elemente, die anhand des *nIDCount*. Verwendung [SetButtonInfo](#setbuttoninfo) jedes Elements Attribute festlegen.

##  <a name="setbuttonstyle"></a>  CToolBar::SetButtonStyle

Rufen Sie diese Memberfunktion um den Stil einer Schaltfläche oder ein Trennzeichen oder gruppieren festzulegen.

```
void SetButtonStyle(
    int nIndex,
    UINT nStyle);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Der Index der Schaltfläche oder ein Trennzeichen ist, dessen Informationen festgelegt werden.

*nStyle*<br/>
Das Schaltflächen-Formatvorlage. Die folgenden Button-Stile werden unterstützt:

- TBBS_BUTTON standardmäßige Pushbutton (Standard)

- TBBS_SEPARATOR Trennzeichen

- TBBS_CHECKBOX automatisch Kontrollkästchen Schaltfläche

- TBBS_GROUP kennzeichnet den Anfang einer Gruppe von Schaltflächen

- TBBS_CHECKGROUP kennzeichnet den Anfang einer Gruppe von Kontrollkästchen-Schaltflächen

- TBBS_DROPDOWN erstellt eine Dropdown-Listenfeld-Schaltfläche

- TBBS_AUTOSIZE, die die Breite der Schaltfläche berechnet werden basierend auf den Text der Schaltfläche nicht auf die Größe des Bilds

- TBBS_NOPREFIX den Text der Schaltfläche ein Accelerator-Präfix zugeordnet haben keinen

### <a name="remarks"></a>Hinweise

Einer der Stil der Schaltfläche bestimmt, wie die Schaltfläche angezeigt wird und wie er auf Benutzereingaben reagiert.

Vor dem Aufruf `SetButtonStyle`, rufen Sie die [GetButtonStyle](#getbuttonstyle) Memberfunktion versucht, den Stil Schaltfläche oder ein Trennzeichen abzurufen.

> [!NOTE]
>  Sie können auch festlegen, Schaltflächenstatus mithilfe der *nStyle* Parameter, aber da Schaltflächenstatus von gesteuert werden die [ON_UPDATE_COMMAND_UI](message-map-macros-mfc.md#on_update_command_ui) Handler auf, einen Status Sie festlegen, über `SetButtonStyle` verloren während der Verarbeitung der nächsten im Leerlauf befindet. Finden Sie unter [Aktualisieren von Benutzeroberflächenobjekten](../../mfc/how-to-update-user-interface-objects.md) und [TN031: Steuerleisten](../../mfc/tn031-control-bars.md) für Weitere Informationen.

##  <a name="setbuttontext"></a>  CToolBar::SetButtonText

Rufen Sie diese Funktion, um den Text auf einer Schaltfläche festzulegen.

```
BOOL SetButtonText(
    int nIndex,
    LPCTSTR lpszText);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Der Index der Schaltfläche, dessen Text befindet, festgelegt werden.

*lpszText*<br/>
Zeigt auf den Text auf einer Schaltfläche festgelegt werden.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [GetToolBarCtrl](#gettoolbarctrl).

##  <a name="setheight"></a>  CToolBar::SetHeight

Diese Memberfunktion legt der Symbolleiste auf die Höhe auf den Wert in Pixel im angegebenen *CyHeight*.

```
void SetHeight(int cyHeight);
```

### <a name="parameters"></a>Parameter

*cyHeight*<br/>
Die Höhe in Pixel der Symbolleiste.

### <a name="remarks"></a>Hinweise

Nach dem Aufruf [SetSizes](#setsizes), verwenden Sie diese Memberfunktion auf, um die Höhe der Standardsymbolleiste überschreiben. Wenn die Höhe zu klein ist, werden die Schaltflächen am unteren Rand abgeschnitten.

Wenn diese Funktion nicht aufgerufen wird, verwendet das Framework die Größe der Schaltfläche, um zu bestimmen, der die Höhe der Symbolleiste.

##  <a name="setsizes"></a>  CToolBar::SetSizes

Rufen Sie diese Memberfunktion, um die Schaltflächen der Symbolleiste auf die Größe in Pixel im angegebenen festzulegen *SizeButton*.

```
void SetSizes(
    SIZE sizeButton,
    SIZE sizeImage);
```

### <a name="parameters"></a>Parameter

*sizeButton*<br/>
Die Größe in Pixel der einzelnen Schaltflächen.

*sizeImage*<br/>
Die Größe des jedes Bilds in Pixel an.

### <a name="remarks"></a>Hinweise

Die *SizeImage* Parameter darf die Größe der Bilder in der Symbolleiste auf die Bitmap in Pixel. Die Dimensionen in *SizeButton* muss ausreichend, um das Bild plus 7 Pixel, die zusätzliche Breite und zusätzliche in Höhe von 6 Pixel enthalten sein. Diese Funktion legt auch die Höhe der Symbolleiste die Schaltflächen anpassen.

Rufen Sie diese Memberfunktion nur für Symbolleisten, die nicht folgen *Richtlinien der Windows-Benutzeroberfläche für den Softwareentwurf* Empfehlungen für die Schaltfläche und Image-Größen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCListView#8](../../atl/reference/codesnippet/cpp/ctoolbar-class_4.cpp)]

## <a name="see-also"></a>Siehe auch

[MFC-Muster CTRLBARS](../../visual-cpp-samples.md)<br/>
[MFC-Beispiel DLGCBR32](../../visual-cpp-samples.md)<br/>
[MFC-Beispiel DOCKTOOL](../../visual-cpp-samples.md)<br/>
[CControlBar-Klasse](../../mfc/reference/ccontrolbar-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CToolBarCtrl-Klasse](../../mfc/reference/ctoolbarctrl-class.md)<br/>
[CControlBar-Klasse](../../mfc/reference/ccontrolbar-class.md)

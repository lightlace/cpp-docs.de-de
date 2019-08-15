---
title: Cmfcdropdowntoolbarbutton-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMFCDropDownToolbarButton
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::CMFCDropDownToolbarButton
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::CopyFrom
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::DropDownToolbar
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::ExportToMenuButton
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::GetDropDownToolBar
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::IsDropDown
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::IsExtraSize
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnCalculateSize
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnChangeParentWnd
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnClick
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnClickUp
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnContextHelp
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnCustomizeMenu
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnDraw
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnDrawOnCustomizeList
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::Serialize
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::SetDefaultCommand
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::m_uiShowBarDelay
helpviewer_keywords:
- CMFCDropDownToolbarButton [MFC], CMFCDropDownToolbarButton
- CMFCDropDownToolbarButton [MFC], CopyFrom
- CMFCDropDownToolbarButton [MFC], DropDownToolbar
- CMFCDropDownToolbarButton [MFC], ExportToMenuButton
- CMFCDropDownToolbarButton [MFC], GetDropDownToolBar
- CMFCDropDownToolbarButton [MFC], IsDropDown
- CMFCDropDownToolbarButton [MFC], IsExtraSize
- CMFCDropDownToolbarButton [MFC], OnCalculateSize
- CMFCDropDownToolbarButton [MFC], OnChangeParentWnd
- CMFCDropDownToolbarButton [MFC], OnClick
- CMFCDropDownToolbarButton [MFC], OnClickUp
- CMFCDropDownToolbarButton [MFC], OnContextHelp
- CMFCDropDownToolbarButton [MFC], OnCustomizeMenu
- CMFCDropDownToolbarButton [MFC], OnDraw
- CMFCDropDownToolbarButton [MFC], OnDrawOnCustomizeList
- CMFCDropDownToolbarButton [MFC], Serialize
- CMFCDropDownToolbarButton [MFC], SetDefaultCommand
- CMFCDropDownToolbarButton [MFC], m_uiShowBarDelay
ms.assetid: bc9d69e6-bd3e-4c15-9368-e80a504a0ba7
ms.openlocfilehash: fcfb521e309463da81d0064451297b3b73610d2f
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69505323"
---
# <a name="cmfcdropdowntoolbarbutton-class"></a>Cmfcdropdowntoolbarbutton-Klasse

Ein Symbolleisten-Schaltflächentyp, der sich wie eine normale Schaltfläche verhält, wenn darauf geklickt wird. Es wird jedoch eine Dropdown-Symbolleiste ( [cmfcdropdowntoolbar-Klasse](../../mfc/reference/cmfcdropdowntoolbar-class.md) ) geöffnet, wenn der Benutzer die Symbolleisten-Schaltfläche drückt und gedrückt hält.

## <a name="syntax"></a>Syntax

```
class CMFCDropDownToolbarButton : public CMFCToolBarButton
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[Cmfcdropdowntoolbarbutton:: cmfcdropdowntoolbarbutton](#cmfcdropdowntoolbarbutton)|Erstellt ein `CMFCDropDownToolbarButton`-Objekt.|
|`CMFCDropDownToolbarButton::~CMFCDropDownToolbarButton`|Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCDropDownToolbarButton::CopyFrom](#copyfrom)|Kopiert die Eigenschaften einer anderen Symbolleisten Schaltfläche in die aktuelle Schaltfläche. (Überschreibt [cmfctoolbarbutton:: CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom).)|
|`CMFCDropDownToolbarButton::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|
|[CMFCDropDownToolbarButton::DropDownToolbar](#dropdowntoolbar)|Öffnet eine Dropdown-Symbolleiste.|
|[CMFCDropDownToolbarButton::ExportToMenuButton](#exporttomenubutton)|Kopiert Text von der Symbolleisten-Schaltfläche in ein Menü. (Überschreibt [cmfctoolbarbutton:: exporttomendubutton](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton).)|
|[CMFCDropDownToolbarButton::GetDropDownToolBar](#getdropdowntoolbar)|Ruft die Dropdown-Symbolleiste ab, die der Schaltfläche zugeordnet ist.|
|`CMFCDropDownToolbarButton::GetThisClass`|Wird vom Framework verwendet, um einen Zeiger auf das [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt abzurufen, das diesem Klassentyp zugeordnet ist.|
|[CMFCDropDownToolbarButton::IsDropDown](#isdropdown)|Bestimmt, ob die Dropdown-Symbolleiste aktuell geöffnet ist.|
|[Cmfcdropdowntoolbarbutton:: isextrasize](#isextrasize)|Bestimmt, ob die Schaltfläche mit einem erweiterten Rahmen angezeigt werden kann. (Überschreibt [cmfctoolbarbutton:: isextrasize](../../mfc/reference/cmfctoolbarbutton-class.md#isextrasize).)|
|[Cmfcdropdowntoolbarbutton:: oncalculatesize](#oncalculatesize)|Wird von Framework aufgerufen, um die Größe der Schaltfläche für den angegebenen Gerätekontext und den Andock Zustand zu berechnen. (Überschreibt [cmfctoolbarbutton:: oncalculatesize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize).)|
|`CMFCDropDownToolbarButton::OnCancelMode`|Wird von Framework aufgerufen, um die [WM_CANCELMODE](/windows/win32/winmsg/wm-cancelmode) -Nachricht zu verarbeiten. (Überschreibt `CMCToolBarButton::OnCancelMode`.)|
|[CMFCDropDownToolbarButton::OnChangeParentWnd](#onchangeparentwnd)|Wird von Framework aufgerufen, wenn die Schaltfläche in eine neue Symbolleiste eingefügt wird. (Überschreibt [cmfctoolbarbutton:: onchangeparser](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd).)|
|[Cmfcdropdowntoolbarbutton:: OnClick](#onclick)|Wird von Framework aufgerufen, wenn der Benutzer auf die Maustaste klickt. (Überschreibt [cmfctoolbarbutton:: OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick).)|
|[CMFCDropDownToolbarButton::OnClickUp](#onclickup)|Wird von Framework aufgerufen, wenn der Benutzer die Maustaste loslässt. (Überschreibt [cmfctoolbarbutton:: onclickup](../../mfc/reference/cmfctoolbarbutton-class.md#onclickup).)|
|[CMFCDropDownToolbarButton::OnContextHelp](#oncontexthelp)|Wird von Framework aufgerufen, wenn die übergeordnete Symbolleiste eine WM_HELPHITTEST-Meldung behandelt. (Überschreibt [cmfctoolbarbutton:: oncontexthelp](../../mfc/reference/cmfctoolbarbutton-class.md#oncontexthelp).)|
|[Cmfcdropdowntoolbarbutton:: oncustomizemdeu](#oncustomizemenu)|Ändert das bereitgestellte Menü, wenn die Anwendung ein Kontextmenü auf der übergeordneten Symbolleiste anzeigt. (Überschreibt [cmfctoolbarbutton:: oncustomizemdeu](../../mfc/reference/cmfctoolbarbutton-class.md#oncustomizemenu).)|
|[Cmfcdropdowntoolbarbutton:: OnDraw](#ondraw)|Wird von Framework aufgerufen, um die Schaltfläche mithilfe der angegebenen Stile und Optionen zu zeichnen. (Überschreibt [cmfctoolbarbutton:: OnDraw](../../mfc/reference/cmfctoolbarbutton-class.md#ondraw).)|
|[CMFCDropDownToolbarButton::OnDrawOnCustomizeList](#ondrawoncustomizelist)|Wird von Framework aufgerufen, um die Schaltfläche im **Befehls** Bereich des Dialog Felds **Anpassen** zu zeichnen. (Überschreibt [cmfctoolbarbutton:: ondrawoncustomizelist](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist).)|
|[Cmfcdropdowntoolbarbutton:: Serialize](#serialize)|Liest dieses Objekt aus einem Archiv oder schreibt es in ein Archiv. (Überschreibt [cmfctoolbarbutton:: Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize).)|
|[CMFCDropDownToolbarButton::SetDefaultCommand](#setdefaultcommand)|Legt den Standardbefehl fest, den das Framework verwendet, wenn ein Benutzer auf die Schaltfläche klickt.|

### <a name="data-members"></a>Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CMFCDropDownToolbarButton::m_uiShowBarDelay](#m_uishowbardelay)|Gibt die Zeitspanne an, in der ein Benutzer die Maustaste gedrückt halten muss, bevor die Dropdown-Symbolleiste angezeigt wird.|

## <a name="remarks"></a>Hinweise

Ein `CMFCDropDownToolBarButton` unterscheidet sich von einer normalen Schaltfläche dahin, dass es einen kleinen Pfeil in der rechten unteren Ecke der Schaltfläche aufweist. Nachdem der Benutzer eine Schaltfläche aus der Dropdown-Symbolleiste ausgewählt hat, zeigt das Framework sein Symbol auf der Symbolleisten-Schaltfläche der obersten Ebene an (die Schaltfläche mit dem kleinen Pfeil in der unteren rechten Ecke).

Weitere Informationen zum Implementieren einer Dropdown-Symbolleiste finden Sie unter [cmfcdropdowntoolbar-Klasse](../../mfc/reference/cmfcdropdowntoolbar-class.md).

Das `CMFCDropDownToolBarButton` Objekt kann in ein [cmfctoolbarmenubutton-Klassen](../../mfc/reference/cmfctoolbarmenubutton-class.md) Objekt exportiert und als Menü Schaltfläche mit einem Popup Menü angezeigt werden.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[CMFCDropDownToolbarButton](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxdropdowntoolbar.h

##  <a name="copyfrom"></a>Cmfcdropdowntoolbarbutton:: CopyFrom

Kopiert die Eigenschaften einer anderen Symbolleisten Schaltfläche in die aktuelle Schaltfläche.

```
virtual void CopyFrom(const CMFCToolBarButton& src);
```

### <a name="parameters"></a>Parameter

*src*<br/>
in Ein Verweis auf die Quell Schaltfläche, von der kopiert werden soll.

### <a name="remarks"></a>Hinweise

Mit dieser Methode können Sie eine weitere Symbolleisten Schaltfläche auf diese Symbolleisten Schaltfläche *src* muss den Typ `CMFCDropDownToolbarButton`aufweisen.

##  <a name="cmfcdropdowntoolbarbutton"></a>Cmfcdropdowntoolbarbutton:: cmfcdropdowntoolbarbutton

Erstellt ein `CMFCDropDownToolbarButton`-Objekt.

```
CMFCDropDownToolbarButton();

CMFCDropDownToolbarButton(
    LPCTSTR lpszName,
    CMFCDropDownToolBar* pToolBar);
```

### <a name="parameters"></a>Parameter

*Wert*<br/>
in Der Standardtext der Schaltfläche.

*pToolBar*<br/>
in Ein Zeiger auf das `CMFCDropDownToolBar` -Objekt, das angezeigt wird, wenn der Benutzer die Schaltfläche drückt.

### <a name="remarks"></a>Hinweise

Die zweite Überladung des Konstruktors kopiert die erste Schaltfläche auf der Symbolleiste, die von *ptoolbar* angegeben wird, in die Dropdown Schaltfläche.

In der Regel verwendet eine Dropdown-Symbolleisten Schaltfläche den Text aus der zuletzt verwendeten Schaltfläche auf der Symbolleiste, die von *ptoolbar* angegeben wird. Der von *lpszname* angegebene Text wird verwendet, wenn die Schaltfläche in eine Menü Schaltfläche konvertiert wird oder auf der Registerkarte **Befehle** des Dialog Felds **Anpassen** angezeigt wird. Weitere Informationen zum Dialogfeld **Anpassen** finden Sie unter [cmfctoolbarscustomizedialog-Klasse](../../mfc/reference/cmfctoolbarscustomizedialog-class.md).

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie ein Objekt der `CMFCDropDownToolbarButton` -Klasse erstellt wird. Dieser Code Ausschnitt ist Teil des [Visual Studio-Demo](../../overview/visual-cpp-samples.md)Beispiels.

[!code-cpp[NVC_MFC_VisualStudioDemo#31](../../mfc/codesnippet/cpp/cmfcdropdowntoolbarbutton-class_1.cpp)]

##  <a name="dropdowntoolbar"></a>Cmfcdropdowntoolbarbutton::D ropdowntoolbar

Öffnet eine Dropdown-Symbolleiste.

```
BOOL DropDownToolbar(CWnd* pWnd);
```

### <a name="parameters"></a>Parameter

*pWnd*<br/>
in Das übergeordnete Fenster des Dropdown Rahmens oder NULL, wenn das übergeordnete Fenster der Dropdown-Symbolleisten Schaltfläche verwendet werden soll.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn die Methode erfolgreich ist. andernfalls 0.

### <a name="remarks"></a>Hinweise

Die [cmfcdropdowntoolbarbutton:: OnClick](#onclick) -Methode ruft diese Methode auf, um die Dropdown-Symbolleiste zu öffnen, wenn der Benutzer die Symbolleisten-Schaltfläche drückt und gedrückt hält.

Diese Methode erstellt die Dropdown-Symbolleiste mithilfe der [cmfcdropdownframe:: Create](../../mfc/reference/cmfcdropdownframe-class.md#create) -Methode. Wenn die übergeordnete Symbolleiste vertikal angedockt ist, positioniert diese Methode die Dropdown-Symbolleiste abhängig von der Eignung entweder auf der linken oder rechten Seite der übergeordneten Symbolleiste. Andernfalls positioniert diese Methode die Dropdown-Symbolleiste unterhalb der übergeordneten Symbolleiste.

Diese Methode schlägt fehl, wenn *pwnd* NULL ist und die Dropdown-Symbolleisten Schaltfläche kein übergeordnetes Fenster hat.

##  <a name="exporttomenubutton"></a>Cmfcdropdowntoolbarbutton:: exporttomeinubutton

Kopiert Text von der Symbolleisten-Schaltfläche in ein Menü.

```
virtual BOOL ExportToMenuButton(CMFCToolBarMenuButton& menuButton) const;
```

### <a name="parameters"></a>Parameter

*menuButton*<br/>
in Ein Verweis auf die Menü Schaltfläche für das Ziel.

### <a name="return-value"></a>Rückgabewert

Ein Wert ungleich 0 (null), wenn die Methode erfolgreich ausgeführt wird, andernfalls 0 (null).

### <a name="remarks"></a>Hinweise

Diese Methode ruft die Basisklassen Implementierung ( [cmfctoolbarbutton:: exporttomenubutton](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton)) auf und fügt dann an die Menü Schaltfläche des Ziels ein Popup Menü an, das jedes Symbolleisten-Menü Element in dieser Schaltfläche enthält. Diese Methode fügt keine Untermenüs an das Popup Menü an.

Diese Methode schlägt fehl, `m_pToolBar`wenn die übergeordnete Symbolleiste,, NULL ist oder die Basisklassen Implementierung false zurückgibt.

##  <a name="getdropdowntoolbar"></a>Cmfcdropdowntoolbarbutton:: getdropdowntoolbar

Ruft die Dropdown-Symbolleiste ab, die der Schaltfläche zugeordnet ist.

```
CMFCToolBar* GetDropDownToolBar() const;
```

### <a name="return-value"></a>Rückgabewert

Die Dropdown-Symbolleiste, die der Schaltfläche zugeordnet ist.

### <a name="remarks"></a>Hinweise

Diese Methode gibt den `m_pToolBar` Datenmember zurück.

##  <a name="isdropdown"></a>Cmfcdropdowntoolbarbutton:: IsDropDown

Bestimmt, ob die Dropdown-Symbolleiste aktuell geöffnet ist.

```
BOOL IsDropDown() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn die Dropdown-Symbolleiste momentan geöffnet ist. andernfalls 0.

### <a name="remarks"></a>Hinweise

Das Framework öffnet die Dropdown-Symbolleiste mithilfe der [cmfcdropdowntoolbarbutton::D ropdowntoolbar](#dropdowntoolbar) -Methode. Das Framework schließt die Dropdown-Symbolleiste, wenn der Benutzer die linke Maustaste im nicht-Client Bereich der Dropdown-Symbolleiste drückt.

##  <a name="isextrasize"></a>Cmfcdropdowntoolbarbutton:: isextrasize

Bestimmt, ob die Schaltfläche mit einem erweiterten Rahmen angezeigt werden kann.

```
virtual BOOL IsExtraSize() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Symbolleisten-Schaltfläche mit einem erweiterten Rahmen angezeigt werden kann. andernfalls 0.

### <a name="remarks"></a>Hinweise

Weitere Informationen zu erweiterten Rahmen finden Sie unter [cmfctoolbarbutton:: isextrasize](../../mfc/reference/cmfctoolbarbutton-class.md#isextrasize).

##  <a name="m_uishowbardelay"></a>Cmfcdropdowntoolbarbutton:: m_uiShowBarDelay

Gibt die Zeitspanne an, in der ein Benutzer die Maustaste gedrückt halten muss, bevor die Dropdown-Symbolleiste angezeigt wird.

```
static UINT m_uiShowBarDelay;
```

### <a name="remarks"></a>Hinweise

Die Verzögerungszeit wird in Millisekunden gemessen. Der Standardwert ist 500. Sie können eine weitere Verzögerung festlegen, indem Sie den Wert dieses freigegebenen Datenmembers ändern.

##  <a name="oncalculatesize"></a>Cmfcdropdowntoolbarbutton:: oncalculatesize

Wird von Framework aufgerufen, um die Größe der Schaltfläche für den angegebenen Gerätekontext und den Andock Zustand zu berechnen.

```
virtual SIZE OnCalculateSize(
    CDC* pDC,
    const CSize& sizeDefault,
    BOOL bHorz);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
in Der Gerätekontext, der die Schaltfläche anzeigt.

*sizeDefault*<br/>
in Die Standardgröße der Schaltfläche.

*bHorz*<br/>
in Der Andock Zustand der übergeordneten Symbolleiste. Dieser Parameter ist true, wenn die Symbolleiste horizontal angedockt oder unverankert ist, oder false, wenn die Symbolleiste vertikal angedockt ist.

### <a name="return-value"></a>Rückgabewert

Eine `SIZE` -Struktur, die die Abmessungen der Schaltfläche in Pixel enthält.

### <a name="remarks"></a>Hinweise

Diese Methode erweitert die Basisklassen Implementierung ( [cmfctoolbarbutton:: oncalculatesize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize)), indem die Breite des Dropdown Pfeils der horizontalen Dimension der Schaltflächen Größe hinzugefügt wird.

##  <a name="onchangeparentwnd"></a>Cmfcdropdowntoolbarbutton:: onchangepartwnd

Wird von Framework aufgerufen, wenn die Schaltfläche in eine neue Symbolleiste eingefügt wird.

```
virtual void OnChangeParentWnd(CWnd* pWndParent);
```

### <a name="parameters"></a>Parameter

*pWndParent*<br/>
in Das neue übergeordnete Fenster.

### <a name="remarks"></a>Hinweise

Diese Methode überschreibt die Basisklassen Implementierung ( [cmfctoolbarbutton:: onchangebientwnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd)), indem die Text Bezeichnung ( [cmfctoolbarbutton:: m_strText](../../mfc/reference/cmfctoolbarbutton-class.md#m_strtext)) gelöscht und [cmfctoolbarbutton:: m_bText](../../mfc/reference/cmfctoolbarbutton-class.md#m_btext) und [cmfctoolbarbutton festgelegt wird. :: m_bUserButton](../../mfc/reference/cmfctoolbarbutton-class.md#m_buserbutton) Data Members in false.

##  <a name="onclick"></a>Cmfcdropdowntoolbarbutton:: OnClick

Wird von Framework aufgerufen, wenn der Benutzer auf die Maustaste klickt.

```
virtual BOOL OnClick(
    CWnd* pWnd,
    BOOL bDelay = TRUE);
```

### <a name="parameters"></a>Parameter

*pWnd*<br/>
in Das übergeordnete Fenster der Symbolleisten Schaltfläche.

*bDelay*<br/>
in TRUE, wenn die Meldung mit einer Verzögerung behandelt werden soll.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn die Schaltfläche die Klick Nachricht verarbeitet. andernfalls 0.

### <a name="remarks"></a>Hinweise

Diese Methode erweitert die Basisklassen Implementierung [cmfctoolbarbutton:: OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick)durch Aktualisieren des Status der Dropdown-Symbolleiste.

Wenn ein Benutzer auf die Symbolleisten Schaltfläche klickt, erstellt diese Methode einen Timer, der die vom [cmfcdropdowntoolbarbutton:: m_uiShowBarDelay](#m_uishowbardelay) -Datenmember angegebene Zeitspanne wartet und dann mithilfe von cmfcdropdowntoolbarbutton die Dropdown-Symbolleiste öffnet. [ ::D ropdowntoolbar](#dropdowntoolbar) -Methode. Diese Methode schließt die Dropdown-Symbolleiste, wenn der Benutzer das zweite Mal auf die Symbolleisten Schaltfläche klickt.

##  <a name="onclickup"></a>Cmfcdropdowntoolbarbutton:: onclickup

Wird von Framework aufgerufen, wenn der Benutzer die Maustaste loslässt.

```
virtual BOOL OnClickUp();
```

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn die Schaltfläche die Klick Nachricht verarbeitet. andernfalls 0.

### <a name="remarks"></a>Hinweise

Diese Methode erweitert die Basisklassen Implementierung [cmfctoolbarbutton:: onclickup](../../mfc/reference/cmfctoolbarbutton-class.md#onclickup)durch Aktualisieren des Status der Dropdown-Symbolleiste.

Diese Methode beendet den Dropdown-Symbolleisten-Timer, wenn er aktiv ist. Wenn die Dropdown Leiste geöffnet ist, wird Sie geschlossen.

Weitere Informationen zur Dropdown-Symbolleiste und zum Dropdown-Symbolleisten-Timer finden Sie unter [cmfcdropdowntoolbarbutton:: OnClick](#onclick).

##  <a name="oncontexthelp"></a>Cmfcdropdowntoolbarbutton:: oncontexthelp

Wird von Framework aufgerufen, wenn die übergeordnete Symbolleiste eine WM_HELPHITTEST-Meldung behandelt.

```
virtual BOOL OnContextHelp(CWnd* pWnd);
```

### <a name="parameters"></a>Parameter

*pWnd*<br/>
in Das übergeordnete Fenster der Symbolleisten Schaltfläche.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn die Schaltfläche die Hilfe Nachricht verarbeitet. andernfalls 0.

### <a name="remarks"></a>Hinweise

Diese Methode erweitert die Basisklassen Implementierung ( [cmfctoolbarbutton:: oncontexthelp](../../mfc/reference/cmfctoolbarbutton-class.md#oncontexthelp)) durch Aufrufen der [cmfcdropdowntoolbarbutton:: OnClick](#onclick) -Methode, wobei *bdelay* auf false festgelegt ist. Diese Methode gibt den Wert zurück, der von [cmfcdropdowntoolbarbutton:: OnClick](#onclick)zurückgegeben wird.

Weitere Informationen zur WM_HELPHITTEST-Nachricht finden [Sie unter TN028: Unterstützung](../../mfc/tn028-context-sensitive-help-support.md)von kontextbezogenen Hilfe.

##  <a name="oncustomizemenu"></a>Cmfcdropdowntoolbarbutton:: oncustomizemdeu

Ändert das bereitgestellte Menü, wenn die Anwendung ein Kontextmenü auf der übergeordneten Symbolleiste anzeigt.

```
virtual BOOL OnCustomizeMenu(CMenu* pMenu);
```

### <a name="parameters"></a>Parameter

*pMenu*<br/>
in Das Menü, das angepasst werden soll.

### <a name="return-value"></a>Rückgabewert

Diese Methode gibt "true" zurück.

### <a name="remarks"></a>Hinweise

Diese Methode erweitert die Basisklassen Implementierung ( [cmfctoolbarbutton:: oncustomizemenu](../../mfc/reference/cmfctoolbarbutton-class.md#oncustomizemenu)) durch Deaktivieren der folgenden Menü Elemente:

- **Schaltflächen Bild kopieren**

- **Darstellung der Schaltfläche**

- **Image**

- **Text**

- **Bild und Text**

Überschreiben Sie diese Methode, um das Kontextmenü zu ändern, das vom Framework im Anpassungsmodus angezeigt wird.

##  <a name="ondraw"></a>Cmfcdropdowntoolbarbutton:: OnDraw

Wird von Framework aufgerufen, um die Schaltfläche mithilfe der angegebenen Stile und Optionen zu zeichnen.

```
virtual void OnDraw(
    CDC* pDC,
    const CRect& rect,
    CMFCToolBarImages* pImages,
    BOOL bHorz = TRUE,
    BOOL bCustomizeMode = FALSE,
    BOOL bHighlight = FALSE,
    BOOL bDrawBorder = TRUE,
    BOOL bGrayDisabledButtons = TRUE);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
in Der Gerätekontext, der die Schaltfläche anzeigt.

*Rect*<br/>
in Das umgebende Rechteck der Schaltfläche.

*pimages*<br/>
in Die Auflistung von Symbolleisten Bildern, die der Schaltfläche zugeordnet ist.

*bHorz*<br/>
in Der Andock Zustand der übergeordneten Symbolleiste. Dieser Parameter ist true, wenn die Schaltfläche horizontal angedockt ist, und false, wenn die Schaltfläche vertikal angedockt ist.

*bcustomizemode*<br/>
in Gibt an, ob sich die Symbolleiste im Anpassungsmodus befindet. Dieser Parameter ist true, wenn sich die Symbolleiste im Anpassungsmodus befindet, und false, wenn sich die Symbolleiste nicht im Anpassungsmodus befindet.

*bHighlight*<br/>
in Gibt an, ob die Schaltfläche hervorgehoben ist. Dieser Parameter ist true, wenn die Schaltfläche markiert ist, und false, wenn die Schaltfläche nicht hervorgehoben ist.

*bDrawBorder*<br/>
in Gibt an, ob der Rahmen der Schaltfläche angezeigt werden soll. Dieser Parameter ist true, wenn die Schaltfläche den Rahmen und den Wert false anzeigen soll, wenn die Schaltfläche den Rahmen nicht anzeigen soll.

*bGrayDisabledButtons*<br/>
in Gibt an, ob deaktivierte Schaltflächen oder die deaktivierte Bilder Auflistung verwendet werden sollen Dieser Parameter ist true, wenn deaktivierte Schaltflächen schattiert werden sollen, und false, wenn diese Methode die deaktivierte Bilder Auflistung verwenden soll

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode, um die Symbolleisten-Schaltfläche zu

##  <a name="ondrawoncustomizelist"></a>Cmfcdropdowntoolbarbutton:: ondrawoncustomizelist

Wird von Framework aufgerufen, um die Schaltfläche im **Befehls** Bereich des Dialog Felds **Anpassen** zu zeichnen.

```
virtual int OnDrawOnCustomizeList(
    CDC* pDC,
    const CRect& rect,
    BOOL bSelected);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
in Der Gerätekontext, der die Schaltfläche anzeigt.

*Rect*<br/>
in Das umgebende Rechteck der Schaltfläche.

*bausgewählt*<br/>
in Gibt an, ob die Schaltfläche ausgewählt ist. Wenn dieser Parameter true ist, wird die Schaltfläche ausgewählt. Wenn dieser Parameter false ist, wird die Schaltfläche nicht ausgewählt.

### <a name="return-value"></a>Rückgabewert

Die Breite der Schaltfläche im angegebenen Gerätekontext in Pixel.

### <a name="remarks"></a>Hinweise

Diese Methode wird im Dialogfeld Anpassung (Registerkarte **Befehle** ) aufgerufen, wenn die Schaltfläche für die Anzeige im Listenfeld Besitzer gezeichnet werden muss.

Diese Methode erweitert die Basisklassen Implementierung ( [cmfctoolbarbutton:: ondrawoncustomizelist](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist)), indem die Text Bezeichnung der Schaltfläche auf den Namen der Schaltfläche (d. h. auf den Wert des *lpszname* -Parameters, den Sie an den Konstruktor übergeben haben) geändert wird. ).

##  <a name="serialize"></a>Cmfcdropdowntoolbarbutton:: Serialize

Liest dieses Objekt aus einem Archiv oder schreibt es in ein Archiv.

```
virtual void Serialize(CArchive& ar);
```

### <a name="parameters"></a>Parameter

*ar*<br/>
in Das `CArchive` -Objekt, aus dem bzw. in das serialisiert werden soll.

### <a name="remarks"></a>Hinweise

Diese Methode erweitert die Basisklassen Implementierung ( [cmfctoolbarbutton:: Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize)) durch Serialisieren der Ressourcen-ID der übergeordneten Symbolleiste. Wenn das Archiv geladen wird ( [CArchive:: isload](../../mfc/reference/carchive-class.md#isloading) gibt einen Wert ungleich 0 (null) zurück), `m_pToolBar` legt diese Methode den Datenmember auf die Symbolleiste fest, die die serialisierte Ressourcen-ID enthält.

##  <a name="setdefaultcommand"></a>Cmfcdropdowntoolbarbutton:: setdefaultcommand

Legt den Standardbefehl fest, den das Framework verwendet, wenn ein Benutzer auf die Schaltfläche klickt.

```
void SetDefaultCommand(UINT uiCmd);
```

### <a name="parameters"></a>Parameter

*uiCmd*<br/>
in Die ID des Standard Befehls.

### <a name="remarks"></a>Hinweise

Aufrufen Sie diese Methode, um einen Standardbefehl anzugeben, den das Framework ausführt, wenn der Benutzer auf die Schaltfläche klickt. Ein Element mit der von *uicmd* angegebenen Befehls-ID muss sich auf der übergeordneten Dropdown-Symbolleiste befinden.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCDropDownToolBar-Klasse](../../mfc/reference/cmfcdropdowntoolbar-class.md)<br/>
[CMFCToolBar-Klasse](../../mfc/reference/cmfctoolbar-class.md)<br/>
[CMFCToolBarMenuButton-Klasse](../../mfc/reference/cmfctoolbarmenubutton-class.md)<br/>
[Exemplarische Vorgehensweise: Einfügen von Steuerelementen in eine Symbolleiste](../../mfc/walkthrough-putting-controls-on-toolbars.md)

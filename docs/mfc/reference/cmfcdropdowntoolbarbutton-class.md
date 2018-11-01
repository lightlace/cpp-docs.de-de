---
title: CMFCDropDownToolbarButton-Klasse
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
ms.openlocfilehash: 3544bbd65b5e0c754552f93b45263f768b73fe69
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50625315"
---
# <a name="cmfcdropdowntoolbarbutton-class"></a>CMFCDropDownToolbarButton-Klasse

Ein Symbolleisten-Schaltflächentyp, der sich wie eine normale Schaltfläche verhält, wenn darauf geklickt wird. Allerdings eine Dropdown Symbolleiste öffnen ( [CMFCDropDownToolBar-Klasse](../../mfc/reference/cmfcdropdowntoolbar-class.md) , wenn der Benutzer drückt und die Symbolleisten-Schaltfläche gedrückt hält.

## <a name="syntax"></a>Syntax

```
class CMFCDropDownToolbarButton : public CMFCToolBarButton
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CMFCDropDownToolbarButton::CMFCDropDownToolbarButton](#cmfcdropdowntoolbarbutton)|Erstellt ein `CMFCDropDownToolbarButton`-Objekt.|
|`CMFCDropDownToolbarButton::~CMFCDropDownToolbarButton`|Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCDropDownToolbarButton::CopyFrom](#copyfrom)|Kopiert die Eigenschaften von einer anderen Symbolleistenschaltfläche, auf die Schaltfläche "aktuelle". (Überschreibt [CMFCToolBarButton::CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom).)|
|`CMFCDropDownToolbarButton::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|
|[CMFCDropDownToolbarButton::DropDownToolbar](#dropdowntoolbar)|Öffnet eine Dropdown Symbolleiste.|
|[CMFCDropDownToolbarButton::ExportToMenuButton](#exporttomenubutton)|Kopiert den Text aus der Symbolleisten-Schaltfläche zu einem Menü. (Überschreibt [CMFCToolBarButton::ExportToMenuButton](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton).)|
|[CMFCDropDownToolbarButton::GetDropDownToolBar](#getdropdowntoolbar)|Ruft ab, der Dropdown-Symbolleisten, die mit der Schaltfläche zugeordnet ist.|
|`CMFCDropDownToolbarButton::GetThisClass`|Durch das Framework verwendet wird, einen Zeiger zum Abrufen der [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das diesem Klassentyp zugeordnet ist.|
|[CMFCDropDownToolbarButton::IsDropDown](#isdropdown)|Bestimmt, ob der Dropdown-Symbolleisten derzeit geöffnet ist.|
|[CMFCDropDownToolbarButton::IsExtraSize](#isextrasize)|Bestimmt, ob die Schaltfläche mit einem erweiterten Rahmen angezeigt werden kann. (Überschreibt [CMFCToolBarButton::IsExtraSize](../../mfc/reference/cmfctoolbarbutton-class.md#isextrasize).)|
|[CMFCDropDownToolbarButton::OnCalculateSize](#oncalculatesize)|Wird aufgerufen, durch das Framework die Größe der Schaltfläche für den angegebenen Gerätekontext und Andockstatus berechnet. (Überschreibt [CMFCToolBarButton::OnCalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize).)|
|`CMFCDropDownToolbarButton::OnCancelMode`|Wird aufgerufen, durch das Framework, behandeln die [WM_CANCELMODE](/windows/desktop/winmsg/wm-cancelmode) Nachricht. (Überschreibt `CMCToolBarButton::OnCancelMode`.)|
|[CMFCDropDownToolbarButton::OnChangeParentWnd](#onchangeparentwnd)|Vom Framework aufgerufen, wenn die Schaltfläche mit der in eine neue Symbolleiste eingefügt wird. (Überschreibt [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd).)|
|[CMFCDropDownToolbarButton::OnClick](#onclick)|Vom Framework aufgerufen, wenn der Benutzer die Maustaste klickt. (Überschreibt [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick).)|
|[CMFCDropDownToolbarButton::OnClickUp](#onclickup)|Vom Framework aufgerufen, wenn der Benutzer die Maustaste loslässt. (Überschreibt [CMFCToolBarButton::OnClickUp](../../mfc/reference/cmfctoolbarbutton-class.md#onclickup).)|
|[CMFCDropDownToolbarButton::OnContextHelp](#oncontexthelp)|Vom Framework aufgerufen, wenn die übergeordneten Symbolleiste eine WM_HELPHITTEST-Meldung verarbeitet. (Überschreibt [CMFCToolBarButton::OnContextHelp](../../mfc/reference/cmfctoolbarbutton-class.md#oncontexthelp).)|
|[CMFCDropDownToolbarButton::OnCustomizeMenu](#oncustomizemenu)|Ändert das angegebene Menü an, wenn die Anwendung auf der Symbolleiste des übergeordneten wird ein Kontextmenü angezeigt. (Überschreibt [CMFCToolBarButton::OnCustomizeMenu](../../mfc/reference/cmfctoolbarbutton-class.md#oncustomizemenu).)|
|[CMFCDropDownToolbarButton::OnDraw](#ondraw)|Wird aufgerufen, durch das Framework zum Zeichnen der Schaltfläche mit der angegebenen Formate und -Optionen. (Überschreibt [CMFCToolBarButton::OnDraw](../../mfc/reference/cmfctoolbarbutton-class.md#ondraw).)|
|[CMFCDropDownToolbarButton::OnDrawOnCustomizeList](#ondrawoncustomizelist)|Wird aufgerufen, durch das Framework zum Zeichnen der Schaltfläche der **Befehle** im Bereich der **anpassen** im Dialogfeld. (Überschreibt [CMFCToolBarButton::OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist).)|
|[CMFCDropDownToolbarButton::Serialize](#serialize)|Dieses Objekt aus einem Archiv liest oder schreibt dieses in ein Archiv. (Überschreibt [CMFCToolBarButton::Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize).)|
|[CMFCDropDownToolbarButton::SetDefaultCommand](#setdefaultcommand)|Legt fest, den Standardbefehl, den das Framework verwendet, wenn ein Benutzer die Schaltfläche klickt.|

### <a name="data-members"></a>Datenmember

|name|Beschreibung|
|----------|-----------------|
|[CMFCDropDownToolbarButton::m_uiShowBarDelay](#m_uishowbardelay)|Gibt die Länge der Zeit, die ein Benutzer die Maustaste gedrückt halten muss, bevor die Dropdown-Symbolleiste angezeigt.|

## <a name="remarks"></a>Hinweise

Ein `CMFCDropDownToolBarButton` eine normale Schaltfläche besteht darin, dass es einen kleinen Pfeil in der unteren rechten Ecke der Schaltfläche hat. Nachdem der Benutzer aus der Dropdown-Symbolleiste eine Schaltfläche auswählt, zeigt das Framework das entsprechende Symbol auf der obersten Ebene Symbolleisten-Schaltfläche (die Schaltfläche mit den kleinen Pfeil in der unteren rechten Ecke).

Informationen dazu, wie Sie eine Dropdown Symbolleiste implementieren, finden Sie unter [CMFCDropDownToolBar-Klasse](../../mfc/reference/cmfcdropdowntoolbar-class.md).

Die `CMFCDropDownToolBarButton` Objekt kann exportiert werden, um eine [CMFCToolBarMenuButton-Klasse](../../mfc/reference/cmfctoolbarmenubutton-class.md) Objekt aus, und eine Schaltfläche mit einem Popup-Menü angezeigt.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[CMFCDropDownToolbarButton](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxdropdowntoolbar.h

##  <a name="copyfrom"></a>  CMFCDropDownToolbarButton::CopyFrom

Kopiert die Eigenschaften von einer anderen Symbolleistenschaltfläche, auf die Schaltfläche "aktuelle".

```
virtual void CopyFrom(const CMFCToolBarButton& src);
```

### <a name="parameters"></a>Parameter

*src*<br/>
[in] Ein Verweis auf die Schaltfläche "Quelle", aus dem kopiert werden sollen.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Methode zum Kopieren von einer anderen Symbolleistenschaltfläche diese Symbolleisten-Schaltfläche auf. *Src* muss vom Typ `CMFCDropDownToolbarButton`.

##  <a name="cmfcdropdowntoolbarbutton"></a>  CMFCDropDownToolbarButton::CMFCDropDownToolbarButton

Erstellt ein `CMFCDropDownToolbarButton`-Objekt.

```
CMFCDropDownToolbarButton();

CMFCDropDownToolbarButton(
    LPCTSTR lpszName,
    CMFCDropDownToolBar* pToolBar);
```

### <a name="parameters"></a>Parameter

*Wert*<br/>
[in] Der Standardtext der Schaltfläche.

*pToolBar*<br/>
[in] Ein Zeiger auf die `CMFCDropDownToolBar` -Objekt, das angezeigt wird, wenn der Benutzer die Schaltfläche klickt.

### <a name="remarks"></a>Hinweise

Die zweite Überladung des Konstruktors kopiert der Dropdown-Schaltfläche für die erste Schaltfläche auf der Symbolleiste, *pToolBar* angibt.

In der Regel verwendet eine Dropdown-Symbolleisten-Schaltfläche den Text von der zuletzt verwendeten Schaltfläche auf der Symbolleiste, *pToolBar* angibt. Er verwendet den angegebenen Text *Wert* Wenn die Schaltfläche mit der in einer Menüschaltfläche konvertiert wird, oder wird angezeigt, der **Befehle** Registerkarte die **anpassen** Dialogfeld. Weitere Informationen zu den **anpassen** im Dialogfeld finden Sie unter [CMFCToolBarsCustomizeDialog-Klasse](../../mfc/reference/cmfctoolbarscustomizedialog-class.md).

### <a name="example"></a>Beispiel

Im folgende Beispiel wird veranschaulicht, wie zum Erstellen eines Objekts von der `CMFCDropDownToolbarButton` Klasse. Dieser Codeausschnitt ist Teil der [Visual Studio-Demobeispiel](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_VisualStudioDemo#31](../../mfc/codesnippet/cpp/cmfcdropdowntoolbarbutton-class_1.cpp)]

##  <a name="dropdowntoolbar"></a>  CMFCDropDownToolbarButton::DropDownToolbar

Öffnet eine Dropdown Symbolleiste.

```
BOOL DropDownToolbar(CWnd* pWnd);
```

### <a name="parameters"></a>Parameter

*Aufnehmen*<br/>
[in] Das übergeordnete Fenster des Dropdown-Rahmens oder NULL, um das übergeordnete Fenster der Dropdown-Symbolleisten-Schaltfläche zu verwenden.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Methode erfolgreich ist; andernfalls 0.

### <a name="remarks"></a>Hinweise

Die [CMFCDropDownToolbarButton::OnClick](#onclick) Methode ruft diese Methode, um die Dropdown-Symbolleisten geöffnet werden, wenn der Benutzer drückt und die Symbolleisten-Schaltfläche gedrückt hält.

Dieser Methode erstellt die Dropdown-Symbolleisten mithilfe der [CMFCDropDownFrame::Create](../../mfc/reference/cmfcdropdownframe-class.md#create) Methode. Wenn die übergeordneten Symbolleiste vertikal angedockt ist, positioniert diese Methode der Dropdown-Symbolleiste entweder auf der linken oder rechten Seite der übergeordneten Symbolleiste, je nach der Anpassung. Diese Methode wird, andernfalls die Dropdown-Symbolleiste unterhalb der übergeordneten Symbolleiste positioniert.

Diese Methode schlägt fehl, wenn *aufnehmen* NULL ist und die Dropdown-Symbolleisten-Schaltfläche verfügt nicht über ein übergeordnetes Fenster.

##  <a name="exporttomenubutton"></a>  CMFCDropDownToolbarButton::ExportToMenuButton

Kopiert den Text aus der Symbolleisten-Schaltfläche zu einem Menü.

```
virtual BOOL ExportToMenuButton(CMFCToolBarMenuButton& menuButton) const;
```

### <a name="parameters"></a>Parameter

*MenuButton*<br/>
[in] Ein Verweis auf die Menüschaltfläche Ziel.

### <a name="return-value"></a>Rückgabewert

Ein Wert ungleich 0 (null), wenn die Methode erfolgreich ausgeführt wird, andernfalls 0 (null).

### <a name="remarks"></a>Hinweise

Diese Methode ruft die basisklassenimplementierung ( [CMFCToolBarButton::ExportToMenuButton](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton)) und fügt dann an die Ziel-Menüschaltfläche ein Popup-Menü, das jede Symbolleisten-Menüelement auf diese Schaltfläche enthält. Diese Methode fügt keinen untergeordneten Menüs zu dem Popup-Menü.

Diese Methode schlägt fehl, wenn der übergeordneten Symbolleiste `m_pToolBar`, NULL ist, oder die basisklassenimplementierung gibt FALSE zurück.

##  <a name="getdropdowntoolbar"></a>  CMFCDropDownToolbarButton::GetDropDownToolBar

Ruft ab, der Dropdown-Symbolleisten, die mit der Schaltfläche zugeordnet ist.

```
CMFCToolBar* GetDropDownToolBar() const;
```

### <a name="return-value"></a>Rückgabewert

Die Dropdown-Symbolleisten, die mit der Schaltfläche zugeordnet ist.

### <a name="remarks"></a>Hinweise

Diese Methode gibt die `m_pToolBar` -Datenmember.

##  <a name="isdropdown"></a>  CMFCDropDownToolbarButton::IsDropDown

Bestimmt, ob der Dropdown-Symbolleisten derzeit geöffnet ist.

```
BOOL IsDropDown() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn der Dropdown-Symbolleisten derzeit geöffnet ist; andernfalls 0.

### <a name="remarks"></a>Hinweise

Das Framework öffnet die Dropdown-Symbolleisten mithilfe der [CMFCDropDownToolbarButton::DropDownToolbar](#dropdowntoolbar) Methode. Das Framework schließt die Dropdown-Symbolleisten auf, wenn der Benutzer die linke Maustaste in den nicht-Clientbereich der Dropdown-Symbolleiste drückt.

##  <a name="isextrasize"></a>  CMFCDropDownToolbarButton::IsExtraSize

Bestimmt, ob die Schaltfläche mit einem erweiterten Rahmen angezeigt werden kann.

```
virtual BOOL IsExtraSize() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Symbolleisten-Schaltfläche mit einem erweiterten Rahmen angezeigt werden kann; andernfalls 0.

### <a name="remarks"></a>Hinweise

Weitere Informationen zu erweiterten Rahmen, finden Sie unter [CMFCToolBarButton::IsExtraSize](../../mfc/reference/cmfctoolbarbutton-class.md#isextrasize).

##  <a name="m_uishowbardelay"></a>  CMFCDropDownToolbarButton::m_uiShowBarDelay

Gibt die Länge der Zeit, die ein Benutzer die Maustaste gedrückt halten muss, bevor die Dropdown-Symbolleiste angezeigt.

```
static UINT m_uiShowBarDelay;
```

### <a name="remarks"></a>Hinweise

Die Verzögerungszeit wird in Millisekunden gemessen. Der Standardwert ist 500. Sie können einen anderen Verzögerung festlegen, durch Ändern des Werts des freigegebenen Elements.

##  <a name="oncalculatesize"></a>  CMFCDropDownToolbarButton::OnCalculateSize

Wird aufgerufen, durch das Framework die Größe der Schaltfläche für den angegebenen Gerätekontext und Andockstatus berechnet.

```
virtual SIZE OnCalculateSize(
    CDC* pDC,
    const CSize& sizeDefault,
    BOOL bHorz);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
[in] Der Gerätekontext, in dem die Schaltfläche angezeigt.

*sizeDefault*<br/>
[in] Die Standardgröße der Schaltfläche.

*bHorz*<br/>
[in] Der Status der Andocken der übergeordneten Symbolleiste. Dieser Parameter ist "true", wenn die Symbolleiste horizontal angedockt oder unverankert ist, oder "false", wenn die Symbolleiste vertikal angedockt ist.

### <a name="return-value"></a>Rückgabewert

Ein `SIZE` Struktur, die die Abmessungen der Schaltfläche in Pixel enthält.

### <a name="remarks"></a>Hinweise

Diese Methode erweitert die basisklassenimplementierung ( [CMFCToolBarButton::OnCalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize)) durch die Breite der Dropdown-Pfeil auf die horizontale Dimension der Größe der Schaltfläche hinzufügen.

##  <a name="onchangeparentwnd"></a>  CMFCDropDownToolbarButton::OnChangeParentWnd

Vom Framework aufgerufen, wenn die Schaltfläche mit der in eine neue Symbolleiste eingefügt wird.

```
virtual void OnChangeParentWnd(CWnd* pWndParent);
```

### <a name="parameters"></a>Parameter

*pWndParent*<br/>
[in] Das neue übergeordnete Fenster.

### <a name="remarks"></a>Hinweise

Diese Methode überschreibt die basisklassenimplementierung ( [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd)) durch das Löschen der Bezeichnung ( [CMFCToolBarButton::m_strText](../../mfc/reference/cmfctoolbarbutton-class.md#m_strtext)) und die Einstellung der [ CMFCToolBarButton::m_bText](../../mfc/reference/cmfctoolbarbutton-class.md#m_btext) und [CMFCToolBarButton::m_bUserButton](../../mfc/reference/cmfctoolbarbutton-class.md#m_buserbutton) Datenmember auf "false".

##  <a name="onclick"></a>  CMFCDropDownToolbarButton::OnClick

Vom Framework aufgerufen, wenn der Benutzer die Maustaste klickt.

```
virtual BOOL OnClick(
    CWnd* pWnd,
    BOOL bDelay = TRUE);
```

### <a name="parameters"></a>Parameter

*Aufnehmen*<br/>
[in] Das übergeordnete Fenster der Symbolleisten-Schaltfläche.

*bDelay*<br/>
[in] TRUE, wenn die Nachricht mit einer Verzögerung behandelt werden soll.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn die Schaltfläche, die auf-Nachricht verarbeitet; andernfalls 0.

### <a name="remarks"></a>Hinweise

Diese Methode erweitert die basisklassenimplementierung [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick), durch das Aktualisieren des Status der Dropdown-Symbolleiste.

Wenn ein Benutzer die Symbolleisten-Schaltfläche klickt, wird diese Methode erstellt einen Timer, der die Länge des angegebenen Zeitintervalls wartet der [CMFCDropDownToolbarButton::m_uiShowBarDelay](#m_uishowbardelay) -Datenmember aus und klicken Sie dann öffnet der Dropdown-Symbolleiste mithilfe der [CMFCDropDownToolbarButton::DropDownToolbar](#dropdowntoolbar) Methode. Diese Methode schließt die Dropdown-Symbolleisten zweiten Mal, das der Benutzer die Symbolleisten-Schaltfläche klickt.

##  <a name="onclickup"></a>  CMFCDropDownToolbarButton::OnClickUp

Vom Framework aufgerufen, wenn der Benutzer die Maustaste loslässt.

```
virtual BOOL OnClickUp();
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn die Schaltfläche, die auf-Nachricht verarbeitet; andernfalls 0.

### <a name="remarks"></a>Hinweise

Diese Methode erweitert die basisklassenimplementierung [CMFCToolBarButton::OnClickUp](../../mfc/reference/cmfctoolbarbutton-class.md#onclickup), durch das Aktualisieren des Status der Dropdown-Symbolleiste.

Diese Methode beendet den Dropdown-Symbolleisten-Timer, wenn er aktiv ist. Es schließt die Dropdown-Symbolleisten, falls er geöffnet ist.

Weitere Informationen zu den Dropdown-Symbolleisten und Dropdown-Symbolleisten-Timer, finden Sie unter [CMFCDropDownToolbarButton::OnClick](#onclick).

##  <a name="oncontexthelp"></a>  CMFCDropDownToolbarButton::OnContextHelp

Vom Framework aufgerufen, wenn die übergeordneten Symbolleiste eine WM_HELPHITTEST-Meldung verarbeitet.

```
virtual BOOL OnContextHelp(CWnd* pWnd);
```

### <a name="parameters"></a>Parameter

*Aufnehmen*<br/>
[in] Das übergeordnete Fenster der Symbolleisten-Schaltfläche.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn die Schaltfläche mit der auf die Hilfe-Nachricht verarbeitet; andernfalls 0.

### <a name="remarks"></a>Hinweise

Diese Methode erweitert die basisklassenimplementierung ( [CMFCToolBarButton::OnContextHelp](../../mfc/reference/cmfctoolbarbutton-class.md#oncontexthelp)) durch Aufrufen der [CMFCDropDownToolbarButton::OnClick](#onclick) -Methode mit *bDelay*auf "false" festgelegt. Diese Methode gibt zurück, den Wert, der von zurückgegebene [CMFCDropDownToolbarButton::OnClick](#onclick).

Weitere Informationen zur Meldung WM_HELPHITTEST finden Sie unter [TN028: kontextbezogene Hilfe Support](../../mfc/tn028-context-sensitive-help-support.md).

##  <a name="oncustomizemenu"></a>  CMFCDropDownToolbarButton::OnCustomizeMenu

Ändert das angegebene Menü an, wenn die Anwendung auf der Symbolleiste des übergeordneten wird ein Kontextmenü angezeigt.

```
virtual BOOL OnCustomizeMenu(CMenu* pMenu);
```

### <a name="parameters"></a>Parameter

*pMenu*<br/>
[in] Klicken Sie im Menü anpassen.

### <a name="return-value"></a>Rückgabewert

Diese Methode gibt "true" zurück.

### <a name="remarks"></a>Hinweise

Diese Methode erweitert die basisklassenimplementierung ( [CMFCToolBarButton::OnCustomizeMenu](../../mfc/reference/cmfctoolbarbutton-class.md#oncustomizemenu)) deaktivieren Sie die folgenden Punkte:

- **Bild der Schaltfläche Kopieren**

- **Darstellung der Schaltfläche**

- **Image**

- **Text**

- **Bild und Text**

Überschreiben Sie diese Methode, um das Kontextmenü zu ändern, das das Framework im Anpassungsmodus anzeigt.

##  <a name="ondraw"></a>  CMFCDropDownToolbarButton::OnDraw

Wird aufgerufen, durch das Framework zum Zeichnen der Schaltfläche mit der angegebenen Formate und -Optionen.

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
[in] Der Gerätekontext, in dem die Schaltfläche angezeigt.

*Rect*<br/>
[in] Das umschließende Rechteck der Schaltfläche.

*pImages*<br/>
[in] Die Auflistung der Symbolleistenbilder, die mit der Schaltfläche zugeordnet ist.

*bHorz*<br/>
[in] Der Status der Andocken der übergeordneten Symbolleiste. Dieser Parameter ist "true", wenn die Schaltfläche horizontal und "false" angedockt ist, wenn die Schaltfläche vertikal angedockt ist.

*bCustomizeMode*<br/>
[in] Gibt an, ob die Symbolleiste im Anpassungsmodus befindet. Dieser Parameter ist "true", wenn die Symbolleiste im Anpassungsmodus und "false" ist, wenn die Symbolleiste nicht im Anpassungsmodus wird.

*bHighlight*<br/>
[in] Gibt an, ob die Schaltfläche markiert wird. Dieser Parameter ist, wenn die Schaltfläche markiert wird "Wahr" und "false", wenn die Schaltfläche nicht hervorgehoben ist.

*bDrawBorder*<br/>
[in] Gibt an, ob den Rahmen der Schaltfläche angezeigt werden soll. Dieser Parameter ist "true", wenn die Schaltfläche anzeigen soll, dessen Rahmen und "false", wenn die Schaltfläche "den Rahmen nicht angezeigt werden soll.

*bGrayDisabledButtons*<br/>
[in] Gibt an, ob deaktivierte Schaltflächen schattieren oder die Auflistung der deaktivierten Bilder. Dieser Parameter ist "true", wenn deaktivierte Schaltflächen schattierten und "false" werden soll, wenn diese Methode die Auflistung der deaktivierten Bilder verwenden sollten.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode zum Anpassen von Symbolleisten-Schaltfläche zeichnen.

##  <a name="ondrawoncustomizelist"></a>  CMFCDropDownToolbarButton::OnDrawOnCustomizeList

Wird aufgerufen, durch das Framework zum Zeichnen der Schaltfläche der **Befehle** im Bereich der **anpassen** im Dialogfeld.

```
virtual int OnDrawOnCustomizeList(
    CDC* pDC,
    const CRect& rect,
    BOOL bSelected);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
[in] Der Gerätekontext, in dem die Schaltfläche angezeigt.

*Rect*<br/>
[in] Das umschließende Rechteck der Schaltfläche.

*bSelected*<br/>
[in] Gibt an, ob die Schaltfläche ausgewählt wird. Wenn dieser Parameter TRUE ist, wird die Schaltfläche ausgewählt. Wenn dieser Parameter auf "false" ist, wird die Schaltfläche nicht ausgewählt.

### <a name="return-value"></a>Rückgabewert

Die Breite in Pixel der Schaltfläche auf den angegebenen Gerätekontext.

### <a name="remarks"></a>Hinweise

Diese Methode wird aufgerufen, indem Sie im Dialogfeld "anpassen" ( **Befehle** Registerkarte ") die Schaltfläche ist bei erforderlich, um das Ownerdrawn-Listenfeld angezeigt.

Diese Methode erweitert die basisklassenimplementierung ( [CMFCToolBarButton::OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist)) durch Ändern der Bezeichnung der Schaltfläche auf den Namen der Schaltfläche (d. h. auf den Wert des der *Wert* Parameter, der Sie sich an den Konstruktor übergeben).

##  <a name="serialize"></a>  CMFCDropDownToolbarButton::Serialize

Dieses Objekt aus einem Archiv liest oder schreibt dieses in ein Archiv.

```
virtual void Serialize(CArchive& ar);
```

### <a name="parameters"></a>Parameter

*ar*<br/>
[in] Die `CArchive` Objekt aus dem oder zum Serialisieren.

### <a name="remarks"></a>Hinweise

Diese Methode erweitert die basisklassenimplementierung ( [CMFCToolBarButton::Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize)) durch die Ressourcen-ID der übergeordneten Symbolleiste Serialisierung. Das Archiv wird geladen, wenn ( [CArchive::IsLoading](../../mfc/reference/carchive-class.md#isloading) gibt einen Wert ungleich null), diese Methode wird die `m_pToolBar` -Datenmember auf der Symbolleiste, die die serialisierte Ressource-ID enthält.

##  <a name="setdefaultcommand"></a>  CMFCDropDownToolbarButton::SetDefaultCommand

Legt fest, den Standardbefehl, den das Framework verwendet, wenn ein Benutzer die Schaltfläche klickt.

```
void SetDefaultCommand(UINT uiCmd);
```

### <a name="parameters"></a>Parameter

*uiCmd*<br/>
[in] Die ID des Standardbefehls.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Methode, um einen Standardbefehl angeben, den das Framework, das ausgeführt wird, wenn der Benutzer auf die Schaltfläche klickt. Ein Element mit der Befehls-ID, die anhand des *UiCmd* muss in der übergeordneten Dropdown-Symbolleiste befinden.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCDropDownToolBar-Klasse](../../mfc/reference/cmfcdropdowntoolbar-class.md)<br/>
[CMFCToolBar-Klasse](../../mfc/reference/cmfctoolbar-class.md)<br/>
[CMFCToolBarMenuButton-Klasse](../../mfc/reference/cmfctoolbarmenubutton-class.md)<br/>
[Exemplarische Vorgehensweise: Steuerelemente in eine Symbolleiste einfügen](../../mfc/walkthrough-putting-controls-on-toolbars.md)


---
title: CMFCColorPopupMenu-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMFCColorPopupMenu
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu::CMFCColorPopupMenu
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu::CreateTearOffBar
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu::GetMenuBar
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu::SetPropList
helpviewer_keywords:
- CMFCColorPopupMenu [MFC], CMFCColorPopupMenu
- CMFCColorPopupMenu [MFC], CreateTearOffBar
- CMFCColorPopupMenu [MFC], GetMenuBar
- CMFCColorPopupMenu [MFC], SetPropList
ms.assetid: 0bf9efe8-aed5-4ab7-b23b-eb284b4668be
ms.openlocfilehash: 0c2fed4aa239faa96abf692a46a27102ce9820a1
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57283396"
---
# <a name="cmfccolorpopupmenu-class"></a>CMFCColorPopupMenu-Klasse

Stellt ein Popup-Menü, das Benutzer verwenden, um die Farben in einem Dokument oder die Anwendung auswählen.

## <a name="syntax"></a>Syntax

```
class CMFCColorPopupMenu : public CMFCPopupMenu
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|||
|-|-|
|Name|Beschreibung|
|[CMFCColorPopupMenu::CMFCColorPopupMenu](#cmfccolorpopupmenu)|Erstellt ein `CMFCColorPopupMenu`-Objekt.|
|`CMFCColorPopupMenu::~CMFCColorPopupMenu`|Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|||
|-|-|
|Name|Beschreibung|
|[CMFCColorPopupMenu::CreateTearOffBar](#createtearoffbar)|Erstellt eine andockbare abtrennbare-Farbleiste an. (Überschreibt [CMFCPopupMenu::CreateTearOffBar](../../mfc/reference/cmfcpopupmenu-class.md#createtearoffbar).)|
|[CMFCColorPopupMenu::GetMenuBar](#getmenubar)|Gibt die [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md) , in dem Popupmenü eingebettet ist. (Overrides [CMFCPopupMenu::GetMenuBar](../../mfc/reference/cmfcpopupmenu-class.md#getmenubar).)|
|`CMFCColorPopupMenu::GetThisClass`|Durch das Framework verwendet wird, einen Zeiger zum Abrufen der [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das diesem Klassentyp zugeordnet ist.|
|[CMFCColorPopupMenu::SetPropList](#setproplist)|Legt das Grid-Steuerelement-Eigenschaftenobjekt der eingebetteten `CMFCColorBar` Objekt.|

### <a name="data-members"></a>Datenmember

|||
|-|-|
|name|Beschreibung|
|`m_bEnabledInCustomizeMode`|Ein boolescher Wert, der bestimmt, ob der Farbleiste angezeigt.|
|`m_wndColorBar`|Die `CMFCColorBar` Objekt, das die Farbauswahl bereitstellt.|

### <a name="remarks"></a>Hinweise

Diese Klasse erbt die Funktionalität im Popupmenü die `CMFCPopupMenu` Klasse und verwaltet eine `CMFCColorBar` Objekt, das die Farbauswahl bereitstellt. Wenn die Symbolleiste Framework ist im Anpassungsmodus und `m_bEnabledInCustomizeMode` Member auf "false" festgelegt ist, die Farbleiste-Objekt wird nicht angezeigt. Weitere Informationen zu den Anpassungsmodus, finden Sie unter [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)

Weitere Informationen zu `CMFCColorBar`, finden Sie unter [CMFCColorBar-Klasse](../../mfc/reference/cmfccolorbar-class.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

[CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)

[CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)

[CMFCColorPopupMenu](../../mfc/reference/cmfccolorpopupmenu-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxcolorpopupmenu.h

##  <a name="cmfccolorpopupmenu"></a>  CMFCColorPopupMenu::CMFCColorPopupMenu

Erstellt ein `CMFCColorPopupMenu`-Objekt.

```
CMFCColorPopupMenu(
    const CArray<COLORREF, COLORREF>& colors,
    COLORREF color,
    LPCTSTR lpszAutoColor,
    LPCTSTR lpszOtherColor,
    LPCTSTR lpszDocColors, CList<COLORREF, COLORREF>& lstDocColors,
    int nColumns,
    int nHorzDockRows,
    int nVertDockColumns,
    COLORREF colorAutomatic,
    UINT uiCommandID,
    BOOL bStdColorDlg = FALSE);

CMFCColorPopupMenu(
    CMFCColorButton* pParentBtn,
    const CArray<COLORREF, COLORREF>& colors,
    COLORREF color,
    LPCTSTR lpszAutoColor,
    LPCTSTR lpszOtherColor,
    LPCTSTR lpszDocColors, CList<COLORREF, COLORREF>& lstDocColors,
    int nColumns,
    COLORREF colorAutomatic);

CMFCColorPopupMenu(
    CMFCRibbonColorButton* pParentBtn,
    const CArray<COLORREF, COLORREF>& colors,
    COLORREF color,
    LPCTSTR lpszAutoColor,
    LPCTSTR lpszOtherColor,
    LPCTSTR lpszDocColors, CList<COLORREF, COLORREF>& lstDocColors,
    int nColumns,
    COLORREF colorAutomatic,
    UINT nID);
```

### <a name="parameters"></a>Parameter

*colors*<br/>
[in] Ein Array von Farben, die das Framework auf dem Popup-Menü angezeigt werden soll.

*color*<br/>
[in] Die standardmäßig ausgewählten Farbe.

*lpszAutoColor*<br/>
[in] Die textbezeichnung des der *automatische* farbenschaltfläche (Standard), oder NULL.

Die standardmäßige Bezeichnung für die automatische Schaltfläche ist **automatische**.

*lpszOtherColor*<br/>
[in] Die textbezeichnung des der *andere* Schaltfläche, welche zeigt weitere Farben, oder NULL.

Die standardmäßige Bezeichnung für die andere Schaltfläche ist **Weitere Farben...** .

*lpszDocColors*<br/>
[in] Die Beschriftung der Schaltfläche Dokument Farben. Die Farben (Palette) Dokument Listet alle Farben, die das Dokument derzeit verwendet.

*lstDocColors*<br/>
[in] Eine Liste von Farben, die das Dokument derzeit verwendet werden soll.

*nColumns*<br/>
[in] Die Anzahl der Spalten, die das Array von Farben aufweist.

*nHorzDockRows*<br/>
[in] Die Anzahl der Zeilen, die über der Farbleiste verfügt, wenn er horizontal angedockt ist.

*nVertDockColumns*<br/>
[in] Die Anzahl der Spalten, die der Farbleiste hat, wenn sie vertikal angedockt wird.

*colorAutomatic*<br/>
[in] Die Standardfarbe, die das Framework gilt, wenn Sie die automatische Schaltfläche klicken.

*uiCommandID*<br/>
[in] Der Befehl der Farbleiste-Control-ID.

*bStdColorDlg*<br/>
[in] Ein boolescher Wert, der angibt, ob das Dialogfeld Farbe standardsystembenachrichtigung angezeigt oder [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) Dialogfeld.

*pParentBtn*<br/>
[in] Ein Zeiger auf eine Schaltfläche "übergeordneten".

*nID*<br/>
[in] Die Befehls-ID.

### <a name="remarks"></a>Hinweise

Jede überladene Konstruktor legt die `m_bEnabledInCustomizeMode` Member auf "false".

### <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht das Erstellen einer `CMFCColorPopupMenu` Objekt.

[!code-cpp[NVC_MFC_RibbonApp#34](../../mfc/reference/codesnippet/cpp/cmfccolorpopupmenu-class_1.cpp)]

##  <a name="createtearoffbar"></a>  CMFCColorPopupMenu::CreateTearOffBar

Erstellt eine andockbare abtrennbare-Farbleiste an.

```
virtual CPane* CreateTearOffBar(
    CFrameWnd* pWndMain,
    UINT uiID,
    LPCTSTR lpszName);
```

### <a name="parameters"></a>Parameter

|||
|-|-|
|Parameter|Beschreibung|
|*pWndMain*|[in] Zeiger auf das übergeordnete Fenster der abtrennbarer Leiste.|
|*uiID*|[in] Die Befehls-ID der abtrennbarer Leiste.|
|*Wert*|[in] Der Fenstertext im der abtrennbarer Leiste.|

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die neue abtrennbare Steuerleistenobjekt.

### <a name="remarks"></a>Hinweise

Diese Methode erstellt eine [CMFCColorBar-Klasse](../../mfc/reference/cmfccolorbar-class.md) -Objekt und wandelt es zu einem [CPane-Klasse](../../mfc/reference/cpane-class.md) Zeiger. Sie können diesen Wert umwandeln an eine [CMFCColorBar-Klasse](../../mfc/reference/cmfccolorbar-class.md) Zeiger mit einem der die Umwandlung-Makros in [Typ umwandeln von MFC-Klasse von Objekten](../../mfc/reference/type-casting-of-mfc-class-objects.md).

##  <a name="getmenubar"></a>  CMFCColorPopupMenu::GetMenuBar

Gibt die [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md) , in dem Popupmenü eingebettet ist.

```
virtual CMFCPopupMenuBar* GetMenuBar();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die eingebettete `CMFCPopupMenuBar`.

### <a name="remarks"></a>Hinweise

Im Popupmenü "Farbe" verfügt über ein eingebettetes [CMFCPopupMenuBar-Klasse](../../mfc/reference/cmfcpopupmenubar-class.md) Objekt. Überschreiben Sie diese Methode in einer abgeleiteten Klasse an, wenn Ihre Anwendung einen anderen eingebetteten Typ verwendet.

##  <a name="setproplist"></a>  CMFCColorPopupMenu::SetPropList

Legt das Grid-Steuerelement-Eigenschaftenobjekt der eingebetteten `CMFCColorBar` Objekt.

```
void SetPropList(CMFCPropertyGridCtrl* pWndList);
```

### <a name="parameters"></a>Parameter

*pWndList*<br/>
[in] Zeiger auf ein Eigenschaftenobjekt der Grid-Steuerelement.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)

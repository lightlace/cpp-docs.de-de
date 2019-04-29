---
title: CMFCPopupMenuBar-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMFCPopupMenuBar
- AFXPOPUPMENUBAR/CMFCPopupMenuBar
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::AdjustSizeImmediate
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::BuildOrigItems
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::CloseDelayedSubMenu
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::ExportToMenu
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::FindDestintationToolBar
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::GetCurrentMenuImageSize
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::GetDefaultMenuId
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::GetLastCommandIndex
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::GetOffset
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::ImportFromMenu
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::IsDropDownListMode
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::IsPaletteMode
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::IsRibbonPanel
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::IsRibbonPanelInRegularMode
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::LoadFromHash
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::RestoreDelayedSubMenu
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::SetButtonStyle
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::SetOffset
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::StartPopupMenuTimer
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::m_bDisableSideBarInXPMode
helpviewer_keywords:
- CMFCPopupMenuBar [MFC], AdjustSizeImmediate
- CMFCPopupMenuBar [MFC], BuildOrigItems
- CMFCPopupMenuBar [MFC], CloseDelayedSubMenu
- CMFCPopupMenuBar [MFC], ExportToMenu
- CMFCPopupMenuBar [MFC], FindDestintationToolBar
- CMFCPopupMenuBar [MFC], GetCurrentMenuImageSize
- CMFCPopupMenuBar [MFC], GetDefaultMenuId
- CMFCPopupMenuBar [MFC], GetLastCommandIndex
- CMFCPopupMenuBar [MFC], GetOffset
- CMFCPopupMenuBar [MFC], ImportFromMenu
- CMFCPopupMenuBar [MFC], IsDropDownListMode
- CMFCPopupMenuBar [MFC], IsPaletteMode
- CMFCPopupMenuBar [MFC], IsRibbonPanel
- CMFCPopupMenuBar [MFC], IsRibbonPanelInRegularMode
- CMFCPopupMenuBar [MFC], LoadFromHash
- CMFCPopupMenuBar [MFC], RestoreDelayedSubMenu
- CMFCPopupMenuBar [MFC], SetButtonStyle
- CMFCPopupMenuBar [MFC], SetOffset
- CMFCPopupMenuBar [MFC], StartPopupMenuTimer
- CMFCPopupMenuBar [MFC], m_bDisableSideBarInXPMode
ms.assetid: 4c93c459-7f70-4240-8c63-280bb811e374
ms.openlocfilehash: acb1e2be7d40e5e0c569fffcc92c57c750be8f91
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62374024"
---
# <a name="cmfcpopupmenubar-class"></a>CMFCPopupMenuBar-Klasse

Eine Menüleiste, die in einem Popupmenü eingebettet ist.

## <a name="syntax"></a>Syntax

```
class CMFCPopupMenuBar : public CMFCToolBar
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCPopupMenuBar::AdjustSizeImmediate](#adjustsizeimmediate)|Sofort berechnet das Layout eines Bereichs ein. (Überschreibt [CPane::AdjustSizeImmediate](../../mfc/reference/cpane-class.md#adjustsizeimmediate).)|
|[CMFCPopupMenuBar::BuildOrigItems](#buildorigitems)|Lädt ein Popupmenüelemente aus einer angegebenen Menüressource.|
|[CMFCPopupMenuBar::CloseDelayedSubMenu](#closedelayedsubmenu)|Schließt eine verzögerte Popup-Schaltfläche.|
|[CMFCPopupMenuBar::ExportToMenu](#exporttomenu)|Erstellt ein Menü in der Popup-Menü-Schaltflächen an.|
|[CMFCPopupMenuBar::FindDestintationToolBar](#finddestintationtoolbar)|Sucht die Symbolleiste befindet, in einem bestimmten Zeitpunkt.|
|[CMFCPopupMenuBar::GetCurrentMenuImageSize](#getcurrentmenuimagesize)|Gibt die Größe der Menüschaltfläche des Images an.|
|[CMFCPopupMenuBar::GetDefaultMenuId](#getdefaultmenuid)|Gibt den Bezeichner des das Standardmenüelement.|
|[CMFCPopupMenuBar::GetLastCommandIndex](#getlastcommandindex)|Ruft den Index des zuletzt ausgeführten Menübefehls.|
|[CMFCPopupMenuBar::GetOffset](#getoffset)|Ruft den Zeilenoffset der Popup-Menüleiste.|
|[CMFCPopupMenuBar::ImportFromMenu](#importfrommenu)|Importiert Popup-Menü-Schaltflächen in einem angegebenen Menü an.|
|[CMFCPopupMenuBar::IsDropDownListMode](#isdropdownlistmode)|Gibt an, ob die Menüleiste "Popup" im Drop-Down-List-Modus befindet.|
|[CMFCPopupMenuBar::IsPaletteMode](#ispalettemode)|Gibt an, ob die Menüleiste "Popup" in der Palettenmodus befindet.|
|[CMFCPopupMenuBar::IsRibbonPanel](#isribbonpanel)|Gibt an, ob dies ein Menübandbereich (standardmäßig "false") ist.|
|[CMFCPopupMenuBar::IsRibbonPanelInRegularMode](#isribbonpanelinregularmode)|Gibt an, ob dies ein Menübandbereich im regulären Modus (standardmäßig "false") ist.|
|[CMFCPopupMenuBar::LoadFromHash](#loadfromhash)|Lädt eine archivierte Menü an.|
|[CMFCPopupMenuBar::RestoreDelayedSubMenu](#restoredelayedsubmenu)|Stellt eine verzögerte Schaltfläche zum Schließen der Popup-Menüleiste.|
|[CMFCPopupMenuBar::SetButtonStyle](#setbuttonstyle)|Legt das Format der Symbolleisten-Schaltfläche am angegebenen Index fest. (Überschreibt [CMFCToolBar::SetButtonStyle](../../mfc/reference/cmfctoolbar-class.md#setbuttonstyle).)|
|[CMFCPopupMenuBar::SetOffset](#setoffset)|Legt die Zeilenoffset die Menüleiste "Popup" fest.|
|[CMFCPopupMenuBar::StartPopupMenuTimer](#startpopupmenutimer)|Startet den Timer für eine angegebenen verzögerten Popup-Menü-Schaltfläche.|

### <a name="data-members"></a>Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CMFCPopupMenuBar::m_bDisableSideBarInXPMode](#m_bdisablesidebarinxpmode)|Gibt an, ob die graue Randleiste angezeigt wird, wenn die Anwendung über eine Darstellung von Windows XP verfügt.|

## <a name="remarks"></a>Hinweise

Die `CMFCPopupMenuBar` wird erstellt, zur gleichen Zeit wie eine [CMFCPopupMenu-Klasse](../../mfc/reference/cmfcpopupmenu-class.md) und darin eingebetteten. Die `CMFCPopupMenuBar` deckt den gesamten Clientbereich, der die `CMFCPopupMenu` Objekt. Tastatur- und Mauseingaben unterstützt. Kommuniziert es auch, dass die Eingabe die `CMFCPopupMenu` und Rahmenfenster der obersten Ebene.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird veranschaulicht, wie zum Initialisieren einer `CMFCPopupMenuBar` -Objekt aus einem `CMFCPopupMenu` Objekt. Dieser Codeausschnitt ist Teil des [Draw Client-Beispiels](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_DrawClient#7](../../mfc/reference/codesnippet/cpp/cmfcpopupmenubar-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)

[CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)

[CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxpopupmenubar.h

##  <a name="adjustsizeimmediate"></a>  CMFCPopupMenuBar::AdjustSizeImmediate

Sofort berechnet das Layout des Bereichs Leiste Popup-Menü aus. (Überschreibt [CPane::AdjustSizeImmediate](../../mfc/reference/cpane-class.md#adjustsizeimmediate).

```
virtual void AdjustSizeImmediate(BOOL bRecalcLayout);
```

### <a name="parameters"></a>Parameter

*bRecalcLayout*<br/>
[in] True, um das Layout des Menübereichs Leiste Popup automatisch neu berechnet. andernfalls "false".

### <a name="remarks"></a>Hinweise

##  <a name="buildorigitems"></a>  CMFCPopupMenuBar::BuildOrigItems

Lädt ein Popupmenüelemente aus einer angegebenen Menüressource.

```
BOOL BuildOrigItems(UINT uiMenuResID);
```

### <a name="parameters"></a>Parameter

*uiMenuResID*<br/>
[in] Gibt an, die Menü-ID der Menüressource laden.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg oder FALSE zurück.

### <a name="remarks"></a>Hinweise

##  <a name="closedelayedsubmenu"></a>  CMFCPopupMenuBar::CloseDelayedSubMenu

Schließt eine Popup-Menü-Schaltfläche, die verzögert wurde.

```
virtual void CloseDelayedSubMenu();
```

### <a name="remarks"></a>Hinweise

##  <a name="exporttomenu"></a>  CMFCPopupMenuBar::ExportToMenu

Erstellt ein Menü in der Popup-Menü-Schaltflächen an.

```
virtual HMENU ExportToMenu() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt ein Handle für das neue Menü an.

### <a name="remarks"></a>Hinweise

##  <a name="finddestintationtoolbar"></a>  CMFCPopupMenuBar::FindDestintationToolBar

Sucht die Symbolleiste befindet, in einem bestimmten Zeitpunkt.

```
CMFCToolBar* FindDestintationToolBar(CPoint point);
```

### <a name="parameters"></a>Parameter

*point*<br/>
[in] Ein Punkt auf dem Bildschirm.

### <a name="return-value"></a>Rückgabewert

Gibt ein Handle für die Symbolleiste, wo liegt der Punkt, sofern vorhanden, oder NULL, wenn nicht.

### <a name="remarks"></a>Hinweise

##  <a name="getcurrentmenuimagesize"></a>  CMFCPopupMenuBar::GetCurrentMenuImageSize

Gibt die Größe der Menüschaltfläche des Images an.

```
virtual CSize GetCurrentMenuImageSize() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt die Größe der Menüschaltfläche des Images in der Symbolleiste zurück.

### <a name="remarks"></a>Hinweise

##  <a name="getdefaultmenuid"></a>  CMFCPopupMenuBar::GetDefaultMenuId

Gibt den Bezeichner des das Standardmenüelement.

```
UINT GetDefaultMenuId() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt den Bezeichner des das Standardmenüelement in die Menüleiste "Popup" zurück.

### <a name="remarks"></a>Hinweise

##  <a name="getlastcommandindex"></a>  CMFCPopupMenuBar::GetLastCommandIndex

Ruft den Index des zuletzt ausgeführten Menübefehls.

```
static int __stdcall GetLastCommandIndex();
```

### <a name="return-value"></a>Rückgabewert

Gibt den Index des letzten Menübefehls im, das aufgerufen wurde.

### <a name="remarks"></a>Hinweise

##  <a name="getoffset"></a>  CMFCPopupMenuBar::GetOffset

Ruft den Zeilenoffset der Popup-Menüleiste.

```
int GetOffset() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt die Menüleiste "Popup" die Zeilenoffset zurück.

### <a name="remarks"></a>Hinweise

Dieser Wert wird festgelegt, mit [CMFCPopupMenuBar::SetOffset](#setoffset).

##  <a name="importfrommenu"></a>  CMFCPopupMenuBar::ImportFromMenu

Importiert Popup-Menü-Schaltflächen in einem angegebenen Menü an.

```
virtual BOOL ImportFromMenu(
    HMENU hMenu,
    BOOL bShowAllCommands = FALSE);
```

### <a name="parameters"></a>Parameter

*hMenu*<br/>
[in] Klicken Sie im Menü aus der die Popup-Menüschaltflächen importiert werden soll.

*bShowAllCommands*<br/>
[in] TRUE, wenn alle Befehle in diesem Menü werden importiert, oder FALSE, wenn Sie nur selten verwendeten ausgeblendet werden können.

### <a name="return-value"></a>Rückgabewert

Gibt TRUE zurück, wenn die Menüschaltflächen, nicht erfolgreich aus dem Menü, oder FALSE, wenn importiert wurden.

### <a name="remarks"></a>Hinweise

##  <a name="isdropdownlistmode"></a>  CMFCPopupMenuBar::IsDropDownListMode

Gibt an, ob die Menüleiste "Popup" im Drop-Down-List-Modus befindet.

```
BOOL IsDropDownListMode() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt TRUE zurück, wenn die Popup-Menüleiste im Drop-Down-List-Modus oder FALSE, wenn nicht ist.

### <a name="remarks"></a>Hinweise

##  <a name="ispalettemode"></a>  CMFCPopupMenuBar::IsPaletteMode

Gibt an, ob die Menüleiste "Popup" in der Palettenmodus befindet.

```
BOOL IsPaletteMode() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn die Palettenmodus aktiviert ist, oder "false" ist dies nicht der zurück.

### <a name="remarks"></a>Hinweise

Wenn die Menüleiste auf Palettenmodus festgelegt ist, werden die Menüelemente in mehreren Spalten und eine begrenzte Anzahl von Zeilen angezeigt.

##  <a name="isribbonpanel"></a>  CMFCPopupMenuBar::IsRibbonPanel

Gibt an, ob dies ein Menübandbereich (standardmäßig "false") ist.

```
virtual BOOL IsRibbonPanel() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt FALSE zurück, in der Standardeinstellung gibt an, dass es sich nicht um einen Menübandbereich handelt.

### <a name="remarks"></a>Hinweise

##  <a name="isribbonpanelinregularmode"></a>  CMFCPopupMenuBar::IsRibbonPanelInRegularMode

Gibt an, ob dies ein Menübandbereich im regulären Modus (standardmäßig "false") ist.

```
virtual BOOL IsRibbonPanelInRegularMode() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt FALSE zurück, in der Standardeinstellung gibt an, dass dies keinem Menübandbereich im regulären Modus ist.

### <a name="remarks"></a>Hinweise

##  <a name="loadfromhash"></a>  CMFCPopupMenuBar::LoadFromHash

Lädt eine archivierte Menü an.

```
BOOL LoadFromHash(HMENU hMenu);
```

### <a name="parameters"></a>Parameter

*hMenu*<br/>
[in] Ein Handle für das archivierte Menü geladen werden.

### <a name="return-value"></a>Rückgabewert

Gibt TRUE zurück, wenn das Menü erfolgreich geladen wurde, oder FALSE, wenn nicht wird.

### <a name="remarks"></a>Hinweise

##  <a name="m_bdisablesidebarinxpmode"></a>  CMFCPopupMenuBar::m_bDisableSideBarInXPMode

Ein boolescher Parameter, der angibt, ob Ihre Anwendung eine graue Randleiste verfügt, wenn es sich um die Darstellung eines Windows XP hat.

```
BOOL m_bDisableSideBarInXPMode;
```

### <a name="remarks"></a>Hinweise

Wenn diese Membervariable auf "false" festgelegt ist, und die Anwendung eine Darstellung von Windows XP enthält, zeichnet das Framework eine graue Randleiste in Ihrer Anwendung.

Der Standardwert ist "false".

##  <a name="restoredelayedsubmenu"></a>  CMFCPopupMenuBar::RestoreDelayedSubMenu

Stellt eine verzögerte Schaltfläche zum Schließen der Popup-Menüleiste.

```
virtual void RestoreDelayedSubMenu();
```

### <a name="remarks"></a>Hinweise

##  <a name="setbuttonstyle"></a>  CMFCPopupMenuBar::SetButtonStyle

Legt das Format der Symbolleisten-Schaltfläche am angegebenen Index fest. (Überschreibt [CMFCToolBar::SetButtonStyle](../../mfc/reference/cmfctoolbar-class.md#setbuttonstyle).)

```
virtual void SetButtonStyle(
    int nIndex,
    UINT nStyle);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
[in] Der nullbasierte Index der Symbolleisten-Schaltfläche, dessen Stil ist, festgelegt werden.

*nStyle*<br/>
[in] Der Stil der Schaltfläche. Finden Sie unter [ToolBar-Steuerelement-Stile](../../mfc/reference/toolbar-control-styles.md) für die Liste der Formatvorlagen für Symbolleistenschaltflächen von verfügbar.

### <a name="remarks"></a>Hinweise

##  <a name="setoffset"></a>  CMFCPopupMenuBar::SetOffset

Legt die Zeilenoffset die Menüleiste "Popup" fest.

```
void SetOffset(int iOffset);
```

### <a name="parameters"></a>Parameter

*iOffset*<br/>
[in] Die Anzahl der Zeilen an, die die Menüleiste "Popup" versetzt werden sollen.

### <a name="remarks"></a>Hinweise

##  <a name="startpopupmenutimer"></a>  CMFCPopupMenuBar::StartPopupMenuTimer

Startet den Timer für eine angegebenen verzögerten Popup-Menü-Schaltfläche.

```
void StartPopupMenuTimer(
    CMFCToolBarMenuButton* pMenuButton,
    int nDelayFactor = 1);
```

### <a name="parameters"></a>Parameter

*pMenuButton*<br/>
[in] Zeiger auf die Schaltfläche für das der verzögerungszeitgeber festgelegt.

*nDelayFactor*<br/>
[in] Verzögerung der Faktor, gleich mit mindestens einem durch die standardmäßige Menü-Verzögerungszeit (in der Regel zwischen einer halben Sekunde und fünf Sekunden) multipliziert.

### <a name="remarks"></a>Hinweise

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCColorBar-Klasse](../../mfc/reference/cmfccolorbar-class.md)<br/>
[CMFCPopupMenu-Klasse](../../mfc/reference/cmfcpopupmenu-class.md)

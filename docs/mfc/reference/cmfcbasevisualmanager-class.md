---
title: CMFCBaseVisualManager-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCBaseVisualManager
- AFXVISUALMANAGER/CMFCBaseVisualManager
- AFXVISUALMANAGER/CMFCBaseVisualManager::CMFCBaseVisualManager
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawCheckBox
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawComboBorder
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawComboDropButton
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawPushButton
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawRadioButton
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawStatusBarProgress
- AFXVISUALMANAGER/CMFCBaseVisualManager::FillReBarPane
- AFXVISUALMANAGER/CMFCBaseVisualManager::GetStandardWindowsTheme
- AFXVISUALMANAGER/CMFCBaseVisualManager::CleanUpThemes
- AFXVISUALMANAGER/CMFCBaseVisualManager::UpdateSystemColors
dev_langs:
- C++
helpviewer_keywords:
- CMFCBaseVisualManager [MFC], CMFCBaseVisualManager
- CMFCBaseVisualManager [MFC], DrawCheckBox
- CMFCBaseVisualManager [MFC], DrawComboBorder
- CMFCBaseVisualManager [MFC], DrawComboDropButton
- CMFCBaseVisualManager [MFC], DrawPushButton
- CMFCBaseVisualManager [MFC], DrawRadioButton
- CMFCBaseVisualManager [MFC], DrawStatusBarProgress
- CMFCBaseVisualManager [MFC], FillReBarPane
- CMFCBaseVisualManager [MFC], GetStandardWindowsTheme
- CMFCBaseVisualManager [MFC], CleanUpThemes
- CMFCBaseVisualManager [MFC], UpdateSystemColors
ms.assetid: d56f3afc-cdea-4de1-825a-a08999c571e0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ec48152b918fb43cf859377e64eeb64478ad15f3
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46374274"
---
# <a name="cmfcbasevisualmanager-class"></a>CMFCBaseVisualManager-Klasse

Eine Ebene zwischen abgeleiteten Erscheinungsbild-Manager und der Windows-Design-API.

`CMFCBaseVisualManager` UxTheme.dll, lädt, falls verfügbar, und verwaltet den Zugriff auf Windows-Design-API-Methoden.

Diese Klasse ist nur zur internen Verwendung.

## <a name="syntax"></a>Syntax

```
class CMFCBaseVisualManager: public CObject
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|||
|-|-|
|Name|Beschreibung|
|[CMFCBaseVisualManager::CMFCBaseVisualManager](#cmfcbasevisualmanager)|Erstellt und initialisiert ein `CMFCBaseVisualManager`-Objekt.|
|`CMFCBaseVisualManager::~CMFCBaseVisualManager`|Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|||
|-|-|
|Name|Beschreibung|
|[CMFCBaseVisualManager::DrawCheckBox](#drawcheckbox)|Zeichnet ein Kontrollkästchen-Steuerelement mit dem aktuellen Windows-Design.|
|[CMFCBaseVisualManager::DrawComboBorder](#drawcomboborder)|Zeichnet einen Combo Box Rahmen mit dem aktuellen Windows-Design.|
|[CMFCBaseVisualManager::DrawComboDropButton](#drawcombodropbutton)|Zeichnet eine Dropdown-kombinationsfeldschaltfläche mit dem aktuellen Windows-Design.|
|[CMFCBaseVisualManager::DrawPushButton](#drawpushbutton)|Zeichnet eine Schaltfläche mit dem aktuellen Windows-Design.|
|[CMFCBaseVisualManager::DrawRadioButton](#drawradiobutton)|Zeichnet ein Optionsfeld-Steuerelement mit dem aktuellen Windows-Design.|
|[CMFCBaseVisualManager::DrawStatusBarProgress](#drawstatusbarprogress)|Zeichnet eine Statusanzeige auf ein Statusleisten-Steuerelement ( [CMFCStatusBar-Klasse](../../mfc/reference/cmfcstatusbar-class.md)) mit dem aktuellen Windows-Design.|
|[CMFCBaseVisualManager::FillReBarPane](#fillrebarpane)|Füllt den Hintergrund des Infoleisten-Steuerelements mit dem aktuellen Windows-Design.|
|[CMFCBaseVisualManager::GetStandardWindowsTheme](#getstandardwindowstheme)|Ruft das aktuelle Windows-Design ab.|

### <a name="protected-methods"></a>Geschützte Methoden

|||
|-|-|
|Name|Beschreibung|
|[CMFCBaseVisualManager::CleanUpThemes](#cleanupthemes)|Aufrufe `CloseThemeData` für alle Handles in abgerufenen `UpdateSystemColors`.|
|[CMFCBaseVisualManager::UpdateSystemColors](#updatesystemcolors)|Aufrufe `OpenThemeData` zum Abrufen von Handles für die verschiedenen Steuerelemente zeichnen: Windows, Symbolleisten, Schaltflächen und So weiter.|

## <a name="remarks"></a>Hinweise

Sie müssen keine Objekte dieser Klasse nicht direkt instanziieren.

Da es sich um eine Basisklasse für alle visuellen Manager handelt, rufen Sie einfach [CMFCVisualManager::GetInstance](../../mfc/reference/cmfcvisualmanager-class.md#getinstance)Abrufen eines Zeigers auf den aktuellen Visual-Manager und Zugriff auf die Methoden für die `CMFCBaseVisualManager` verwenden diesen Zeiger. Wenn Sie ein Steuerelement angezeigt wird, mit dem aktuellen Windows-Design haben, es ist jedoch besser, verwenden Sie die `CMFCVisualManagerWindows` Schnittstelle.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CMFCBaseVisualManager](../../mfc/reference/cmfcbasevisualmanager-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxvisualmanager.h

##  <a name="cleanupthemes"></a>  CMFCBaseVisualManager::CleanUpThemes

Aufrufe `CloseThemeData` für alle Handles in abgerufenen `UpdateSystemColors`.

```
void CleanUpThemes();
```

### <a name="remarks"></a>Hinweise

Nur für interne Verwendung.

##  <a name="cmfcbasevisualmanager"></a>  CMFCBaseVisualManager::CMFCBaseVisualManager

Erstellt und initialisiert ein `CMFCBaseVisualManager`-Objekt.

```
CMFCBaseVisualManager();
```

##  <a name="drawcheckbox"></a>  CMFCBaseVisualManager::DrawCheckBox

Zeichnet ein Kontrollkästchen-Steuerelement mit dem aktuellen Windows-Design.

```
virtual BOOL DrawCheckBox(
    CDC* pDC,
    CRect rect,
    BOOL bHighlighted,
    int nState,
    BOOL bEnabled,
    BOOL bPressed);

);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
[in] Ein Zeiger auf einen Gerätekontext

*Rect*<br/>
[in] Das umschließende Rechteck des Kontrollkästchens.

*bHighlighted*<br/>
[in] Gibt an, ob das Kontrollkästchen markiert ist.

*nState*<br/>
[in] 0 für deaktiviert, 1 für Normal aktiviert,

2 für gemischte Normal.

*bAktiviert*<br/>
[in] Gibt an, ob das Kontrollkästchen aktiviert ist.

*bPressed*<br/>
[in] Gibt an, ob das Kontrollkästchen geklickt wird.

### <a name="return-value"></a>Rückgabewert

True, wenn der Design-API aktiviert ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

Die Werte der *nState* entsprechen die folgenden Kontrollkästchen-Stile.

|nState|Aktivieren Sie das Kontrollkästchen-Stil|
|------------|---------------------|
|0|CBS_UNCHECKEDNORMAL|
|1|CBS_CHECKEDNORMAL|
|2|CBS_MIXEDNORMAL|

##  <a name="drawcomboborder"></a>  CMFCBaseVisualManager::DrawComboBorder

Zeichnet den Rahmen des Kombinationsfelds mit dem aktuellen Windows-Design.

```
virtual BOOL DrawComboBorder(
    CDC* pDC,
    CRect rect,
    BOOL bDisabled,
    BOOL bIsDropped,
    BOOL bIsHighlighted);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
[in] Ein Zeiger auf einen Gerätekontext.

*Rect*<br/>
[in] Umschließende Rechteck des Rahmen des Kombinationsfelds.

*bDeaktiviert*<br/>
[in] Gibt an, ob der Rahmen des Kombinationsfelds deaktiviert ist.

*bIsDropped*<br/>
[in] Gibt an, ob der Rahmen des Kombinationsfelds nach unten gelöscht wird.

*bIsHighlighted*<br/>
[in] Gibt an, ob der Rahmen des Kombinationsfelds markiert wird.

### <a name="return-value"></a>Rückgabewert

True, wenn der Design-API aktiviert ist. andernfalls "false".

##  <a name="drawcombodropbutton"></a>  CMFCBaseVisualManager::DrawComboDropButton

Zeichnet eine Dropdown-kombinationsfeldschaltfläche mit dem aktuellen Windows-Design.

```
virtual BOOL DrawComboDropButton(
    CDC* pDC,
    CRect rect,
    BOOL bDisabled,
    BOOL bIsDropped,
    BOOL bIsHighlighted);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*pDC*|[in] Ein Zeiger auf einen Gerätekontext.|
|*Rect*|[in] Das umschließende Rechteck von der Dropdown-kombinationsfeldschaltfläche.|
|*bDeaktiviert*|[in] Gibt an, ob der Dropdown-kombinationsfeldschaltfläche deaktiviert ist.|
|*bIsDropped*|[in] Gibt an, ob der Dropdown-kombinationsfeldschaltfläche, nach unten gelöscht wird.|
|*bIsHighlighted*|[in] Gibt an, ob der Dropdown-kombinationsfeldschaltfläche hervorgehoben ist.|

### <a name="return-value"></a>Rückgabewert

True, wenn der Design-API aktiviert ist. andernfalls "false".

##  <a name="drawpushbutton"></a>  CMFCBaseVisualManager::DrawPushButton

Zeichnet eine Schaltfläche mit dem aktuellen Windows-Design.

```
virtual BOOL DrawPushButton(
    CDC* pDC,
    CRect rect,
    CMFCButton* pButton,
    UINT uiState);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
[in] Ein Zeiger auf einen Gerätekontext.

*Rect*<br/>
[in] Das umschließende Rechteck von der Schaltfläche.

*pButton*<br/>
[in] Ein Zeiger auf die [CMFCButton-Klasse](../../mfc/reference/cmfcbutton-class.md) Objekt, das gezeichnet werden soll.

*uiState*<br/>
[in] Ignoriert. Der Status stammt aus *pButton*.

### <a name="return-value"></a>Rückgabewert

True, wenn der Design-API aktiviert ist. andernfalls "false".

##  <a name="drawradiobutton"></a>  CMFCBaseVisualManager::DrawRadioButton

Zeichnet ein Optionsfeld-Steuerelement mit dem aktuellen Windows-Design.

```
virtual BOOL DrawRadioButton(
    CDC* pDC,
    CRect rect,
    BOOL bHighlighted,
    BOOL bChecked,
    BOOL bEnabled,
    BOOL bPressed);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
[in] Ein Zeiger auf einen Gerätekontext.

*Rect*<br/>
[in] Das umschließende Rechteck des Optionsfelds.

*bHighlighted*<br/>
[in] Gibt an, ob das Optionsfeld "hervorgehoben ist.

*bChecked*<br/>
[in] Gibt an, ob das Optionsfeld aktiviert ist.

*bAktiviert*<br/>
[in] Gibt an, ob das Optionsfeld aktiviert ist.

*bPressed*<br/>
[in] Gibt an, ob das Optionsfeld gedrückt wird.

### <a name="return-value"></a>Rückgabewert

True, wenn der Design-API aktiviert ist. andernfalls "false".

##  <a name="drawstatusbarprogress"></a>  CMFCBaseVisualManager::DrawStatusBarProgress

Zeichnet Statusanzeige auf der Statusleiste-Steuerelement ( [CMFCStatusBar-Klasse](../../mfc/reference/cmfcstatusbar-class.md)) mit dem aktuellen Windows-Design.

```
virtual BOOL DrawStatusBarProgress(
    CDC* pDC,
    CMFCStatusBar* pStatusBar,
    CRect rectProgress,
    int nProgressTotal,
    int nProgressCurr,
    COLORREF clrBar,
    COLORREF clrProgressBarDest,
    COLORREF clrProgressText,
    BOOL bProgressText);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
[in] Ein Zeiger auf einen Gerätekontext.

*pStatusBar*<br/>
[in] Ein Zeiger auf die Statusleiste. Dieser Wert wird ignoriert.

*rectProgress*<br/>
[in] Das umschließende Rechteck der Statusanzeige in *pDC* Koordinaten.

*nProgressTotal*<br/>
[in] Der gesamte Statuswert.

*nProgressCurr*<br/>
[in] Der aktuelle Status-Wert.

*clrBar*<br/>
[in] Die Startfarbe. `CMFCBaseVisualManager` ignoriert diese. Abgeleitete Klassen können sie für Farbverläufe verwenden.

*clrProgressBarDest*<br/>
[in] Die Endfarbe. `CMFCBaseVisualManager` ignoriert diese. Abgeleitete Klassen können sie für Farbverläufe verwenden.

*clrProgressText*<br/>
[in] Textfarbe des Status. `CMFCBaseVisualManager` ignoriert diese. Die Textfarbe wird definiert, indem `afxGlobalData.clrBtnText`.

*bProgressText*<br/>
[in] Gibt an, ob der Text angezeigt werden soll.

### <a name="return-value"></a>Rückgabewert

True, wenn der Design-API aktiviert ist. andernfalls "false".

##  <a name="fillrebarpane"></a>  CMFCBaseVisualManager::FillReBarPane

Füllt den Hintergrund des Infoleisten-Steuerelements mit dem aktuellen Windows-Design.

```
virtual void FillReBarPane(
    CDC* pDC,
    CBasePane* pBar,
    CRect rectClient);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
[in] Ein Zeiger auf einen Gerätekontext.

*pBar*<br/>
[in] Ein Zeiger auf einen Bereich, dessen Hintergrund gezeichnet werden soll.

*rectClient*<br/>
[in] Das umschließende Rechteck des Bereichs, der gefüllt werden soll.

### <a name="return-value"></a>Rückgabewert

True, wenn der Design-API aktiviert ist. andernfalls "false".

##  <a name="getstandardwindowstheme"></a>  CMFCBaseVisualManager::GetStandardWindowsTheme

Ruft das aktuelle Windows-Design ab.

```
virtual WinXpTheme GetStandardWindowsTheme();
```

### <a name="return-value"></a>Rückgabewert

Die zurzeit ausgewählte Farbe mit Design "Windows". Dabei kann es sich um eine der folgenden Enumerationswerte sein:

- `WinXpTheme_None` – Es gibt keine Designs aktiviert.

- `WinXpTheme_NonStandard` -nicht standardmäßige Design (d. h., ein Design ausgewählt ist, aber keine aus der Liste unten) aktiviert ist.

- `WinXpTheme_Blue` -Design "Blau" (Luna).

- `WinXpTheme_Olive` -Oliv Design.

- `WinXpTheme_Silver` -silberfarbenes Design.

##  <a name="updatesystemcolors"></a>  CMFCBaseVisualManager::UpdateSystemColors

Aufrufe `OpenThemeData` zum Abrufen von Handles für die verschiedenen Steuerelemente zeichnen: Windows, Symbolleisten, Schaltflächen und So weiter.

```
void UpdateSystemColors();
```

### <a name="remarks"></a>Hinweise

Nur für interne Verwendung.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)

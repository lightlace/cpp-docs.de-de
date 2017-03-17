---
title: Klasse CMFCBaseVisualManager | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
- ~CMFCBaseVisualManager destructor
- CMFCBaseVisualManager class, destructor
- CMFCBaseVisualManager class
ms.assetid: d56f3afc-cdea-4de1-825a-a08999c571e0
caps.latest.revision: 24
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 7c726fe71b7dcf26353fe0ce3a6b383eb5b578b9
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcbasevisualmanager-class"></a>CMFCBaseVisualManager-Klasse
Eine Ebene zwischen abgeleiteten visuellen Manager und der Windows-API-Design.  
  
 `CMFCBaseVisualManager`Lädt UxTheme.dll, sofern verfügbar, und verwaltet den Zugriff auf Windows-Design-API-Methoden.  
  
 Diese Klasse ist nur zur internen Verwendung.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCBaseVisualManager: public CObject  
```  
  
## <a name="members"></a>Mitglieder  
  
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
|[CMFCBaseVisualManager::DrawComboBorder](#drawcomboborder)|Zeichnet den Rahmen ein Kombinationsfeld mit dem aktuellen Windows-Design.|  
|[CMFCBaseVisualManager::DrawComboDropButton](#drawcombodropbutton)|Zeichnet eine Kombinationsfeld Dropdown-Schaltfläche mit dem aktuellen Windows-Design.|  
|[CMFCBaseVisualManager::DrawPushButton](#drawpushbutton)|Zeichnet eine Schaltfläche mit dem aktuellen Windows-Design.|  
|[CMFCBaseVisualManager::DrawRadioButton](#drawradiobutton)|Zeichnet ein Optionsfeld-Steuerelement mit dem aktuellen Windows-Design.|  
|[CMFCBaseVisualManager::DrawStatusBarProgress](#drawstatusbarprogress)|Zeichnet eine Statusanzeige auf ein Statusleisten-Steuerelement ( [CMFCStatusBar-Klasse](../../mfc/reference/cmfcstatusbar-class.md)) mit dem aktuellen Windows-Design.|  
|[CMFCBaseVisualManager::FillReBarPane](#fillrebarpane)|Füllt den Hintergrund des Grundleisten-Steuerelement mit der aktuellen Windows-Designs.|  
|[CMFCBaseVisualManager::GetStandardWindowsTheme](#getstandardwindowstheme)|Ruft das aktuelle Windows-Design ab.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|||  
|-|-|  
|Name|Beschreibung|  
|[CMFCBaseVisualManager::CleanUpThemes](#cleanupthemes)|Aufrufe `CloseThemeData` für alle Handles in abgerufen `UpdateSystemColors`.|  
|[CMFCBaseVisualManager::UpdateSystemColors](#updatesystemcolors)|Aufrufe `OpenThemeData` zum Abrufen von Handles für die verschiedenen Steuerelemente zeichnen: Windows, Symbolleisten, Schaltflächen und So weiter.|  
  
## <a name="remarks"></a>Hinweise  
 Sie müssen keinen Objekte dieser Klasse direkt zu instanziieren.  
  
 Da es sich um eine Basisklasse für alle visuellen Manager handelt, können Sie nur aufrufen [CMFCVisualManager::GetInstance](../../mfc/reference/cmfcvisualmanager-class.md#getinstance)und rufen Sie einen Zeiger auf den aktuellen Visual-Manager und die Methoden für die `CMFCBaseVisualManager` mit diesen Zeiger. Wenn Sie ein Steuerelement mit dem aktuellen Windows-Design angezeigt haben, es ist jedoch besser, verwenden Sie die `CMFCVisualManagerWindows` Schnittstelle.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCBaseVisualManager](../../mfc/reference/cmfcbasevisualmanager-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxvisualmanager.h  
  
##  <a name="cleanupthemes"></a>CMFCBaseVisualManager::CleanUpThemes  
 Aufrufe `CloseThemeData` für alle Handles in abgerufen `UpdateSystemColors`.  
  
```  
void CleanUpThemes();
```  
  
### <a name="remarks"></a>Hinweise  
 Nur für interne Verwendung.  
  
##  <a name="cmfcbasevisualmanager"></a>CMFCBaseVisualManager::CMFCBaseVisualManager  
 Erstellt und initialisiert ein `CMFCBaseVisualManager`-Objekt.  
  
```  
CMFCBaseVisualManager();
```  
  
##  <a name="drawcheckbox"></a>CMFCBaseVisualManager::DrawCheckBox  
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
 [in] `pDC`  
 Ein Zeiger auf einen Gerätekontext  
  
 [in] `rect`  
 Das umschließende Rechteck des Kontrollkästchens.  
  
 [in] `bHighlighted`  
 Gibt an, ob das Kontrollkästchen markiert wird.  
  
 [in] `nState`  
 0 für die Option deaktiviert, 1 für aktivierten Normal  
  
 2 für gemischten Normal.  
  
 [in] `bEnabled`  
 Gibt an, ob das Kontrollkästchen aktiviert ist.  
  
 [in] `bPressed`  
 Gibt an, ob das Kontrollkästchen gedrückt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Design-API aktiviert ist. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Die Werte der `nState` die folgenden Kontrollkästchen-Stile entsprechen.  
  
|nState|Das Kontrollkästchen Stil|  
|------------|---------------------|  
|0|CBS_UNCHECKEDNORMAL|  
|1|CBS_CHECKEDNORMAL|  
|2|CBS_MIXEDNORMAL|  
  
##  <a name="drawcomboborder"></a>CMFCBaseVisualManager::DrawComboBorder  
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
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `rect`  
 Umschließende Rechteck für den Rahmen des Kombinationsfelds.  
  
 [in] `bDisabled`  
 Gibt an, ob der Rahmen des Kombinationsfelds deaktiviert ist.  
  
 [in] `bIsDropped`  
 Gibt an, ob der Kombinationsfeld Rahmen sichtbar ist.  
  
 [in] `bIsHighlighted`  
 Gibt an, ob der Rahmen des Kombinationsfelds markiert wird.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Design-API aktiviert ist. andernfalls `FALSE`.  
  
##  <a name="drawcombodropbutton"></a>CMFCBaseVisualManager::DrawComboDropButton  
 Zeichnet eine Kombinationsfeld Dropdown-Schaltfläche mit dem aktuellen Windows-Design.  
  
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
|[in] `pDC`|Ein Zeiger zu einem Gerätekontext.|  
|[in] `rect`|Das umschließende Rechteck für das Kombinationsfeld Dropdown-Schaltfläche.|  
|[in] `bDisabled`|Gibt an, ob die Kombinationsfeld Dropdown-Schaltfläche deaktiviert ist.|  
|[in] `bIsDropped`|Gibt an, ob die Kombinationsfeld Dropdown-Schaltfläche geklickt wird.|  
|[in] `bIsHighlighted`|Gibt an, ob die Dropdownschaltfläche des Kombinationsfelds markiert wird.|  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Design-API aktiviert ist. andernfalls `FALSE`.  
  
##  <a name="drawpushbutton"></a>CMFCBaseVisualManager::DrawPushButton  
 Zeichnet eine Schaltfläche mit dem aktuellen Windows-Design.  
  
```  
virtual BOOL DrawPushButton(
    CDC* pDC,   
    CRect rect,   
    CMFCButton* pButton,   
    UINT uiState);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `rect`  
 Das umschließende Rechteck von der Schaltfläche.  
  
 [in] `pButton`  
 Ein Zeiger auf die [CMFCButton Klasse](../../mfc/reference/cmfcbutton-class.md) zu zeichnenden Objekt.  
  
 [in] `uiState`  
 Ignoriert. Der Status stammt aus `pButton`.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Design-API aktiviert ist. andernfalls `FALSE`.  
  
##  <a name="drawradiobutton"></a>CMFCBaseVisualManager::DrawRadioButton  
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
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `rect`  
 Das umschließende Rechteck des Optionsfelds.  
  
 [in] `bHighlighted`  
 Gibt an, ob das Optionsfeld markiert wird.  
  
 [in] `bChecked`  
 Gibt an, ob das Optionsfeld aktiviert ist.  
  
 [in] `bEnabled`  
 Gibt an, ob das Optionsfeld aktiviert ist.  
  
 [in] `bPressed`  
 Gibt an, ob die Schaltfläche gedrückt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Design-API aktiviert ist. andernfalls `FALSE`.  
  
##  <a name="drawstatusbarprogress"></a>CMFCBaseVisualManager::DrawStatusBarProgress  
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
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `pStatusBar`  
 Ein Zeiger auf die Statusleiste. Dieser Wert wird ignoriert.  
  
 [in] `rectProgress`  
 Das umschließende Rechteck der Statusanzeige in `pDC` Koordinaten.  
  
 [in] `nProgressTotal`  
 Der Gesamt-Wert.  
  
 [in] `nProgressCurr`  
 Der aktuelle Statuswert.  
  
 [in] `clrBar`  
 Die Farbe für den Anfang. `CMFCBaseVisualManager`ignoriert. Abgeleitete Klassen können sie für Farbverläufe verwenden.  
  
 [in] `clrProgressBarDest`  
 Die Endfarbe. `CMFCBaseVisualManager`ignoriert. Abgeleitete Klassen können sie für Farbverläufe verwenden.  
  
 [in] `clrProgressText`  
 Textfarbe ausgeführt. `CMFCBaseVisualManager`ignoriert. Die Farbe des Texts wird definiert, indem `afxGlobalData.clrBtnText`.  
  
 [in] `bProgressText`  
 Gibt an, ob der Text angezeigt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Design-API aktiviert ist. andernfalls `FALSE`.  
  
##  <a name="fillrebarpane"></a>CMFCBaseVisualManager::FillReBarPane  
 Füllt den Hintergrund des Grundleisten-Steuerelement mit der aktuellen Windows-Designs.  
  
```  
virtual void FillReBarPane(
    CDC* pDC,   
    CBasePane* pBar,   
    CRect rectClient);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `pBar`  
 Ein Zeiger auf einen Bereich, deren Hintergrund gezeichnet werden soll.  
  
 [in] `rectClient`  
 Das umschließende Rechteck des Bereichs, der ausgefüllt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Design-API aktiviert ist. andernfalls `FALSE`.  
  
##  <a name="getstandardwindowstheme"></a>CMFCBaseVisualManager::GetStandardWindowsTheme  
 Ruft das aktuelle Windows-Design ab.  
  
```  
virtual WinXpTheme GetStandardWindowsTheme();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die ausgewählte Windows-Design-Farbe. Dabei kann es sich um eine der folgenden Enumerationswerte sein:  
  
- `WinXpTheme_None`-Es gibt keine Designs aktiviert.  
  
- `WinXpTheme_NonStandard`-nicht Standarddesign ausgewählt ist (d. h., ein Design ausgewählt ist, aber keine aus der Liste unten).  
  
- `WinXpTheme_Blue`-Design "Blau" (Luna).  
  
- `WinXpTheme_Olive`-Olivenöl Design.  
  
- `WinXpTheme_Silver`-Silber-Design.  
  
##  <a name="updatesystemcolors"></a>CMFCBaseVisualManager::UpdateSystemColors  
 Aufrufe `OpenThemeData` zum Abrufen von Handles für die verschiedenen Steuerelemente zeichnen: Windows, Symbolleisten, Schaltflächen und So weiter.  
  
```  
void UpdateSystemColors();
```  
  
### <a name="remarks"></a>Hinweise  
 Nur für interne Verwendung.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)


---
title: CMFCBaseVisualManager Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: edb579cff639da9965c7214c2dd8abce8459d254
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcbasevisualmanager-class"></a>CMFCBaseVisualManager-Klasse
Eine Softwareebene zwischen abgeleiteten visuelle Manager und der Windows-Design-API.  
  
 `CMFCBaseVisualManager`Lädt UxTheme.dll, falls verfügbar, und verwaltet den Zugriff auf Windows-Design-API-Methoden.  
  
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
|[CMFCBaseVisualManager::DrawCheckBox](#drawcheckbox)|Zeichnet ein Kontrollkästchen-Steuerelement mit dem aktuellen Windows-Design an.|  
|[CMFCBaseVisualManager::DrawComboBorder](#drawcomboborder)|Zeichnet einen Rahmen Kombinationsfeld mit dem aktuellen Windows-Design an.|  
|[CMFCBaseVisualManager::DrawComboDropButton](#drawcombodropbutton)|Zeichnet eine Dropdown-kombinationsfeldschaltfläche mit dem aktuellen Windows-Design an.|  
|[CMFCBaseVisualManager::DrawPushButton](#drawpushbutton)|Zeichnet eine Schaltfläche mit dem aktuellen Windows-Design an.|  
|[CMFCBaseVisualManager::DrawRadioButton](#drawradiobutton)|Zeichnet ein Optionsfeld-Steuerelement mit dem aktuellen Windows-Design an.|  
|[CMFCBaseVisualManager::DrawStatusBarProgress](#drawstatusbarprogress)|Zeichnet eine Statusanzeige auf ein Statusleisten-Steuerelement ( [CMFCStatusBar-Klasse](../../mfc/reference/cmfcstatusbar-class.md)) mit dem aktuellen Windows-Design.|  
|[CMFCBaseVisualManager::FillReBarPane](#fillrebarpane)|Füllt den Hintergrund des Grundleisten-Steuerelement mit dem aktuellen Windows-Design an.|  
|[CMFCBaseVisualManager::GetStandardWindowsTheme](#getstandardwindowstheme)|Ruft das aktuelle Windows-Design ab.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|||  
|-|-|  
|Name|Beschreibung|  
|[CMFCBaseVisualManager::CleanUpThemes](#cleanupthemes)|Aufrufe `CloseThemeData` für alle Handles in abgerufenen `UpdateSystemColors`.|  
|[CMFCBaseVisualManager::UpdateSystemColors](#updatesystemcolors)|Aufrufe `OpenThemeData` zum Abrufen des Handles für das Zeichnen von verschiedenen Steuerelementen: Windows, Symbolleisten, Schaltflächen und So weiter.|  
  
## <a name="remarks"></a>Hinweise  
 Sie müssen keine Objekte dieser Klasse nicht direkt instanziieren.  
  
 Da es sich um eine Basisklasse für alle visuellen Manager handelt, können Sie nur aufrufen [CMFCVisualManager::GetInstance](../../mfc/reference/cmfcvisualmanager-class.md#getinstance), rufen Sie einen Zeiger auf den aktuellen Visual-Manager und Zugriff auf die Methoden für die `CMFCBaseVisualManager` mit diesen Zeiger. Wenn Sie ein Steuerelement anzeigen, indem Sie mit dem aktuellen Windows-Design müssen, es ist jedoch eher die Verwendung der `CMFCVisualManagerWindows` Schnittstelle.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCBaseVisualManager](../../mfc/reference/cmfcbasevisualmanager-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxvisualmanager.h  
  
##  <a name="cleanupthemes"></a>CMFCBaseVisualManager::CleanUpThemes  
 Aufrufe `CloseThemeData` für alle Handles in abgerufenen `UpdateSystemColors`.  
  
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
 Zeichnet ein Kontrollkästchen-Steuerelement mit dem aktuellen Windows-Design an.  
  
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
 Ein Zeiger zu einem Gerätekontext  
  
 [in] `rect`  
 Das umschließende Rechteck des Kontrollkästchens.  
  
 [in] `bHighlighted`  
 Gibt an, ob das Kontrollkästchen hervorgehoben ist.  
  
 [in] `nState`  
 0 für deaktiviert wurde, 1 für aktivierte Normal  
  
 2 für gemischte Normal.  
  
 [in] `bEnabled`  
 Gibt an, ob das Kontrollkästchen aktiviert ist.  
  
 [in] `bPressed`  
 Gibt an, ob das Kontrollkästchen gedrückt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn Design-API aktiviert ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Die Werte der `nState` die folgenden Kontrollkästchen-Stile entsprechen.  
  
|nState|Kontrollkästchen-Stil|  
|------------|---------------------|  
|0|CBS_UNCHECKEDNORMAL|  
|1|CBS_CHECKEDNORMAL|  
|2|CBS_MIXEDNORMAL|  
  
##  <a name="drawcomboborder"></a>CMFCBaseVisualManager::DrawComboBorder  
 Zeichnet den Rahmen des Kombinationsfelds mit dem aktuellen Windows-Design an.  
  
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
 Das umgebende Rechteck für den Rahmen des Kombinationsfelds.  
  
 [in] `bDisabled`  
 Gibt an, ob der Rahmen des Kombinationsfelds deaktiviert ist.  
  
 [in] `bIsDropped`  
 Gibt an, ob das Kombinationsfeld Rahmen unten gelöscht wird.  
  
 [in] `bIsHighlighted`  
 Gibt an, ob der Rahmen des Kombinationsfelds markiert ist.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn Design-API aktiviert ist; andernfalls `FALSE`.  
  
##  <a name="drawcombodropbutton"></a>CMFCBaseVisualManager::DrawComboDropButton  
 Zeichnet eine Dropdown-kombinationsfeldschaltfläche mit dem aktuellen Windows-Design an.  
  
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
|[in] `rect`|Das umschließende Rechteck der Dropdownschaltfläche des Kombinationsfelds.|  
|[in] `bDisabled`|Gibt an, ob der Dropdown-kombinationsfeldschaltfläche deaktiviert ist.|  
|[in] `bIsDropped`|Gibt an, ob der Dropdown-kombinationsfeldschaltfläche, nach unten gelöscht wird.|  
|[in] `bIsHighlighted`|Gibt an, ob die Dropdownschaltfläche des Kombinationsfelds markiert ist.|  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn Design-API aktiviert ist; andernfalls `FALSE`.  
  
##  <a name="drawpushbutton"></a>CMFCBaseVisualManager::DrawPushButton  
 Zeichnet eine Schaltfläche mit dem aktuellen Windows-Design an.  
  
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
 Das umschließende Rechteck der Push-Schaltfläche.  
  
 [in] `pButton`  
 Ein Zeiger auf die [CMFCButton Klasse](../../mfc/reference/cmfcbutton-class.md) Objekt gezeichnet werden soll.  
  
 [in] `uiState`  
 Ignoriert. Der Status entnommen `pButton`.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn Design-API aktiviert ist; andernfalls `FALSE`.  
  
##  <a name="drawradiobutton"></a>CMFCBaseVisualManager::DrawRadioButton  
 Zeichnet ein Optionsfeld-Steuerelement mit dem aktuellen Windows-Design an.  
  
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
 Gibt an, ob das Optionsfeld markiert ist.  
  
 [in] `bChecked`  
 Gibt an, ob das Optionsfeld aktiviert ist.  
  
 [in] `bEnabled`  
 Gibt an, ob das Optionsfeld aktiviert ist.  
  
 [in] `bPressed`  
 Gibt an, ob das Optionsfeld gedrückt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn Design-API aktiviert ist; andernfalls `FALSE`.  
  
##  <a name="drawstatusbarprogress"></a>CMFCBaseVisualManager::DrawStatusBarProgress  
 Zeichnet Statusanzeige auf StatusBar-Steuerelement ( [CMFCStatusBar-Klasse](../../mfc/reference/cmfcstatusbar-class.md)) mit dem aktuellen Windows-Design.  
  
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
 Ein Zeiger auf der Statusleiste. Dieser Wert wird ignoriert.  
  
 [in] `rectProgress`  
 Das umschließende Rechteck der Statusanzeige im `pDC` Koordinaten.  
  
 [in] `nProgressTotal`  
 Der Wert des Gesamtstatus.  
  
 [in] `nProgressCurr`  
 Der aktuelle Statuswert.  
  
 [in] `clrBar`  
 Die Startfarbe. `CMFCBaseVisualManager`ignoriert. Abgeleitete Klassen können sie für Farbverläufe.  
  
 [in] `clrProgressBarDest`  
 Die Endfarbe. `CMFCBaseVisualManager`ignoriert. Abgeleitete Klassen können sie für Farbverläufe.  
  
 [in] `clrProgressText`  
 Textfarbe ausgeführt. `CMFCBaseVisualManager`ignoriert. Die Textfarbe wird definiert, indem `afxGlobalData.clrBtnText`.  
  
 [in] `bProgressText`  
 Gibt an, ob der Text angezeigt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn Design-API aktiviert ist; andernfalls `FALSE`.  
  
##  <a name="fillrebarpane"></a>CMFCBaseVisualManager::FillReBarPane  
 Füllt den Hintergrund des Grundleisten-Steuerelement mit dem aktuellen Windows-Design an.  
  
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
 Ein Zeiger auf einen Bereich, dessen Hintergrund gezeichnet werden soll.  
  
 [in] `rectClient`  
 Das umschließende Rechteck des Bereichs gefüllt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn Design-API aktiviert ist; andernfalls `FALSE`.  
  
##  <a name="getstandardwindowstheme"></a>CMFCBaseVisualManager::GetStandardWindowsTheme  
 Ruft das aktuelle Windows-Design ab.  
  
```  
virtual WinXpTheme GetStandardWindowsTheme();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die aktuell ausgewählte Windows-Design-Farbe. Die folgenden Enumerationswerte sind möglich:  
  
- `WinXpTheme_None`-Es ist kein Design aktiviert.  
  
- `WinXpTheme_NonStandard`-Design "nicht dem standard" aktiviert ist (d. h., ein Design ausgewählt ist, aber keine aus der Liste unten).  
  
- `WinXpTheme_Blue`-Design "Blau" (Luna).  
  
- `WinXpTheme_Olive`-Olivenöl Design.  
  
- `WinXpTheme_Silver`-Design "Silber".  
  
##  <a name="updatesystemcolors"></a>CMFCBaseVisualManager::UpdateSystemColors  
 Aufrufe `OpenThemeData` zum Abrufen des Handles für das Zeichnen von verschiedenen Steuerelementen: Windows, Symbolleisten, Schaltflächen und So weiter.  
  
```  
void UpdateSystemColors();
```  
  
### <a name="remarks"></a>Hinweise  
 Nur für interne Verwendung.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)

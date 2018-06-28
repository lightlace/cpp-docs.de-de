---
title: CMFCPopupMenuBar-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: aede6e3224149bd237ca2bb830370718105e1f83
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2018
ms.locfileid: "37037754"
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
|[CMFCPopupMenuBar::BuildOrigItems](#buildorigitems)|Popup-Menüelemente aus einer angegebenen Menüressource geladen.|  
|[CMFCPopupMenuBar::CloseDelayedSubMenu](#closedelayedsubmenu)|Schließt eine Menüschaltfläche verzögerte Popupfenster an.|  
|[CMFCPopupMenuBar::ExportToMenu](#exporttomenu)|Erstellt ein Menü das Popupmenü Schaltflächen.|  
|[CMFCPopupMenuBar::FindDestintationToolBar](#finddestintationtoolbar)|Sucht die Symbolleiste, in ein angegebenen Punkt befindet.|  
|[CMFCPopupMenuBar::GetCurrentMenuImageSize](#getcurrentmenuimagesize)|Gibt die Größe der Menüschaltfläche des Images an.|  
|[CMFCPopupMenuBar::GetDefaultMenuId](#getdefaultmenuid)|Gibt den Bezeichner des Menüelements Standardwert zurück.|  
|[CMFCPopupMenuBar::GetLastCommandIndex](#getlastcommandindex)|Ruft den Index des zuletzt aufgerufenen Menübefehls ab.|  
|[CMFCPopupMenuBar::GetOffset](#getoffset)|Ruft das Zeilenoffset der Popup-Menüleiste ab.|  
|[CMFCPopupMenuBar::ImportFromMenu](#importfrommenu)|Importiert Popup-Schaltflächen in einem angegebenen Menü an.|  
|[CMFCPopupMenuBar::IsDropDownListMode](#isdropdownlistmode)|Gibt an, ob die Menüleiste Popup im Dropdown-Listenfeld-Modus befindet.|  
|[CMFCPopupMenuBar::IsPaletteMode](#ispalettemode)|Gibt an, ob die Menüleiste Popup im Palettenmodus befindet.|  
|[CMFCPopupMenuBar::IsRibbonPanel](#isribbonpanel)|Gibt an, ob dies ein Menübandbereich ist ( `FALSE` standardmäßig).|  
|[CMFCPopupMenuBar::IsRibbonPanelInRegularMode](#isribbonpanelinregularmode)|Gibt an, ob dies ein Menübandbereich im normalen Modus ist ( `FALSE` standardmäßig).|  
|[CMFCPopupMenuBar::LoadFromHash](#loadfromhash)|Lädt eine archivierte Menü an.|  
|[CMFCPopupMenuBar::RestoreDelayedSubMenu](#restoredelayedsubmenu)|Stellt eine verzögerte Menüschaltfläche für das Schließen der Popup-Menüleiste.|  
|[CMFCPopupMenuBar::SetButtonStyle](#setbuttonstyle)|Legt den Stil der Symbolleisten-Schaltfläche am angegebenen Index fest. (Überschreibt [CMFCToolBar::SetButtonStyle](../../mfc/reference/cmfctoolbar-class.md#setbuttonstyle).)|  
|[CMFCPopupMenuBar::SetOffset](#setoffset)|Legt das Zeilenoffset der Popup-Menüleiste fest.|  
|[CMFCPopupMenuBar::StartPopupMenuTimer](#startpopupmenutimer)|Startet den Timer für eine angegebene verzögerte Popup-Menüschaltfläche.|  
  
### <a name="data-members"></a>Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[CMFCPopupMenuBar::m_bDisableSideBarInXPMode](#m_bdisablesidebarinxpmode)|Gibt an, ob die graue Randleiste angezeigt wird, wenn die Anwendung eine Windows XP-Darstellung hat.|  
  
## <a name="remarks"></a>Hinweise  
 Die `CMFCPopupMenuBar` wird erstellt, zur gleichen Zeit wie eine [CMFCPopupMenu Klasse](../../mfc/reference/cmfcpopupmenu-class.md) und darin eingebettet. Die `CMFCPopupMenuBar` deckt den gesamten Clientbereich der `CMFCPopupMenu` Objekt. Es unterstützt Tastatur- und Mauseingaben. Kommuniziert auch, dass die Eingabe die `CMFCPopupMenu` und an das Rahmenfenster der obersten Ebene.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie zum Initialisieren einer `CMFCPopupMenuBar` -Objekt aus einem `CMFCPopupMenu` Objekt. Dieser Codeausschnitt ist Teil des [Draw Client-Beispiels](../../visual-cpp-samples.md).  
  
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
 Sofort berechnet das Layout der Leistenbereich das Popup-Menü aus. (Überschreibt [CPane::AdjustSizeImmediate](../../mfc/reference/cpane-class.md#adjustsizeimmediate).  
  
```  
virtual void AdjustSizeImmediate(BOOL bRecalcLayout);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *bRecalcLayout*  
 `TRUE` Das Layout der Popup-Menü-Leistenbereich automatisch neu berechnet; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="buildorigitems"></a>  CMFCPopupMenuBar::BuildOrigItems  
 Popup-Menüelemente aus einer angegebenen Menüressource geladen.  
  
```  
BOOL BuildOrigItems(UINT uiMenuResID);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *UiMenuResID*  
 Gibt die im Menü-ID für die Menüressource laden.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `TRUE` im Erfolgsfall oder `FALSE` Wenn dies nicht.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="closedelayedsubmenu"></a>  CMFCPopupMenuBar::CloseDelayedSubMenu  
 Wird eine Popup-Menüschaltfläche, die verzögert wurde geschlossen.  
  
```  
virtual void CloseDelayedSubMenu();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="exporttomenu"></a>  CMFCPopupMenuBar::ExportToMenu  
 Erstellt ein Menü über die Schaltflächen der Popup-Menü.  
  
```  
virtual HMENU ExportToMenu() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt ein Handle für das neue Menü zurück.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="finddestintationtoolbar"></a>  CMFCPopupMenuBar::FindDestintationToolBar  
 Sucht die Symbolleiste, in ein angegebenen Punkt befindet.  
  
```  
CMFCToolBar* FindDestintationToolBar(CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *zeigen*  
 Einen Punkt auf dem Bildschirm.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt ein Handle für die Symbolleiste, wo liegt der Punkt, wenn Therei ist, oder `NULL` Wenn dies nicht.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getcurrentmenuimagesize"></a>  CMFCPopupMenuBar::GetCurrentMenuImageSize  
 Gibt die Größe der Menüschaltfläche des Images an.  
  
```  
virtual CSize GetCurrentMenuImageSize() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Größe der Bilder Menüschaltfläche auf der Symbolleiste.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getdefaultmenuid"></a>  CMFCPopupMenuBar::GetDefaultMenuId  
 Gibt den Bezeichner des Menüelements Standardwert zurück.  
  
```  
UINT GetDefaultMenuId() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Bezeichner des Menüelements standardmäßig in der Popup-Menüleiste zurück.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getlastcommandindex"></a>  CMFCPopupMenuBar::GetLastCommandIndex  
 Ruft den Index des zuletzt aufgerufenen Menübefehls ab.  
  
```  
static int __stdcall GetLastCommandIndex();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Index des letzten Menübefehls, das aufgerufen wurde.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getoffset"></a>  CMFCPopupMenuBar::GetOffset  
 Ruft das Zeilenoffset der Popup-Menüleiste ab.  
  
```  
int GetOffset() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Zeilenoffset der Popup-Menüleiste.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wert wird festgelegt, mit [CMFCPopupMenuBar::SetOffset](#setoffset).  
  
##  <a name="importfrommenu"></a>  CMFCPopupMenuBar::ImportFromMenu  
 Importiert Popup-Schaltflächen in einem angegebenen Menü an.  
  
```  
virtual BOOL ImportFromMenu(
    HMENU hMenu,  
    BOOL bShowAllCommands = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *hMenu*  
 Klicken Sie im Menü aus der Popup-Menüschaltflächen importiert.  
  
 [in] *bShowAllCommands*  
 `TRUE` Wenn alle Befehle in diesem Menü sind importiert werden, oder `FALSE` Wenn selten verwendeten ausgeblendet werden können.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `TRUE` Wenn Menüschaltflächen Menü, erfolgreich importiert wurden oder `FALSE` Wenn dies nicht.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isdropdownlistmode"></a>  CMFCPopupMenuBar::IsDropDownListMode  
 Gibt an, ob die Menüleiste Popup im Dropdown-Listenfeld-Modus befindet.  
  
```  
BOOL IsDropDownListMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `TRUE` im Dropdown-Listenfeld-Modus ist der Popup-Menüleiste oder `FALSE` Wenn dies nicht.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ispalettemode"></a>  CMFCPopupMenuBar::IsPaletteMode  
 Gibt an, ob die Menüleiste Popup im Palettenmodus befindet.  
  
```  
BOOL IsPaletteMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `TRUE` Palettenmodus aktiviert ist, oder `FALSE` Wenn dies nicht.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Menüleiste auf Palettenmodus festgelegt ist, werden die Menüelemente in mehreren Spalten und eine begrenzte Anzahl von Zeilen angezeigt.  
  
##  <a name="isribbonpanel"></a>  CMFCPopupMenuBar::IsRibbonPanel  
 Gibt an, ob dies ein Menübandbereich ist ( `FALSE` standardmäßig).  
  
```  
virtual BOOL IsRibbonPanel() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `FALSE` Standardmäßig gibt an, dass es sich nicht um ein Menübandbereich handelt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isribbonpanelinregularmode"></a>  CMFCPopupMenuBar::IsRibbonPanelInRegularMode  
 Gibt an, ob dies ein Menübandbereich im normalen Modus ist ( `FALSE` standardmäßig).  
  
```  
virtual BOOL IsRibbonPanelInRegularMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `FALSE` Standardmäßig gibt an, dass dies ein Menübandbereich nicht im regulären Modus befindet.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="loadfromhash"></a>  CMFCPopupMenuBar::LoadFromHash  
 Lädt eine archivierte Menü an.  
  
```  
BOOL LoadFromHash(HMENU hMenu);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *hMenu*  
 Ein Handle für das archivierte Menü zu laden.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `TRUE` Wenn erfolgreich, klicken Sie im Menü geladen wird oder `FALSE` Wenn dies nicht.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="m_bdisablesidebarinxpmode"></a>  CMFCPopupMenuBar::m_bDisableSideBarInXPMode  
 Ein boolescher Parameter, der angibt, ob die Anwendung eine graue Randleiste verfügt, wenn es sich um ein Windows XP-Darstellung hat.  
  
```  
BOOL m_bDisableSideBarInXPMode;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn diese Membervariable, um festgelegt ist `FALSE` und Ihre Anwendung hat eine Darstellung von Windows XP, das Framework zeichnet eine graue Randleiste in Ihrer Anwendung.  
  
 Der Standardwert ist `FALSE`.  
  
##  <a name="restoredelayedsubmenu"></a>  CMFCPopupMenuBar::RestoreDelayedSubMenu  
 Stellt eine verzögerte Menüschaltfläche für das Schließen der Popup-Menüleiste.  
  
```  
virtual void RestoreDelayedSubMenu();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setbuttonstyle"></a>  CMFCPopupMenuBar::SetButtonStyle  
 Legt den Stil der Symbolleisten-Schaltfläche am angegebenen Index fest. (Überschreibt [CMFCToolBar::SetButtonStyle](../../mfc/reference/cmfctoolbar-class.md#setbuttonstyle).)  
  
```  
virtual void SetButtonStyle(
    int nIndex,  
    UINT nStyle);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *nIndex*  
 Der nullbasierte Index der Symbolleisten-Schaltfläche, dessen Format ist, festgelegt werden.  
  
 [in] *nStyle*  
 Die Art der Schaltfläche. Finden Sie unter [Steuerelementtypen für die Symbolleiste](../../mfc/reference/toolbar-control-styles.md) für die Liste der Formatvorlagen für Symbolleistenschaltflächen verfügbar.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setoffset"></a>  CMFCPopupMenuBar::SetOffset  
 Legt das Zeilenoffset der Popup-Menüleiste fest.  
  
```  
void SetOffset(int iOffset);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *iOffset*  
 Die Anzahl der Zeilen an, die die Popup-Menüleiste versetzt werden sollen.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="startpopupmenutimer"></a>  CMFCPopupMenuBar::StartPopupMenuTimer  
 Startet den Timer für eine angegebene verzögerte Popup-Menüschaltfläche.  
  
```  
void StartPopupMenuTimer(
    CMFCToolBarMenuButton* pMenuButton,  
    int nDelayFactor = 1);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pMenuButton*  
 Ein Zeiger auf die Menüschaltfläche, für die den Zeitgeber Verzögerung festgelegt.  
  
 [in] *nDelayFactor*  
 Eine Verzögerung der Faktor, gleich mindestens eins mit Standardmenü, um die Verzögerung (in der Regel zwischen einer halben Sekunde und fünf Sekunden) multipliziert.  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCColorBar-Klasse](../../mfc/reference/cmfccolorbar-class.md)   
 [CMFCPopupMenu-Klasse](../../mfc/reference/cmfcpopupmenu-class.md)

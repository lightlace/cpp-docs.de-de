---
title: Klasse CMFCPopupMenuBar | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCPopupMenuBar
dev_langs:
- C++
helpviewer_keywords:
- CMFCPopupMenuBar class
ms.assetid: 4c93c459-7f70-4240-8c63-280bb811e374
caps.latest.revision: 32
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 46f86035fecc16c45e01a1c70cdde610093d377b
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcpopupmenubar-class"></a>CMFCPopupMenuBar-Klasse
Eine Menüleiste, die in einem Popupmenü eingebettet ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCPopupMenuBar : public CMFCToolBar  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCPopupMenuBar::AdjustSizeImmediate](#adjustsizeimmediate)|Sofort neu berechnet das Layout eines Bereichs ein. (Überschreibt [CPane::AdjustSizeImmediate](../../mfc/reference/cpane-class.md#adjustsizeimmediate).)|  
|[CMFCPopupMenuBar::BuildOrigItems](#buildorigitems)|Lädt Popupmenüelemente aus einer angegebenen Ressource.|  
|[CMFCPopupMenuBar::CloseDelayedSubMenu](#closedelayedsubmenu)|Schließt eine verzögerte Popup-Schaltfläche.|  
|[CMFCPopupMenuBar::ExportToMenu](#exporttomenu)|Erstellt ein Menü, über die Schaltflächen im Popup-Menü.|  
|[CMFCPopupMenuBar::FindDestintationToolBar](#finddestintationtoolbar)|Sucht die Symbolleiste, in ein angegebenen Punkt befindet.|  
|[CMFCPopupMenuBar::GetCurrentMenuImageSize](#getcurrentmenuimagesize)|Gibt die Größe der Schaltfläche Images.|  
|[CMFCPopupMenuBar::GetDefaultMenuId](#getdefaultmenuid)|Gibt den Bezeichner des Menüelements Standardwert zurück.|  
|[CMFCPopupMenuBar::GetLastCommandIndex](#getlastcommandindex)|Ruft den Index der zuletzt aufgerufenen Menübefehl ab.|  
|[CMFCPopupMenuBar::GetOffset](#getoffset)|Ruft den Zeilenoffset der Popup-Menüleiste ab.|  
|[CMFCPopupMenuBar::ImportFromMenu](#importfrommenu)|Importiert Popup-Schaltflächen in einem angegebenen Menü.|  
|[CMFCPopupMenuBar::IsDropDownListMode](#isdropdownlistmode)|Gibt an, ob die Popup-Menüleiste im Dropdown-Listenfeld Modus ist.|  
|[CMFCPopupMenuBar::IsPaletteMode](#ispalettemode)|Gibt an, ob die Popup-Menüleiste in der Palettenmodus ist.|  
|[CMFCPopupMenuBar::IsRibbonPanel](#isribbonpanel)|Gibt an, ob dies ein Menübandbereich ( `FALSE` standardmäßig).|  
|[CMFCPopupMenuBar::IsRibbonPanelInRegularMode](#isribbonpanelinregularmode)|Gibt an, ob dies ein Menübandbereich im normalen Modus ( `FALSE` standardmäßig).|  
|[CMFCPopupMenuBar::LoadFromHash](#loadfromhash)|Lädt eine archivierte Menü.|  
|[CMFCPopupMenuBar::RestoreDelayedSubMenu](#restoredelayedsubmenu)|Stellt eine verzögerte Menüschaltfläche für das Schließen der Popup-Menüleiste.|  
|[CMFCPopupMenuBar::SetButtonStyle](#setbuttonstyle)|Legt den Stil der Symbolleisten-Schaltfläche am angegebenen Index fest. (Überschreibt [CMFCToolBar::SetButtonStyle](../../mfc/reference/cmfctoolbar-class.md#setbuttonstyle).)|  
|[CMFCPopupMenuBar::SetOffset](#setoffset)|Legt den Zeilenoffset der Popup-Menüleiste fest.|  
|[CMFCPopupMenuBar::StartPopupMenuTimer](#startpopupmenutimer)|Startet den Zeitgeber für eine angegebene verzögerte Popup-Schaltfläche.|  
  
### <a name="data-members"></a>Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCPopupMenuBar::m_bDisableSideBarInXPMode](#m_bdisablesidebarinxpmode)|Gibt an, ob die graue Randleiste angezeigt wird, wenn die Anwendung den Stil von Windows XP verfügt.|  
  
## <a name="remarks"></a>Hinweise  
 Die `CMFCPopupMenuBar` wird erstellt, zur gleichen Zeit wie eine [CMFCPopupMenu Klasse](../../mfc/reference/cmfcpopupmenu-class.md) und darin eingebettet. Die `CMFCPopupMenuBar` deckt den gesamten Clientbereich von der `CMFCPopupMenu` Objekt. Tastatur- und Mauseingaben unterstützt. Kommuniziert es auch, dass die Eingabe auf die `CMFCPopupMenu` und an das Rahmenfenster der obersten Ebene.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie zum Initialisieren einer `CMFCPopupMenuBar` -Objekt aus einem `CMFCPopupMenu` Objekt. Dieser Codeausschnitt ist Teil der [zeichnen Clientbeispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DrawClient&#7;](../../mfc/reference/codesnippet/cpp/cmfcpopupmenubar-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxpopupmenubar.h  
  
##  <a name="a-nameadjustsizeimmediatea--cmfcpopupmenubaradjustsizeimmediate"></a><a name="adjustsizeimmediate"></a>CMFCPopupMenuBar::AdjustSizeImmediate  
 Sofort berechnet das Layout der Leistenbereich die Popup-Menü aus. (Überschreibt [CPane::AdjustSizeImmediate](../../mfc/reference/cpane-class.md#adjustsizeimmediate).  
  
```  
virtual void AdjustSizeImmediate(BOOL bRecalcLayout);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bRecalcLayout`  
 `TRUE`Das Layout der Popup-Menü-Leistenbereich automatisch neu berechnet; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namebuildorigitemsa--cmfcpopupmenubarbuildorigitems"></a><a name="buildorigitems"></a>CMFCPopupMenuBar::BuildOrigItems  
 Lädt Popupmenüelemente aus einer angegebenen Ressource.  
  
```  
BOOL BuildOrigItems(UINT uiMenuResID);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiMenuResID`  
 Gibt die ID der Menüressource im geladen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `TRUE` im Erfolgsfall oder `FALSE` ist dies nicht.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameclosedelayedsubmenua--cmfcpopupmenubarclosedelayedsubmenu"></a><a name="closedelayedsubmenu"></a>CMFCPopupMenuBar::CloseDelayedSubMenu  
 Schließt eine Popup-Menüschaltfläche, die verspätet ist.  
  
```  
virtual void CloseDelayedSubMenu();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameexporttomenua--cmfcpopupmenubarexporttomenu"></a><a name="exporttomenu"></a>CMFCPopupMenuBar::ExportToMenu  
 Erstellt ein Menü, über die Schaltflächen der Popup-Menü.  
  
```  
virtual HMENU ExportToMenu() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt ein Handle auf das neue Menü.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namefinddestintationtoolbara--cmfcpopupmenubarfinddestintationtoolbar"></a><a name="finddestintationtoolbar"></a>CMFCPopupMenuBar::FindDestintationToolBar  
 Sucht die Symbolleiste, in ein angegebenen Punkt befindet.  
  
```  
CMFCToolBar* FindDestintationToolBar(CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `point`  
 Ein Punkt auf dem Bildschirm.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt ein Handle für die Symbolleiste, liegt der Punkt, sofern Therei, oder `NULL` ist dies nicht.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetcurrentmenuimagesizea--cmfcpopupmenubargetcurrentmenuimagesize"></a><a name="getcurrentmenuimagesize"></a>CMFCPopupMenuBar::GetCurrentMenuImageSize  
 Gibt die Größe der Schaltfläche Images.  
  
```  
virtual CSize GetCurrentMenuImageSize() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Größe der Schaltfläche Images in der Symbolleiste.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetdefaultmenuida--cmfcpopupmenubargetdefaultmenuid"></a><a name="getdefaultmenuid"></a>CMFCPopupMenuBar::GetDefaultMenuId  
 Gibt den Bezeichner des Menüelements Standardwert zurück.  
  
```  
UINT GetDefaultMenuId() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Bezeichner des Menüelements standardmäßig in der Popup-Menüleiste zurück.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetlastcommandindexa--cmfcpopupmenubargetlastcommandindex"></a><a name="getlastcommandindex"></a>CMFCPopupMenuBar::GetLastCommandIndex  
 Ruft den Index der zuletzt aufgerufenen Menübefehl ab.  
  
```  
static int __stdcall GetLastCommandIndex();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Index des letzten Menübefehls im, das aufgerufen wurde.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetoffseta--cmfcpopupmenubargetoffset"></a><a name="getoffset"></a>CMFCPopupMenuBar::GetOffset  
 Ruft den Zeilenoffset der Popup-Menüleiste ab.  
  
```  
int GetOffset() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Zeilenoffset der Popup-Menüleiste zurück.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wert wird festgelegt, mit [CMFCPopupMenuBar::SetOffset](#setoffset).  
  
##  <a name="a-nameimportfrommenua--cmfcpopupmenubarimportfrommenu"></a><a name="importfrommenu"></a>CMFCPopupMenuBar::ImportFromMenu  
 Importiert Popup-Schaltflächen in einem angegebenen Menü.  
  
```  
virtual BOOL ImportFromMenu(
    HMENU hMenu,  
    BOOL bShowAllCommands = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `hMenu`  
 Klicken Sie im Menü aus dem Popup-Menüschaltflächen importiert.  
  
 [in] `bShowAllCommands`  
 `TRUE`Wenn alle Befehle im Menü sollen importiert werden, oder `FALSE` Wenn selten verwendeten ausgeblendet werden können.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `TRUE` Wenn Menüschaltflächen Menü importiert wurden oder `FALSE` ist dies nicht.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameisdropdownlistmodea--cmfcpopupmenubarisdropdownlistmode"></a><a name="isdropdownlistmode"></a>CMFCPopupMenuBar::IsDropDownListMode  
 Gibt an, ob die Popup-Menüleiste im Dropdown-Listenfeld Modus ist.  
  
```  
BOOL IsDropDownListMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `TRUE` im Dropdown-Listenfeld-Modus ist die Popup-Menüleiste oder `FALSE` ist dies nicht.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameispalettemodea--cmfcpopupmenubarispalettemode"></a><a name="ispalettemode"></a>CMFCPopupMenuBar::IsPaletteMode  
 Gibt an, ob die Popup-Menüleiste in der Palettenmodus ist.  
  
```  
BOOL IsPaletteMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `TRUE` Palettenmodus aktiviert ist, oder `FALSE` ist dies nicht.  
  
### <a name="remarks"></a>Hinweise  
 Bei die Menüleiste auf die Palettenmodus festgelegt ist, werden die Menüelemente in mehreren Spalten und eine begrenzte Anzahl von Zeilen angezeigt.  
  
##  <a name="a-nameisribbonpanela--cmfcpopupmenubarisribbonpanel"></a><a name="isribbonpanel"></a>CMFCPopupMenuBar::IsRibbonPanel  
 Gibt an, ob dies ein Menübandbereich ( `FALSE` standardmäßig).  
  
```  
virtual BOOL IsRibbonPanel() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `FALSE` in der Standardeinstellung gibt an, dass es sich nicht um ein Menübandbereich handelt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameisribbonpanelinregularmodea--cmfcpopupmenubarisribbonpanelinregularmode"></a><a name="isribbonpanelinregularmode"></a>CMFCPopupMenuBar::IsRibbonPanelInRegularMode  
 Gibt an, ob dies ein Menübandbereich im normalen Modus ( `FALSE` standardmäßig).  
  
```  
virtual BOOL IsRibbonPanelInRegularMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `FALSE` in der Standardeinstellung gibt an, dass dies ein Menübandbereich nicht im normalen Modus ist.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameloadfromhasha--cmfcpopupmenubarloadfromhash"></a><a name="loadfromhash"></a>CMFCPopupMenuBar::LoadFromHash  
 Lädt eine archivierte Menü.  
  
```  
BOOL LoadFromHash(HMENU hMenu);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `hMenu`  
 Ein Handle für das archivierte Menü geladen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `TRUE` Wenn erfolgreich, klicken Sie im Menü geladen wird oder `FALSE` ist dies nicht.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namembdisablesidebarinxpmodea--cmfcpopupmenubarmbdisablesidebarinxpmode"></a><a name="m_bdisablesidebarinxpmode"></a>CMFCPopupMenuBar::m_bDisableSideBarInXPMode  
 Ein boolescher Parameter, der angibt, ob die Anwendung eine graue Randleiste verfügt, bei Windows XP darzustellen.  
  
```  
BOOL m_bDisableSideBarInXPMode;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn diese Membervariable, um festgelegt ist `FALSE` und Ihre Anwendung hat einen Stil von Windows XP, das Framework zeichnet eine graue Randleiste in Ihrer Anwendung.  
  
 Der Standardwert ist `FALSE`.  
  
##  <a name="a-namerestoredelayedsubmenua--cmfcpopupmenubarrestoredelayedsubmenu"></a><a name="restoredelayedsubmenu"></a>CMFCPopupMenuBar::RestoreDelayedSubMenu  
 Stellt eine verzögerte Menüschaltfläche für das Schließen der Popup-Menüleiste.  
  
```  
virtual void RestoreDelayedSubMenu();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namesetbuttonstylea--cmfcpopupmenubarsetbuttonstyle"></a><a name="setbuttonstyle"></a>CMFCPopupMenuBar::SetButtonStyle  
 Legt den Stil der Symbolleisten-Schaltfläche am angegebenen Index fest. (Überschreibt [CMFCToolBar::SetButtonStyle](../../mfc/reference/cmfctoolbar-class.md#setbuttonstyle).)  
  
```  
virtual void SetButtonStyle(
    int nIndex,  
    UINT nStyle);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nIndex`  
 Der nullbasierte Index der Symbolleisten-Schaltfläche, dessen Stil ist, festgelegt werden.  
  
 [in] `nStyle`  
 Der Stil der Schaltfläche. Finden Sie unter [Steuerelementtypen für die Symbolleiste](../../mfc/reference/toolbar-control-styles.md) für die Liste der verfügbaren Symbolleiste Schaltflächenstile.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namesetoffseta--cmfcpopupmenubarsetoffset"></a><a name="setoffset"></a>CMFCPopupMenuBar::SetOffset  
 Legt den Zeilenoffset der Popup-Menüleiste fest.  
  
```  
void SetOffset(int iOffset);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iOffset`  
 Die Anzahl der Zeilen, die Popup-Menüleiste versetzt werden soll.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namestartpopupmenutimera--cmfcpopupmenubarstartpopupmenutimer"></a><a name="startpopupmenutimer"></a>CMFCPopupMenuBar::StartPopupMenuTimer  
 Startet den Zeitgeber für eine angegebene verzögerte Popup-Schaltfläche.  
  
```  
void StartPopupMenuTimer(
    CMFCToolBarMenuButton* pMenuButton,  
    int nDelayFactor = 1);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pMenuButton`  
 Ein Zeiger auf die Schaltfläche für den Timer für die Verzögerung einstellen.  
  
 [in] `nDelayFactor`  
 Verzögerung der Faktor, mindestens ein Standardmenü, um die Verzögerung (in der Regel zwischen einer halben Sekunde und fünf Sekunden) multiplizieren gleich.  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCColorBar-Klasse](../../mfc/reference/cmfccolorbar-class.md)   
 [CMFCPopupMenu-Klasse](../../mfc/reference/cmfcpopupmenu-class.md)


---
title: Klasse CMFCVisualManagerWindows7 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- afxvisualmanagerwindows7/CMFCVisualManagerWindows7
- CMFCVisualManagerWindows7
dev_langs:
- C++
helpviewer_keywords:
- CMFCVisualManagerWindows7 class
ms.assetid: e8d87df1-0c09-4b58-8ade-4e911f796e42
caps.latest.revision: 21
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
ms.openlocfilehash: 236223fe371973fb4e009d2fcb242f2ed6e90963
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcvisualmanagerwindows7-class"></a>CMFCVisualManagerWindows7-Klasse
Die `CMFCVisualManagerWindows7` wendet einer Anwendung die Darstellung einer [!INCLUDE[win7](../../build/includes/win7_md.md)] Anwendung.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCVisualManagerWindows7 : public CMFCVisualManagerWindows;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCVisualManagerWindows7::CMFCVisualManagerWindows7](#cmfcvisualmanagerwindows7)|Standardkonstruktor|  
|[CMFCVisualManagerWindows7:: ~ CMFCVisualManagerWindows7](#cmfcvisualmanagerwindows7__~cmfcvisualmanagerwindows7)|Standarddestruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`CMFCVisualManagerWindows7::CleanStyle`|Löscht den aktuellen visuellen Stil, und setzt den standardmäßigen visuellen Stil.|  
|`CMFCVisualManagerWindows7::CleanUp`|Löscht alle Objekte in der Benutzeroberfläche, und setzt die Menüs.|  
|`CMFCVisualManagerWindows7::DrawNcBtn`|Zeichnet eine Schaltfläche in der nicht-Clientbereich im Frame. Das Framework verwendet diese Methode zum Zeichnen zu minimieren, maximieren, schließen und Schaltflächen in der oberen rechten Ecke des Fensterrahmens wiederherstellen. Diese Methode wird nicht aufgerufen, wenn das Programm nicht Aero-Design verwendet.|  
|`CMFCVisualManagerWindows7::DrawNcText`|Zeichnet Text in den nicht-Clientbereich im Frame. Das Framework verwendet diese Methode zum Zeichnen der Titel der Anwendung in der Titelleiste am oberen Rand des Rahmenfensters.|  
|`CMFCVisualManagerWindows7::DrawSeparator`|Zeichnet eine Trennzeichen auf der [CMFCToolBar Klasse](../../mfc/reference/cmfctoolbar-class.md).|  
|`CMFCVisualManagerWindows7::GetRibbonBar`|Ruft die [CMFCRibbonBar Class](../../mfc/reference/cmfcribbonbar-class.md) der Benutzeroberfläche zugeordnet.|  
|[CMFCVisualManagerWindows7::GetRibbonEditBackgroundColor](#getribboneditbackgroundcolor)|Ruft die Hintergrundfarbe eines Menübands bearbeiten.|  
|`CMFCVisualManagerWindows7::GetRibbonPopupBorderSize`|Überschreibt [CMFCVisualManager::GetRibbonPopupBorderSize](../../mfc/reference/cmfcvisualmanager-class.md#getribbonpopupbordersize)|  
|`CMFCVisualManagerWindows7::GetRibbonQuickAccessToolBarChevronOffset`|Überschreibt [CMFCVisualManager::GetRibbonQuickAccessToolBarChevronOffset](../../mfc/reference/cmfcvisualmanager-class.md#getribbonquickaccesstoolbarchevronoffset)|  
|`CMFCVisualManagerWindows7::GetRibbonQuickAccessToolBarRightMargin`|Überschreibt [CMFCVisualManager::GetRibbonQuickAccessToolBarRightMargin](../../mfc/reference/cmfcvisualmanager-class.md#getribbonquickaccesstoolbarrightmargin)|  
|`CMFCVisualManagerWindows7::IsHighlightWholeMenuItem`|Überschreibt [CMFCVisualManagerWindows::IsHighlightWholeMenuItem](../../mfc/reference/cmfcvisualmanagerwindows-class.md#ishighlightwholemenuitem)|  
|`CMFCVisualManagerWindows7::IsOwnerDrawMenuCheck`|Überschreibt [CMFCVisualManager::IsOwnerDrawMenuCheck](../../mfc/reference/cmfcvisualmanager-class.md#isownerdrawmenucheck)|  
|`CMFCVisualManagerWindows7::IsRibbonPresent`|Bestimmt, ob ein `CMFCRibbonBar` vorhanden und sichtbar ist.|  
|`CMFCVisualManagerWindows7::OnDrawButtonBorder`|Überschreibt [CMFCVisualManagerWindows::OnDrawButtonBorder](../../mfc/reference/cmfcvisualmanagerwindows-class.md#ondrawbuttonborder)|  
|`CMFCVisualManagerWindows7::OnDrawCheckBoxEx`|Überschreibt [CMFCVisualManagerWindows::OnDrawCheckBoxEx](../../mfc/reference/cmfcvisualmanagerwindows-class.md#ondrawcheckboxex)|  
|`CMFCVisualManagerWindows7::OnDrawComboDropButton`|Überschreibt [CMFCVisualManagerWindows::OnDrawComboDropButton](../../mfc/reference/cmfcvisualmanagerwindows-class.md#ondrawcombodropbutton)|  
|`CMFCVisualManagerWindows7::OnDrawDefaultRibbonImage`|Überschreibt [CMFCVisualManager::OnDrawDefaultRibbonImage](../../mfc/reference/cmfcvisualmanager-class.md#ondrawdefaultribbonimage)|  
|`CMFCVisualManagerWindows7::OnDrawMenuBorder`|Überschreibt [CMFCVisualManagerWindows::OnDrawMenuBorder](../../mfc/reference/cmfcvisualmanagerwindows-class.md#ondrawmenuborder)|  
|`CMFCVisualManagerWindows7::OnDrawMenuCheck`|Überschreibt [CMFCVisualManager::OnDrawMenuCheck](../../mfc/reference/cmfcvisualmanager-class.md#ondrawmenucheck)|  
|`CMFCVisualManagerWindows7::OnDrawMenuLabel`|Überschreibt [CMFCVisualManager::OnDrawMenuLabel](../../mfc/reference/cmfcvisualmanager-class.md#ondrawmenulabel)|  
|`CMFCVisualManagerWindows7::OnDrawRadioButton`|Außerkraftsetzungen`CMFCVisualManager::OnDrawRadioButton`|  
|`CMFCVisualManagerWindows7::OnDrawRibbonApplicationButton`|Überschreibt [CMFCVisualManager::OnDrawRibbonApplicationButton](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonapplicationbutton)|  
|`CMFCVisualManagerWindows7::OnDrawRibbonButtonBorder`|Überschreibt [CMFCVisualManager::OnDrawRibbonButtonBorder](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonbuttonborder)|  
|`CMFCVisualManagerWindows7::OnDrawRibbonCaption`|Überschreibt [CMFCVisualManager::OnDrawRibbonCaption](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribboncaption)|  
|`CMFCVisualManagerWindows7::OnDrawRibbonCaptionButton`|Überschreibt [CMFCVisualManager::OnDrawRibbonCaptionButton](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribboncaptionbutton)|  
|`CMFCVisualManagerWindows7::OnDrawRibbonCategory`|Überschreibt [CMFCVisualManager::OnDrawRibbonCategory](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribboncategory)|  
|`CMFCVisualManagerWindows7::OnDrawRibbonCategoryTab`|Überschreibt [CMFCVisualManager::OnDrawRibbonCategoryTab](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribboncategorytab)|  
|`CMFCVisualManagerWindows7::OnDrawRibbonDefaultPaneButton`|Überschreibt [CMFCVisualManager::OnDrawRibbonDefaultPaneButton](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbondefaultpanebutton)|  
|`CMFCVisualManagerWindows7::OnDrawRibbonGalleryButton`|Überschreibt [CMFCVisualManager::OnDrawRibbonGalleryButton](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbongallerybutton)|  
|`CMFCVisualManagerWindows7::OnDrawRibbonLaunchButton`|Außerkraftsetzungen`CMFCVisualManager::OnDrawRibbonLaunchButton`|  
|`CMFCVisualManagerWindows7::OnDrawRibbonMenuCheckFrame`|Überschreibt [CMFCVisualManager::OnDrawRibbonMenuCheckFrame](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonmenucheckframe)|  
|`CMFCVisualManagerWindows7::OnDrawRibbonPanel`|Überschreibt [CMFCVisualManager::OnDrawRibbonPanel](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonpanel)|  
|`CMFCVisualManagerWindows7::OnDrawRibbonPanelCaption`|Überschreibt [CMFCVisualManager::OnDrawRibbonPanelCaption](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonpanelcaption)|  
|`CMFCVisualManagerWindows7::OnDrawRibbonProgressBar`|Überschreibt [CMFCVisualManager::OnDrawRibbonProgressBar](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonprogressbar)|  
|`CMFCVisualManagerWindows7::OnDrawRibbonRecentFilesFrame`|Überschreibt [CMFCVisualManager::OnDrawRibbonRecentFilesFrame](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonrecentfilesframe)|  
|`CMFCVisualManagerWindows7::OnDrawRibbonSliderChannel`|Überschreibt [CMFCVisualManager::OnDrawRibbonSliderChannel](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonsliderchannel)|  
|`CMFCVisualManagerWindows7::OnDrawRibbonSliderThumb`|Überschreibt [CMFCVisualManager::OnDrawRibbonSliderThumb](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonsliderthumb)|  
|`CMFCVisualManagerWindows7::OnDrawRibbonSliderZoomButton`|Überschreibt [CMFCVisualManager::OnDrawRibbonSliderZoomButton](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonsliderzoombutton)|  
|`CMFCVisualManagerWindows7::OnDrawRibbonStatusBarPane`|Überschreibt [CMFCVisualManager::OnDrawRibbonStatusBarPane](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonstatusbarpane)|  
|`CMFCVisualManagerWindows7::OnDrawRibbonTabsFrame`|Überschreibt [CMFCVisualManager::OnDrawRibbonTabsFrame](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbontabsframe)|  
|`CMFCVisualManagerWindows7::OnDrawStatusBarSizeBox`|Überschreibt [CMFCVisualManagerWindows::OnDrawStatusBarSizeBox](../../mfc/reference/cmfcvisualmanagerwindows-class.md#ondrawstatusbarsizebox)|  
|`CMFCVisualManagerWindows7::OnFillBarBackground`|Überschreibt [CMFCVisualManagerWindows::OnFillBarBackground](../../mfc/reference/cmfcvisualmanagerwindows-class.md#onfillbarbackground)|  
|`CMFCVisualManagerWindows7::OnFillButtonInterior`|Überschreibt [CMFCVisualManagerWindows::OnFillButtonInterior](../../mfc/reference/cmfcvisualmanagerwindows-class.md#onfillbuttoninterior)|  
|[CMFCVisualManagerWindows7::OnFillMenuImageRect](#onfillmenuimagerect)|Das Framework ruft diese Methode auf, wenn sie den Bereich um menüelementbilder ausfüllt.|  
|`CMFCVisualManagerWindows7::OnFillRibbonButton`|Überschreibt [CMFCVisualManager::OnFillRibbonButton](../../mfc/reference/cmfcvisualmanager-class.md#onfillribbonbutton)|  
|`CMFCVisualManagerWindows7::OnFillRibbonQuickAccessToolBarPopup`|Überschreibt [CMFCVisualManager::OnFillRibbonQuickAccessToolBarPopup](../../mfc/reference/cmfcvisualmanager-class.md#onfillribbonquickaccesstoolbarpopup)|  
|`CMFCVisualManagerWindows7::OnHighlightMenuItem`|Überschreibt [CMFCVisualManagerWindows::OnHighlightMenuItem](../../mfc/reference/cmfcvisualmanagerwindows-class.md#onhighlightmenuitem)|  
|`CMFCVisualManagerWindows7::OnNcActivate`|Überschreibt [CMFCVisualManager::OnNcActivate](../../mfc/reference/cmfcvisualmanager-class.md#onncactivate)|  
|`CMFCVisualManagerWindows7::OnNcPaint`|Überschreibt [CMFCVisualManager::OnNcPaint](../../mfc/reference/cmfcvisualmanager-class.md#onncpaint)|  
|`CMFCVisualManagerWindows7::OnUpdateSystemColors`|Überschreibt [CMFCVisualManagerWindows::OnUpdateSystemColors](../../mfc/reference/cmfcvisualmanagerwindows-class.md#onupdatesystemcolors)|  
|`CMFCVisualManagerWindows7::SetResourceHandle`|Legt das Ressourcenhandle, das die Attribute des visuellen Manager beschreibt.|  
|`CMFCVisualManagerWindows7::SetStyle`|Legt das Farbschema der `CMFCVisualManagerWindows7` GUI.|  
  
## <a name="remarks"></a>Hinweise  
 Verwenden der `CMFCVisualManagerWindows7` Klasse, um das Erscheinungsbild Ihrer Anwendung, um den Standardwert zu imitieren [!INCLUDE[win7](../../build/includes/win7_md.md)] Anwendung. Diese Klasse ist möglicherweise nicht gültig, wenn die Anwendung auf eine Version von Windows ausgeführt wird als frühere [!INCLUDE[win7](../../build/includes/win7_md.md)]. In diesem Szenario wird die Anwendung verwendet den standardmäßigen visuellen Manager gemäß [CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md).  
  
 Die CMFCVisualManagerWindows7 erbt mehrere Methoden von der [CMFCVisualManagerWindows Klasse](../../mfc/reference/cmfcvisualmanagerwindows-class.md) und `CMFCVisualManager` Klasse. Im vorherigen Abschnitt beschriebenen Methoden sind Methoden, die mit der `CMFCVisualManagerWindows7` Klasse.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCBaseVisualManager](../../mfc/reference/cmfcbasevisualmanager-class.md)  
  
 [CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md)  
  
 [CMFCVisualManagerOfficeXP](../../mfc/reference/cmfcvisualmanagerofficexp-class.md)  
  
 [CMFCVisualManagerWindows](../../mfc/reference/cmfcvisualmanagerwindows-class.md)  
  
 `CMFCVisualManagerWindows7`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxvisualmanagerwindows7.h  
  
##  <a name="a-namedtorcmfcvisualmanagerwindows7a--cmfcvisualmanagerwindows7cmfcvisualmanagerwindows7"></a><a name="_dtorcmfcvisualmanagerwindows7"></a>CMFCVisualManagerWindows7:: ~ CMFCVisualManagerWindows7  
 Standarddestruktor.  
  
```  
virtual ~CMFCVisualManagerWindows7();
```  
  
##  <a name="a-namecmfcvisualmanagerwindows7a--cmfcvisualmanagerwindows7cmfcvisualmanagerwindows7"></a><a name="cmfcvisualmanagerwindows7"></a>CMFCVisualManagerWindows7::CMFCVisualManagerWindows7  
 Standardkonstruktor  
  
```  
CMFCVisualManagerWindows7();
```  
  
##  <a name="a-namegetribboneditbackgroundcolora--cmfcvisualmanagerwindows7getribboneditbackgroundcolor"></a><a name="getribboneditbackgroundcolor"></a>CMFCVisualManagerWindows7::GetRibbonEditBackgroundColor  
 Ruft die Farbe des Hintergrunds für ein Menüband-Eingabefeld.  
  
```  
virtual COLORREF GetRibbonEditBackgroundColor (
    CMFCRibbonRichEditCtrl* pEdit,  
    BOOL bIsHighlighted,  
    BOOL bIsPaneHighlighted,  
    BOOL bIsDisabled);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pEdit`  
 Ein Zeiger auf das Steuerelement zum Bearbeiten. Dieser Wert darf nicht `NULL` sein.  
  
 [out] `bIsHighlighted`  
 Gibt zurück, ob das Menüband-Kontrollkästchen markiert wird.  
  
 [out] `bIsPaneHighlighted`  
 Gibt `TRUE` Wenn das Menüband, der Bereich enthält `pEdit` hervorgehoben ist.  
  
 [out] `bIsDisabled`  
 Gibt zurück, ob `pEdit` ist deaktiviert.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Hintergrundfarbe des Bearbeitungsfelds `pEdit`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonfillmenuimagerecta--cmfcvisualmanagerwindows7onfillmenuimagerect"></a><a name="onfillmenuimagerect"></a>CMFCVisualManagerWindows7::OnFillMenuImageRect  
 Das Framework ruft diese Methode auf, wenn es um ein Menü Elementbild herum ausfüllt.  
  
```  
virtual void OnFillMenuImageRect(
    CDC* pDC,  
    CMFCToolBarButton* pButton,  
    CRect rect,  
    CMFCVisualManager::AFX_BUTTON_STATE state);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger auf den Gerätekontext, der eine Schaltfläche.  
  
 [in] `pButton`  
 Ein Zeiger auf eine `CMFCToolBarButton`. Das Framework füllt den Hintergrund für diese Schaltfläche.  
  
 [in] `rect`  
 Ein Rechteck, das die Grenzen des Bildbereichs Menü Schaltfläche angibt.  
  
 [in] `state`  
 Der Zustand der Schaltfläche.  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCVisualManager-Klasse](../../mfc/reference/cmfcvisualmanager-class.md)   
 [CMFCVisualManagerWindows-Klasse](../../mfc/reference/cmfcvisualmanagerwindows-class.md)


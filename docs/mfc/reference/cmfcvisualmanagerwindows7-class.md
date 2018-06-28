---
title: CMFCVisualManagerWindows7 Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCVisualManagerWindows7
- AFXVISUALMANAGERWINDOWS7/CMFCVisualManagerWindows7
- AFXVISUALMANAGERWINDOWS7/CMFCVisualManagerWindows7::CMFCVisualManagerWindows7
- AFXVISUALMANAGERWINDOWS7/CMFCVisualManagerWindows7::GetRibbonEditBackgroundColor
- AFXVISUALMANAGERWINDOWS7/CMFCVisualManagerWindows7::OnFillMenuImageRect
dev_langs:
- C++
helpviewer_keywords:
- CMFCVisualManagerWindows7 Class [MFC]
ms.assetid: e8d87df1-0c09-4b58-8ade-4e911f796e42
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c4bcc39645c079ef9a0b61a4e12782223dd19a92
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2018
ms.locfileid: "37042221"
---
# <a name="cmfcvisualmanagerwindows7-class"></a>CMFCVisualManagerWindows7-Klasse
Die `CMFCVisualManagerWindows7` ermöglicht es einer Anwendung die Darstellung einer [!INCLUDE[win7](../../build/includes/win7_md.md)] Anwendung.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCVisualManagerWindows7 : public CMFCVisualManagerWindows;  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCVisualManagerWindows7::CMFCVisualManagerWindows7](#cmfcvisualmanagerwindows7)|Standardkonstruktor|  
|[CMFCVisualManagerWindows7:: ~ CMFCVisualManagerWindows7](#cmfcvisualmanagerwindows7__~cmfcvisualmanagerwindows7)|Standarddestruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`CMFCVisualManagerWindows7::CleanStyle`|Löscht den aktuellen visuellen Stil, und setzt den visuellen Stil der Standardwert.|  
|`CMFCVisualManagerWindows7::CleanUp`|Löscht alle Objekte in der Benutzeroberfläche, und setzt die Menüs.|  
|`CMFCVisualManagerWindows7::DrawNcBtn`|Zeichnet eine Schaltfläche in der nicht-Clientbereichs auf den Frame. Das Framework verwendet diese Methode zum Zeichnen zu minimieren, maximieren, schließen und Schaltflächen in der oberen rechten Ecke des Fensterrahmens wiederherstellen. Diese Methode wird nicht aufgerufen, wenn das Programm nicht Aero Design verwendet.|  
|`CMFCVisualManagerWindows7::DrawNcText`|Zeichnet Text in den nicht-Clientbereichs auf den Frame. Das Framework verwendet diese Methode der Titel der Anwendung in der Titelleiste oben auf der das Rahmenfenster gezeichnet werden soll.|  
|`CMFCVisualManagerWindows7::DrawSeparator`|Zeichnet eine Trennzeichen für die [CMFCToolBar Klasse](../../mfc/reference/cmfctoolbar-class.md).|  
|`CMFCVisualManagerWindows7::GetRibbonBar`|Ruft die [CMFCRibbonBar Class](../../mfc/reference/cmfcribbonbar-class.md) der Benutzeroberfläche zugeordnet.|  
|[CMFCVisualManagerWindows7::GetRibbonEditBackgroundColor](#getribboneditbackgroundcolor)|Ruft die Hintergrundfarbe eines Menübands bearbeiten.|  
|`CMFCVisualManagerWindows7::GetRibbonPopupBorderSize`|Überschreibt [CMFCVisualManager::GetRibbonPopupBorderSize](../../mfc/reference/cmfcvisualmanager-class.md#getribbonpopupbordersize)|  
|`CMFCVisualManagerWindows7::GetRibbonQuickAccessToolBarChevronOffset`|Überschreibt [CMFCVisualManager::GetRibbonQuickAccessToolBarChevronOffset](../../mfc/reference/cmfcvisualmanager-class.md#getribbonquickaccesstoolbarchevronoffset)|  
|`CMFCVisualManagerWindows7::GetRibbonQuickAccessToolBarRightMargin`|Überschreibt [CMFCVisualManager::GetRibbonQuickAccessToolBarRightMargin](../../mfc/reference/cmfcvisualmanager-class.md#getribbonquickaccesstoolbarrightmargin)|  
|`CMFCVisualManagerWindows7::IsHighlightWholeMenuItem`|Überschreibt [CMFCVisualManagerWindows::IsHighlightWholeMenuItem](../../mfc/reference/cmfcvisualmanagerwindows-class.md#ishighlightwholemenuitem)|  
|`CMFCVisualManagerWindows7::IsOwnerDrawMenuCheck`|Überschreibt [CMFCVisualManager::IsOwnerDrawMenuCheck](../../mfc/reference/cmfcvisualmanager-class.md#isownerdrawmenucheck)|  
|`CMFCVisualManagerWindows7::IsRibbonPresent`|Bestimmt, ob eine `CMFCRibbonBar` vorhanden und sichtbar ist.|  
|`CMFCVisualManagerWindows7::OnDrawButtonBorder`|Überschreibt [CMFCVisualManagerWindows::OnDrawButtonBorder](../../mfc/reference/cmfcvisualmanagerwindows-class.md#ondrawbuttonborder)|  
|`CMFCVisualManagerWindows7::OnDrawCheckBoxEx`|Überschreibt [CMFCVisualManagerWindows::OnDrawCheckBoxEx](../../mfc/reference/cmfcvisualmanagerwindows-class.md#ondrawcheckboxex)|  
|`CMFCVisualManagerWindows7::OnDrawComboDropButton`|Überschreibt [CMFCVisualManagerWindows::OnDrawComboDropButton](../../mfc/reference/cmfcvisualmanagerwindows-class.md#ondrawcombodropbutton)|  
|`CMFCVisualManagerWindows7::OnDrawDefaultRibbonImage`|Überschreibt [CMFCVisualManager::OnDrawDefaultRibbonImage](../../mfc/reference/cmfcvisualmanager-class.md#ondrawdefaultribbonimage)|  
|`CMFCVisualManagerWindows7::OnDrawMenuBorder`|Überschreibt [CMFCVisualManagerWindows::OnDrawMenuBorder](../../mfc/reference/cmfcvisualmanagerwindows-class.md#ondrawmenuborder)|  
|`CMFCVisualManagerWindows7::OnDrawMenuCheck`|Überschreibt [CMFCVisualManager::OnDrawMenuCheck](../../mfc/reference/cmfcvisualmanager-class.md#ondrawmenucheck)|  
|`CMFCVisualManagerWindows7::OnDrawMenuLabel`|Überschreibt [CMFCVisualManager::OnDrawMenuLabel](../../mfc/reference/cmfcvisualmanager-class.md#ondrawmenulabel)|  
|`CMFCVisualManagerWindows7::OnDrawRadioButton`|Überschreibt `CMFCVisualManager::OnDrawRadioButton`|  
|`CMFCVisualManagerWindows7::OnDrawRibbonApplicationButton`|Überschreibt [CMFCVisualManager::OnDrawRibbonApplicationButton](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonapplicationbutton)|  
|`CMFCVisualManagerWindows7::OnDrawRibbonButtonBorder`|Überschreibt [CMFCVisualManager::OnDrawRibbonButtonBorder](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonbuttonborder)|  
|`CMFCVisualManagerWindows7::OnDrawRibbonCaption`|Überschreibt [CMFCVisualManager::OnDrawRibbonCaption](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribboncaption)|  
|`CMFCVisualManagerWindows7::OnDrawRibbonCaptionButton`|Überschreibt [CMFCVisualManager::OnDrawRibbonCaptionButton](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribboncaptionbutton)|  
|`CMFCVisualManagerWindows7::OnDrawRibbonCategory`|Überschreibt [CMFCVisualManager::OnDrawRibbonCategory](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribboncategory)|  
|`CMFCVisualManagerWindows7::OnDrawRibbonCategoryTab`|Überschreibt [CMFCVisualManager::OnDrawRibbonCategoryTab](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribboncategorytab)|  
|`CMFCVisualManagerWindows7::OnDrawRibbonDefaultPaneButton`|Überschreibt [CMFCVisualManager::OnDrawRibbonDefaultPaneButton](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbondefaultpanebutton)|  
|`CMFCVisualManagerWindows7::OnDrawRibbonGalleryButton`|Überschreibt [CMFCVisualManager::OnDrawRibbonGalleryButton](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbongallerybutton)|  
|`CMFCVisualManagerWindows7::OnDrawRibbonLaunchButton`|Überschreibt `CMFCVisualManager::OnDrawRibbonLaunchButton`|  
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
|[CMFCVisualManagerWindows7::OnFillMenuImageRect](#onfillmenuimagerect)|Das Framework ruft diese Methode auf, wenn sie die Fläche um menüelementbilder voll ist.|  
|`CMFCVisualManagerWindows7::OnFillRibbonButton`|Überschreibt [CMFCVisualManager::OnFillRibbonButton](../../mfc/reference/cmfcvisualmanager-class.md#onfillribbonbutton)|  
|`CMFCVisualManagerWindows7::OnFillRibbonQuickAccessToolBarPopup`|Überschreibt [CMFCVisualManager::OnFillRibbonQuickAccessToolBarPopup](../../mfc/reference/cmfcvisualmanager-class.md#onfillribbonquickaccesstoolbarpopup)|  
|`CMFCVisualManagerWindows7::OnHighlightMenuItem`|Überschreibt [CMFCVisualManagerWindows::OnHighlightMenuItem](../../mfc/reference/cmfcvisualmanagerwindows-class.md#onhighlightmenuitem)|  
|`CMFCVisualManagerWindows7::OnNcActivate`|Überschreibt [CMFCVisualManager::OnNcActivate](../../mfc/reference/cmfcvisualmanager-class.md#onncactivate)|  
|`CMFCVisualManagerWindows7::OnNcPaint`|Überschreibt [CMFCVisualManager::OnNcPaint](../../mfc/reference/cmfcvisualmanager-class.md#onncpaint)|  
|`CMFCVisualManagerWindows7::OnUpdateSystemColors`|Überschreibt [CMFCVisualManagerWindows::OnUpdateSystemColors](../../mfc/reference/cmfcvisualmanagerwindows-class.md#onupdatesystemcolors)|  
|`CMFCVisualManagerWindows7::SetResourceHandle`|Legt das Ressourcenhandle, das die Attribute eines visuellen Manager beschreibt.|  
|`CMFCVisualManagerWindows7::SetStyle`|Legt das Farbschema für die `CMFCVisualManagerWindows7` GUI.|  
  
## <a name="remarks"></a>Hinweise  
 Verwenden der `CMFCVisualManagerWindows7` Klasse so ändern Sie die Darstellung der Anwendung, um den Standardwert zu imitieren [!INCLUDE[win7](../../build/includes/win7_md.md)] Anwendung. Diese Klasse ist möglicherweise nicht gültig, wenn Ihre Anwendung auf eine Version von Windows ausgeführt wird als frühere [!INCLUDE[win7](../../build/includes/win7_md.md)]. In diesem Szenario verwendet die Anwendung den standardmäßigen visuellen Manager im definierten [CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md).  
  
 Die CMFCVisualManagerWindows7 erbt mehrere Methoden aufgeteilt, von der [CMFCVisualManagerWindows Klasse](../../mfc/reference/cmfcvisualmanagerwindows-class.md) und die `CMFCVisualManager` Klasse. Im vorherigen Abschnitt aufgeführten Methoden sind Methoden, die noch nicht mit der `CMFCVisualManagerWindows7` Klasse.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCBaseVisualManager](../../mfc/reference/cmfcbasevisualmanager-class.md)  
  
 [CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md)  
  
 [CMFCVisualManagerOfficeXP](../../mfc/reference/cmfcvisualmanagerofficexp-class.md)  
  
 [CMFCVisualManagerWindows](../../mfc/reference/cmfcvisualmanagerwindows-class.md)  
  
 `CMFCVisualManagerWindows7`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxvisualmanagerwindows7.h  
  
##  <a name="_dtorcmfcvisualmanagerwindows7"></a>  CMFCVisualManagerWindows7:: ~ CMFCVisualManagerWindows7  
 Standarddestruktor.  
  
```  
virtual ~CMFCVisualManagerWindows7();
```  
  
##  <a name="cmfcvisualmanagerwindows7"></a>  CMFCVisualManagerWindows7::CMFCVisualManagerWindows7  
 Standardkonstruktor  
  
```  
CMFCVisualManagerWindows7();
```  
  
##  <a name="getribboneditbackgroundcolor"></a>  CMFCVisualManagerWindows7::GetRibbonEditBackgroundColor  
 Ruft die Farbe des Hintergrunds eines Menübands bearbeiten Felds ab.  
  
```  
virtual COLORREF GetRibbonEditBackgroundColor (
    CMFCRibbonRichEditCtrl* pEdit,  
    BOOL bIsHighlighted,  
    BOOL bIsPaneHighlighted,  
    BOOL bIsDisabled);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pEdit*  
 Ein Zeiger auf das Steuerelement zum Bearbeiten. Dieser Wert darf nicht `NULL` sein.  
  
 [out] *bIsHighlighted*  
 Gibt zurück, ob das Menüband Feld hervorgehoben ist.  
  
 [out] *bIsPaneHighlighted*  
 Gibt `TRUE` , wenn das Menüband, der Bereich enthält *pEdit* wird hervorgehoben.  
  
 [out] *bIsDisabled*  
 Gibt zurück, ob *pEdit* ist deaktiviert.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Farbe des Hintergrunds neben dem Bearbeitungsfeld *pEdit*.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onfillmenuimagerect"></a>  CMFCVisualManagerWindows7::OnFillMenuImageRect  
 Das Framework ruft diese Methode auf, wenn sie die Fläche um ein Menü Elementbild voll ist.  
  
```  
virtual void OnFillMenuImageRect(
    CDC* pDC,  
    CMFCToolBarButton* pButton,  
    CRect rect,  
    CMFCVisualManager::AFX_BUTTON_STATE state);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pDC*  
 Ein Zeiger auf den Gerätekontext einer Menüschaltfläche.  
  
 [in] *pButton*  
 Ein Zeiger auf eine `CMFCToolBarButton`. Das Framework füllt den Hintergrund für diese Schaltfläche.  
  
 [in] *Rect*  
 Ein Rechteck, das die Grenzen des Bilds im Menübereich-Schaltfläche angibt.  
  
 [in] *Zustand*  
 Der Zustand der Schaltfläche.  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCVisualManager-Klasse](../../mfc/reference/cmfcvisualmanager-class.md)   
 [CMFCVisualManagerWindows-Klasse](../../mfc/reference/cmfcvisualmanagerwindows-class.md)

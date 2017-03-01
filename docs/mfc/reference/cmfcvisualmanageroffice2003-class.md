---
title: Klasse CMFCVisualManagerOffice2003 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCVisualManagerOffice2003
dev_langs:
- C++
helpviewer_keywords:
- CMFCVisualManagerOffice2003 class
ms.assetid: 115482cd-e349-450a-8dc4-c6023d092aab
caps.latest.revision: 31
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: db48c053de741ff37aacf377f338ea4af4d3bec1
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcvisualmanageroffice2003-class"></a>CMFCVisualManagerOffice2003-Klasse
`CMFCVisualManagerOffice2003`Wendet eine Anwendung eine Microsoft Office 2003-Darstellung.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCVisualManagerOffice2003 : public CMFCVisualManagerOfficeXP  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCVisualManagerOffice2003::DrawComboBorderWinXP](#drawcomboborderwinxp)|Zeichnet den Rahmen des Kombinationsfelds mit dem aktuellen Windows XP-Design. (Überschreibt [CMFCVisualManager::DrawComboBorderWinXP](../../mfc/reference/cmfcvisualmanager-class.md#drawcomboborderwinxp).)|  
|[CMFCVisualManagerOffice2003::DrawComboDropButtonWinXP](#drawcombodropbuttonwinxp)|Zeichnet eine Kombinationsfeld Dropdown-Schaltfläche mit dem aktuellen Windows XP-Design. (Überschreibt [CMFCVisualManager::DrawComboDropButtonWinXP](../../mfc/reference/cmfcvisualmanager-class.md#drawcombodropbuttonwinxp).)|  
|[CMFCVisualManagerOffice2003::DrawCustomizeButton](#drawcustomizebutton)|Zeichnet eine Schaltfläche anpassen.|  
|[CMFCVisualManagerOffice2003::DrawPushButtonWinXP](#drawpushbuttonwinxp)|Zeichnet eine Schaltfläche mit dem aktuellen Windows XP-Design. (Überschreibt [CMFCVisualManager::DrawPushButtonWinXP](../../mfc/reference/cmfcvisualmanager-class.md#drawpushbuttonwinxp).)|  
|[CMFCVisualManagerOffice2003::GetBaseThemeColor](#getbasethemecolor)|Ruft die Designfarbe des Basis.|  
|[CMFCVisualManagerOffice2003::GetHighlightMenuItemColor](#gethighlightmenuitemcolor)|Ruft die Farbe für den markierten Menüelements ab.|  
|[CMFCVisualManagerOffice2003::GetPropertyGridGroupColor](#getpropertygridgroupcolor)|Das Framework ruft diese Methode, um die Hintergrundfarbe einer Eigenschaftenliste abgerufen. (Überschreibt `CMFCVisualManagerOfficeXP::GetPropertyGridGroupColor`.)|  
|[CMFCVisualManagerOffice2003::GetPropertyGridGroupTextColor](#getpropertygridgrouptextcolor)|Das Framework ruft diese Methode, um die Textfarbe der Eigenschaftenliste abzurufen. (Überschreibt `CMFCVisualManagerOfficeXP::GetPropertyGridGroupTextColor`.)|  
|[CMFCVisualManagerOffice2003::GetShowAllMenuItemsHeight](#getshowallmenuitemsheight)|Gibt die Höhe aller Menüelemente. (Überschreibt [CMFCVisualManager::GetShowAllMenuItemsHeight](../../mfc/reference/cmfcvisualmanager-class.md#getshowallmenuitemsheight).)|  
|[CMFCVisualManagerOffice2003::GetSmartDockingBaseGuideColors](#getsmartdockingbaseguidecolors)|Legt das angegebene Basisgruppe Hintergrundfarbe und Farbe des Rahmens. (Überschreibt `CMFCVisualManagerOfficeXP::GetSmartDockingBaseGuideColors`.)|  
|[CMFCVisualManagerOffice2003::GetSmartDockingHighlightToneColor](#getsmartdockinghighlighttonecolor)|Ruft die Hervorhebungsfarbe für Ton ab. (Überschreibt [CMFCVisualManager::GetSmartDockingHighlightToneColor](../../mfc/reference/cmfcvisualmanager-class.md#getsmartdockinghighlighttonecolor).)|  
|[CMFCVisualManagerOffice2003::GetTabFrameColors](#gettabframecolors)|Das Framework ruft diese Funktion bei der Satz von Farben für das Zeichnen einer im Registerkartenfenster abzurufen. (Überschreibt [CMFCVisualManager::GetTabFrameColors](../../mfc/reference/cmfcvisualmanager-class.md#gettabframecolors).)|  
|[CMFCVisualManagerOffice2003::GetToolBarCustomizeButtonMargin](#gettoolbarcustomizebuttonmargin)|Ruft den Rand der Symbolleisten-Schaltfläche anpassen. (Überschreibt `CMFCVisualManager::GetToolBarCustomizeButtonMargin`.)|  
|[CMFCVisualManagerOffice2003::GetToolbarDisabledColor](#gettoolbardisabledcolor)|Ruft die Farbe deaktivierte für die Symbolleiste. (Überschreibt `CMFCVisualManager::GetToolbarDisabledColor`.)|  
|[CMFCVisualManagerOffice2003::GetToolTipInfo](#gettooltipinfo)|Aufgerufen, um QuickInfo-Informationen zu erhalten. (Überschreibt [CMFCVisualManager::GetToolTipInfo](../../mfc/reference/cmfcvisualmanager-class.md#gettooltipinfo).)|  
|[CMFCVisualManagerOffice2003::IsDefaultWinXPColorsEnabled](#isdefaultwinxpcolorsenabled)|Gibt an, ob es sich bei der visuelle Manager systemeigene Windows XP Designfarben verwendet.|  
|[CMFCVisualManagerOffice2003::IsDockingTabHasBorder](#isdockingtabhasborder)|Gibt zurück, ob die aktuelle visuelle Manager Rahmen um Bereiche zeichnet, die im Registerkartenformat und angedockt sind. (Überschreibt [CMFCVisualManager::IsDockingTabHasBorder](../../mfc/reference/cmfcvisualmanager-class.md#isdockingtabhasborder).)|  
|[CMFCVisualManagerOffice2003::IsHighlightOneNoteTabs](#ishighlightonenotetabs)|Gibt an, ob es sich bei OneNote Registerkarten markiert werden sollte. (Überschreibt `CMFCVisualManager::IsHighlightOneNoteTabs`.)|  
|[CMFCVisualManagerOffice2003::IsOffsetPressedButton](#isoffsetpressedbutton)|Wird vom Framework aufgerufen, wenn eine Symbolleisten-Schaltfläche zu zeichnen. (Überschreibt `CMFCVisualManager::IsOffsetPressedButton`.)|  
|[CMFCVisualManagerOffice2003::IsStatusBarOfficeXPLook](#isstatusbarofficexplook)|Gibt an, ob eine Statusleiste mit einer Darstellung des Office XP ist.|  
|[CMFCVisualManagerOffice2003::IsToolbarRoundShape](#istoolbarroundshape)|Gibt an, ob eine angegebene Symbolleiste eine runde Form hat. (Überschreibt [CMFCVisualManager::IsToolbarRoundShape](../../mfc/reference/cmfcvisualmanager-class.md#istoolbarroundshape).)|  
|[CMFCVisualManagerOffice2003::IsUseGlobalTheme](#isuseglobaltheme)|Gibt an, ob ein globale Windows XP-Design verwendet wird.|  
|[CMFCVisualManagerOffice2003::IsWindowsThemingSupported](#iswindowsthemingsupported)|Gibt an, ob Windows-Designs unterstützt wird. (Überschreibt [CMFCVisualManager::IsWindowsThemingSupported](../../mfc/reference/cmfcvisualmanager-class.md#iswindowsthemingsupported).)|  
|[CMFCVisualManagerOffice2003::OnDrawAutoHideButtonBorder](#ondrawautohidebuttonborder)|Das Framework ruft diese Methode auf, wenn es den Rahmen einer Schaltfläche zum automatischen Ausblenden zeichnet. (Überschreibt [CMFCVisualManager::OnDrawAutoHideButtonBorder](../../mfc/reference/cmfcvisualmanager-class.md#ondrawautohidebuttonborder).)|  
|[CMFCVisualManagerOffice2003::OnDrawBarGripper](#ondrawbargripper)|Vom Framework aufgerufen, wenn sie den Ziehpunkt für eine Steuerleiste zeichnet. (Überschreibt `CMFCVisualManagerOfficeXP::OnDrawBarGripper`.)|  
|[CMFCVisualManagerOffice2003::OnDrawBrowseButton](#ondrawbrowsebutton)|Das Framework ruft diese Methode auf, wenn sie die Schaltfläche zum Durchsuchen für ein Bearbeitungssteuerelement zeichnet. (Überschreibt `CMFCVisualManagerOfficeXP::OnDrawBrowseButton`.)|  
|[CMFCVisualManagerOffice2003::OnDrawButtonBorder](#ondrawbuttonborder)|Das Framework ruft diese Methode auf, wenn sie den Rahmen einer Symbolleisten-Schaltfläche zeichnet. (Überschreibt `CMFCVisualManagerOfficeXP::OnDrawButtonBorder`.)|  
|[CMFCVisualManagerOffice2003::OnDrawCaptionBarBorder](#ondrawcaptionbarborder)|Das Framework ruft diese Methode, wenn der Rahmen gezeichnet ein [CMFCCaptionBar Class](../../mfc/reference/cmfccaptionbar-class.md) Objekt. (Überschreibt [CMFCVisualManager::OnDrawCaptionBarBorder](../../mfc/reference/cmfcvisualmanager-class.md#ondrawcaptionbarborder).)|  
|[CMFCVisualManagerOffice2003::OnDrawCheckBoxEx](#ondrawcheckboxex)|Das Framework ruft diese Methode auf, wenn sie ein Kontrollkästchen zeichnet. (Überschreibt [CMFCVisualManager::OnDrawCheckBoxEx](../../mfc/reference/cmfcvisualmanager-class.md#ondrawcheckboxex).)|  
|[CMFCVisualManagerOffice2003::OnDrawComboBorder](#ondrawcomboborder)|Das Framework ruft diese Methode, wenn den Rahmen gezeichnet ein [CMFCToolBarComboBoxButton Klasse](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md) Objekt. (Überschreibt `CMFCVisualManagerOfficeXP::OnDrawComboBorder`.)|  
|[CMFCVisualManagerOffice2003::OnDrawComboDropButton](#ondrawcombodropbutton)|Das Framework ruft diese Methode auf, wenn sie die Dropdownschaltfläche des zeichnet einen [CMFCToolBarComboBoxButton Klasse](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md). (Überschreibt `CMFCVisualManagerOfficeXP::OnDrawComboDropButton`.)|  
|[CMFCVisualManagerOffice2003::OnDrawControlBorder](#ondrawcontrolborder)|Das Framework ruft diese Methode auf, wenn sie den Rand eines Steuerelements zeichnet. (Überschreibt [CMFCVisualManager::OnDrawControlBorder](../../mfc/reference/cmfcvisualmanager-class.md#ondrawcontrolborder).)|  
|[CMFCVisualManagerOffice2003::OnDrawExpandingBox](#ondrawexpandingbox)|Das Framework ruft diese Methode auf, wenn es einem erweiterbaren Feld zeichnet. (Überschreibt [CMFCVisualManager::OnDrawExpandingBox](../../mfc/reference/cmfcvisualmanager-class.md#ondrawexpandingbox).)|  
|[CMFCVisualManagerOffice2003::OnDrawHeaderCtrlBorder](#ondrawheaderctrlborder)|Das Framework ruft diese Methode, wenn es den Rahmen um eine Instanz der zeichnet die [CMFCHeaderCtrl Klasse](../../mfc/reference/cmfcheaderctrl-class.md). (Überschreibt [CMFCVisualManager::OnDrawHeaderCtrlBorder](../../mfc/reference/cmfcvisualmanager-class.md#ondrawheaderctrlborder).)|  
|[CMFCVisualManagerOffice2003::OnDrawMenuBorder](#ondrawmenuborder)|Das Framework ruft diese Methode, wenn der Rahmen gezeichnet ein [CMFCPopupMenu Klasse](../../mfc/reference/cmfcpopupmenu-class.md). (Überschreibt `CMFCVisualManagerOfficeXP::OnDrawMenuBorder`.)|  
|[CMFCVisualManagerOffice2003::OnDrawOutlookBarSplitter](#ondrawoutlookbarsplitter)|Das Framework ruft diese Methode auf, wenn den Splitter für eine Outlook-Leiste gezeichnet. (Überschreibt [CMFCVisualManager::OnDrawOutlookBarSplitter](../../mfc/reference/cmfcvisualmanager-class.md#ondrawoutlookbarsplitter).)|  
|[CMFCVisualManagerOffice2003::OnDrawOutlookPageButtonBorder](#ondrawoutlookpagebuttonborder)|Wird vom Framework aufgerufen, wenn es den Rahmen einer Outlook-Seite-Schaltfläche zeichnet. (Überschreibt [CMFCVisualManager::OnDrawOutlookPageButtonBorder](../../mfc/reference/cmfcvisualmanager-class.md#ondrawoutlookpagebuttonborder).)|  
|[CMFCVisualManagerOffice2003::OnDrawPaneBorder](#ondrawpaneborder)|Das Framework ruft diese Methode, wenn der Rahmen gezeichnet ein [CPane-Klasse](../../mfc/reference/cpane-class.md) Objekt. (Überschreibt `CMFCVisualManagerOfficeXP::OnDrawPaneBorder`.)|  
|[CMFCVisualManagerOffice2003::OnDrawPaneCaption](#ondrawpanecaption)|Das Framework ruft diese Methode auf, wenn sie eine Beschriftung für zeichnet einen [CDockablePane-Klasse](../../mfc/reference/cdockablepane-class.md) Objekt. (Überschreibt `CMFCVisualManagerOfficeXP::OnDrawPaneCaption`.)|  
|[CMFCVisualManagerOffice2003::OnDrawPopupWindowBorder](#ondrawpopupwindowborder)|Das Framework ruft diese Methode auf, wenn sie den Rahmen eines Popup-Fensters zeichnet. (Überschreibt `CMFCVisualManagerOfficeXP::OnDrawPopupWindowBorder`.)|  
|[CMFCVisualManagerOffice2003::OnDrawPopupWindowButtonBorder](#ondrawpopupwindowbuttonborder)|Das Framework ruft diese Methode auf, wenn sie den Rahmen einer Schaltfläche in einem Popupfenster zeichnet. (Überschreibt `CMFCVisualManagerOfficeXP::OnDrawPopupWindowButtonBorder`.)|  
|[CMFCVisualManagerOffice2003::OnDrawPopupWindowCaption](#ondrawpopupwindowcaption)|Das Framework ruft diese Methode auf, wenn sie die Beschriftung des ein Popup-Fenster zeichnet. (Überschreibt `CMFCVisualManagerOfficeXP::OnDrawPopupWindowCaption`.)|  
|[CMFCVisualManagerOffice2003::OnDrawRibbonButtonsGroup](#ondrawribbonbuttonsgroup)|Das Framework ruft diese Methode auf, wenn sie eine Gruppe von Schaltflächen auf der Multifunktionsleiste zeichnet. (Überschreibt [CMFCVisualManager::OnDrawRibbonButtonsGroup](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonbuttonsgroup).)|  
|[CMFCVisualManagerOffice2003::OnDrawRibbonCategoryCaption](#ondrawribboncategorycaption)|Das Framework ruft diese Methode auf, wenn sie auf die Titelleiste für eine Menübandkategorie zeichnet. (Überschreibt [CMFCVisualManager::OnDrawRibbonCategoryCaption](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribboncategorycaption).)|  
|[CMFCVisualManagerOffice2003::OnDrawRibbonCategoryTab](#ondrawribboncategorytab)|Das Framework ruft diese Methode auf, wenn sie die Registerkarte für eine Menübandkategorie zeichnet. (Überschreibt [CMFCVisualManager::OnDrawRibbonCategoryTab](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribboncategorytab).)|  
|[CMFCVisualManagerOffice2003::OnDrawRibbonProgressBar](#ondrawribbonprogressbar)|Das Framework ruft diese Methode auf, wenn er zeichnet einen [CMFCRibbonProgressBar Klasse](../../mfc/reference/cmfcribbonprogressbar-class.md). (Überschreibt [CMFCVisualManager::OnDrawRibbonProgressBar](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonprogressbar).)|  
|[CMFCVisualManagerOffice2003::OnDrawRibbonQuickAccessToolBarSeparator](#ondrawribbonquickaccesstoolbarseparator)|Das Framework ruft diese Methode auf, wenn es eine Trennzeichen auf der Symbolleiste für den Schnellzugriff eines Menübands zeichnet. (Überschreibt `CMFCVisualManagerOfficeXP::OnDrawRibbonQuickAccessToolBarSeparator`.)|  
|[CMFCVisualManagerOffice2003::OnDrawRibbonSliderChannel](#ondrawribbonsliderchannel)|Das Framework ruft diese Methode auf, wenn sie den Kanal des zeichnet einen [CMFCRibbonSlider Klasse](../../mfc/reference/cmfcribbonslider-class.md). (Überschreibt [CMFCVisualManager::OnDrawRibbonSliderChannel](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonsliderchannel).)|  
|[CMFCVisualManagerOffice2003::OnDrawRibbonSliderThumb](#ondrawribbonsliderthumb)|Das Framework ruft diese Methode auf, wenn sie den Ziehpunkt des zeichnet einen [CMFCRibbonSlider](../../mfc/reference/cmfcribbonslider-class.md) Objekt. (Überschreibt [CMFCVisualManager::OnDrawRibbonSliderThumb](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonsliderthumb).)|  
|[CMFCVisualManagerOffice2003::OnDrawRibbonSliderZoomButton](#ondrawribbonsliderzoombutton)|Das Framework ruft diese Methode auf, wenn sie den Zoom-Schaltflächen für zeichnet einen [CMFCRibbonSlider](../../mfc/reference/cmfcribbonslider-class.md) Objekt. (Überschreibt [CMFCVisualManager::OnDrawRibbonSliderZoomButton](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonsliderzoombutton).)|  
|[CMFCVisualManagerOffice2003::OnDrawRibbonStatusBarPane](#ondrawribbonstatusbarpane)|Das Framework ruft diese Methode auf, wenn sie einen Bereich auf der Statusleiste zeichnet. (Überschreibt `CMFCVisualManagerOfficeXP::OnDrawRibbonStatusBarPane`.)|  
|[CMFCVisualManagerOffice2003::OnDrawScrollButtons](#ondrawscrollbuttons)|Das Framework ruft diese Methode auf, wenn es Bildlaufschaltflächen zeichnet. (Überschreibt `CMFCVisualManagerOfficeXP::OnDrawScrollButtons`.)|  
|[CMFCVisualManagerOffice2003::OnDrawSeparator](#ondrawseparator)|Das Framework ruft diese Methode auf, wenn es eine Trennzeichen zeichnet. (Überschreibt `CMFCVisualManagerOfficeXP::OnDrawSeparator`.)|  
|[CMFCVisualManagerOffice2003::OnDrawShowAllMenuItems](#ondrawshowallmenuitems)|Das Framework ruft diese Methode auf, wenn sie alle Elemente in einem Menü zeichnet. (Überschreibt [CMFCVisualManager::OnDrawShowAllMenuItems](../../mfc/reference/cmfcvisualmanager-class.md#ondrawshowallmenuitems).)|  
|[CMFCVisualManagerOffice2003::OnDrawStatusBarPaneBorder](#ondrawstatusbarpaneborder)|Das Framework ruft diese Methode, wenn es den Rahmen für zeichnet einen [CMFCStatusBar-Klasse](../../mfc/reference/cmfcstatusbar-class.md) Objekt. (Überschreibt `CMFCVisualManagerOfficeXP::OnDrawStatusBarPaneBorder`.)|  
|[CMFCVisualManagerOffice2003::OnDrawStatusBarProgress](#ondrawstatusbarprogress)|Das Framework ruft diese Methode, wenn die Statusanzeige gezeichnet wird, auf die [CMFCStatusBar](../../mfc/reference/cmfcstatusbar-class.md) Objekt. (Überschreibt [CMFCVisualManager::OnDrawStatusBarProgress](../../mfc/reference/cmfcvisualmanager-class.md#ondrawstatusbarprogress).)|  
|[CMFCVisualManagerOffice2003::OnDrawStatusBarSizeBox](#ondrawstatusbarsizebox)|Das Framework ruft diese Methode auf, wenn es für das Größeneinstellungsfeld zeichnet einen [CMFCStatusBar](../../mfc/reference/cmfcstatusbar-class.md). (Überschreibt [CMFCVisualManager::OnDrawStatusBarSizeBox](../../mfc/reference/cmfcvisualmanager-class.md#ondrawstatusbarsizebox).)|  
|[CMFCVisualManagerOffice2003::OnDrawTab](#ondrawtab)|Das Framework ruft diese Methode auf, wenn sie die Registerkarten zeichnet einen [CMFCBaseTabCtrl-Klasse](../../mfc/reference/cmfcbasetabctrl-class.md) Objekt. (Überschreibt `CMFCVisualManagerOfficeXP::OnDrawTab`.)|  
|[CMFCVisualManagerOffice2003::OnDrawTabsButtonBorder](#ondrawtabsbuttonborder)|Das Framework ruft diese Methode auf, wenn sie den Rahmen einer Registerkarte Schaltfläche zeichnet. (Überschreibt `CMFCVisualManagerOfficeXP::OnDrawTabsButtonBorder`.)|  
|[CMFCVisualManagerOffice2003::OnDrawTask](#ondrawtask)|Das Framework ruft diese Methode auf, wenn er zeichnet einen [Cmfctaskspanetask-Klasse](../../mfc/reference/cmfctaskspanetask-class.md) Objekt. (Überschreibt `CMFCVisualManagerOfficeXP::OnDrawTask`.)|  
|[CMFCVisualManagerOffice2003::OnDrawTasksGroupAreaBorder](#ondrawtasksgroupareaborder)|Das Framework ruft diese Methode, wenn er zeichnet einen Rahmen um eine Gruppe, auf einem [CMFCTasksPane Klasse](../../mfc/reference/cmfctaskspane-class.md) Objekt. (Überschreibt `CMFCVisualManagerOfficeXP::OnDrawTasksGroupAreaBorder`.)|  
|[CMFCVisualManagerOffice2003::OnDrawTasksGroupCaption](#ondrawtasksgroupcaption)|Das Framework ruft diese Methode auf, wenn sie die Beschriftung für zeichnet einen [CMFCTasksPaneTaskGroup-Klasse](../../mfc/reference/cmfctaskspanetaskgroup-class.md) Objekt. (Überschreibt `CMFCVisualManagerOfficeXP::OnDrawTasksGroupCaption`.)|  
|[CMFCVisualManagerOffice2003::OnDrawTearOffCaption](#ondrawtearoffcaption)|Das Framework ruft diese Methode auf, wenn sie die Beschriftung für zeichnet einen [CMFCPopupMenu Klasse](../../mfc/reference/cmfcpopupmenu-class.md) Objekt. (Überschreibt `CMFCVisualManagerOfficeXP::OnDrawTearOffCaption`.)|  
|[CMFCVisualManagerOffice2003::OnErasePopupWindowButton](#onerasepopupwindowbutton)|Das Framework ruft diese Methode auf, wenn eine Schaltfläche in einem Popupfenster gelöscht. (Überschreibt `CMFCVisualManagerOfficeXP::OnErasePopupWindowButton`.)|  
|[CMFCVisualManagerOffice2003::OnEraseTabsArea](#onerasetabsarea)|Das Framework ruft diese Methode, wenn die Registerkarte Clientbereich eines Fensters Registerkarte gelöscht. (Überschreibt `CMFCVisualManagerOfficeXP::OnEraseTabsArea`.)|  
|[CMFCVisualManagerOffice2003::OnEraseTabsButton](#onerasetabsbutton)|Das Framework ruft diese Methode auf, wenn sie den Text und das Symbol einer Schaltfläche Registerkarte löscht. (Überschreibt `CMFCVisualManagerOfficeXP::OnEraseTabsButton`.)|  
|[CMFCVisualManagerOffice2003::OnEraseTabsFrame](#onerasetabsframe)|Das Framework ruft diese Methode auf, wenn sie einen Frame auf Löscht eine [CMFCBaseTabCtrl-Klasse](../../mfc/reference/cmfcbasetabctrl-class.md). (Überschreibt [CMFCVisualManager::OnEraseTabsFrame](../../mfc/reference/cmfcvisualmanager-class.md#onerasetabsframe).)|  
|[CMFCVisualManagerOffice2003::OnFillAutoHideButtonBackground](#onfillautohidebuttonbackground)|Das Framework ruft diese Methode auf, wenn es den Hintergrund einer Schaltfläche zum automatischen Ausblenden füllt. (Überschreibt [CMFCVisualManager::OnFillAutoHideButtonBackground](../../mfc/reference/cmfcvisualmanager-class.md#onfillautohidebuttonbackground).)|  
|[CMFCVisualManagerOffice2003::OnFillBarBackground](#onfillbarbackground)|Das Framework ruft diese Methode auf, wenn sie den Hintergrund des füllt eine [CBasePane-Klasse](../../mfc/reference/cbasepane-class.md) Objekt. (Überschreibt `CMFCVisualManagerOfficeXP::OnFillBarBackground`.)|  
|[CMFCVisualManagerOffice2003::OnFillButtonInterior](#onfillbuttoninterior)|Das Framework ruft diese Methode auf, wenn sie den Hintergrund einer Symbolleisten-Schaltfläche ausfüllt. (Überschreibt `CMFCVisualManagerOfficeXP::OnFillButtonInterior`.)|  
|[CMFCVisualManagerOffice2003::OnFillCommandsListBackground](#onfillcommandslistbackground)|Das Framework ruft diese Methode auf, wenn sie den Hintergrund einer Symbolleisten-Schaltfläche ausfüllt, der eine Befehlsliste gehört. (Überschreibt `CMFCVisualManagerOfficeXP::OnFillCommandsListBackground`.)|  
|[CMFCVisualManagerOffice2003::OnFillHeaderCtrlBackground](#onfillheaderctrlbackground)|Das Framework ruft diese Methode auf, wenn sie den Hintergrund eines Steuerelements Header ausfüllt. (Überschreibt [CMFCVisualManager::OnFillHeaderCtrlBackground](../../mfc/reference/cmfcvisualmanager-class.md#onfillheaderctrlbackground).)|  
|[CMFCVisualManagerOffice2003::OnFillHighlightedArea](#onfillhighlightedarea)|Das Framework ruft diese Methode auf, wenn es sich um den markierten Bereich einer Symbolleistenschaltfläche ausfüllt. (Überschreibt `CMFCVisualManagerOfficeXP::OnFillHighlightedArea`.)|  
|[CMFCVisualManagerOffice2003::OnFillOutlookBarCaption](#onfilloutlookbarcaption)|Das Framework ruft diese Methode auf, wenn sie den Hintergrund einer Outlook-Titelleiste ausfüllt. (Überschreibt [CMFCVisualManager::OnFillOutlookBarCaption](../../mfc/reference/cmfcvisualmanager-class.md#onfilloutlookbarcaption).)|  
|[CMFCVisualManagerOffice2003::OnFillOutlookPageButton](#onfilloutlookpagebutton)|Das Framework ruft diese Methode auf, wenn sie das Innere einer Outlook-Schaltfläche Seite ausfüllt. (Überschreibt [CMFCVisualManager::OnFillOutlookPageButton](../../mfc/reference/cmfcvisualmanager-class.md#onfilloutlookpagebutton).)|  
|[CMFCVisualManagerOffice2003::OnFillPopupWindowBackground](#onfillpopupwindowbackground)|Das Framework ruft diese Methode auf, wenn sie den Hintergrund eines Popupfensters ausfüllt. (Überschreibt `CMFCVisualManagerOfficeXP::OnFillPopupWindowBackground`.)|  
|[CMFCVisualManagerOffice2003::OnFillTab](#onfilltab)|Das Framework ruft diese Methode auf, wenn sie den Hintergrund eines Fensters Registerkarte ausfüllt. (Überschreibt `CMFCVisualManagerOfficeXP::OnFillTab`.)|  
|[CMFCVisualManagerOffice2003::OnFillTasksGroupInterior](#onfilltasksgroupinterior)|Das Framework ruft diese Methode auf, wenn es das innere füllt eine [CMFCTasksPaneTaskGroup-Klasse](../../mfc/reference/cmfctaskspanetaskgroup-class.md) Objekt. (Überschreibt `CMFCVisualManagerOfficeXP::OnFillTasksGroupInterior`.)|  
|[CMFCVisualManagerOffice2003::OnFillTasksPaneBackground](#onfilltaskspanebackground)|Das Framework ruft diese Methode auf, wenn sie den Hintergrund des füllt eine [CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md) Steuerelement. (Überschreibt [CMFCVisualManager::OnFillTasksPaneBackground](../../mfc/reference/cmfcvisualmanager-class.md#onfilltaskspanebackground).)|  
|[CMFCVisualManagerOffice2003::OnHighlightQuickCustomizeMenuButton](#onhighlightquickcustomizemenubutton)|Das Framework ruft diese Methode, wenn es eine hervorgehobene zeichnet Quick-anpassen-Schaltfläche. (Überschreibt `CMFCVisualManagerOfficeXP::OnHighlightQuickCustomizeMenuButton`.)|  
|[CMFCVisualManagerOffice2003::OnHighlightRarelyUsedMenuItems](#onhighlightrarelyusedmenuitems)|Das Framework ruft diese Methode auf, wenn es einen hervorgehobenen Befehl zeichnet. (Überschreibt `CMFCVisualManagerOfficeXP::OnHighlightRarelyUsedMenuItems`.)|  
|[CMFCVisualManagerOffice2003::OnUpdateSystemColors](#onupdatesystemcolors)|Das Framework ruft diese Funktion auf, wenn sich die Systemfarben ändern. (Überschreibt `CMFCVisualManagerOfficeXP::OnUpdateSystemColors`.)|  
|[CMFCVisualManagerOffice2003::SetDefaultWinXPColors](#setdefaultwinxpcolors)|Gibt an, ob die visuelle Manager sollten systemeigene Windows XP-Design-Farben verwenden oder Farben abgerufenes [GetSysColor](http://msdn.microsoft.com/library/windows/desktop/ms724371).|  
|[CMFCVisualManagerOffice2003::SetStatusBarOfficeXPLook](#setstatusbarofficexplook)|Gibt an, dass die globalen Windows XP-Designs verwendet werden soll.|  
|[CMFCVisualManagerOffice2003::SetUseGlobalTheme](#setuseglobaltheme)|Gibt an, ob die visuelle Manager ein globales Design verwendet.|  
  
## <a name="remarks"></a>Hinweise  
 Sie verwenden die `CMFCVisualManagerOffice2003` Klasse so ändern Sie das Erscheinungsbild Ihrer Anwendung, die Microsoft Office 2003 ähnelt.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die Office 2003 visuellen Manager festgelegt. Dieser Codeausschnitt ist Teil der [Desktop Warnung Demobeispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DesktopAlertDemo&6;](../../mfc/reference/codesnippet/cpp/cmfcvisualmanageroffice2003-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCBaseVisualManager](../../mfc/reference/cmfcbasevisualmanager-class.md)  
  
 [CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md)  
  
 [CMFCVisualManagerOfficeXP](../../mfc/reference/cmfcvisualmanagerofficexp-class.md)  
  
 [CMFCVisualManagerOffice2003](../../mfc/reference/cmfcvisualmanageroffice2003-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxvisualmanageroffice2003.h  
  
##  <a name="a-namedrawcomboborderwinxpa--cmfcvisualmanageroffice2003drawcomboborderwinxp"></a><a name="drawcomboborderwinxp"></a>CMFCVisualManagerOffice2003::DrawComboBorderWinXP  
 Zeichnet den Rahmen des Kombinationsfelds mit dem aktuellen Windows XP-Design.  
  
```  
virtual BOOL DrawComboBorderWinXP(
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
 Gibt `TRUE` bei aktiviertem das API-Design oder `FALSE` ist dies nicht.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namedrawcombodropbuttonwinxpa--cmfcvisualmanageroffice2003drawcombodropbuttonwinxp"></a><a name="drawcombodropbuttonwinxp"></a>CMFCVisualManagerOffice2003::DrawComboDropButtonWinXP  
 Zeichnet eine Kombinationsfeld Dropdown-Schaltfläche mit dem aktuellen Windows XP-Design.  
  
```  
virtual BOOL DrawComboDropButtonWinXP(
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
 Das umschließende Rechteck für das Kombinationsfeld Dropdown-Schaltfläche.  
  
 [in] `bDisabled`  
 Gibt an, ob die Kombinationsfeld Dropdown-Schaltfläche deaktiviert ist.  
  
 [in] `bIsDropped`  
 Gibt an, ob die Kombinationsfeld Dropdown-Schaltfläche geklickt wird.  
  
 [in] `bIsHighlighted`  
 Gibt an, ob die Dropdownschaltfläche des Kombinationsfelds markiert wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `TRUE` bei aktiviertem das API-Design oder `FALSE` ist dies nicht.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namedrawcustomizebuttona--cmfcvisualmanageroffice2003drawcustomizebutton"></a><a name="drawcustomizebutton"></a>CMFCVisualManagerOffice2003::DrawCustomizeButton  
 Zeichnet eine Schaltfläche anpassen.  
  
```  
virtual void DrawCustomizeButton(
    CDC* pDC,  
    CRect rect,  
    BOOL bIsHorz,  
    CMFCVisualManager::AFX_BUTTON_STATE state,  
    BOOL bIsCustomize,  
    BOOL bIsMoreButtons);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger auf einen Anzeigekontext.  
  
 [in] `rect`  
 Das umschließende Rechteck der Schaltfläche  
  
 [in] `bIsHorz`  
 `TRUE`Wenn die Schaltfläche horizontale ist oder `FALSE` wenn vertikale.  
  
 [in] `state`  
 Der Zustand der Schaltfläche wie er ist (reguläre, gedrückt oder hervorgehobenen) gezeichnet werden.  
  
 [in] `bIsCustomize`  
 `TRUE`Wenn das Image anpassen, scrollen Sie nach unten oder Pfeil-nach-links in dem schaltflächenrechteck gezeichnet werden soll oder `FALSE` ist dies nicht.  
  
 [in] `bIsMoreButtons`  
 `TRUE`Wenn die Horizontal oder vertikal mehr Schaltflächen anpassen Bild gezeichnet werden soll, in dem schaltflächenrechteck oder `FALSE` ist dies nicht.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namedrawpushbuttonwinxpa--cmfcvisualmanageroffice2003drawpushbuttonwinxp"></a><a name="drawpushbuttonwinxp"></a>CMFCVisualManagerOffice2003::DrawPushButtonWinXP  
 Zeichnet eine Schaltfläche mit dem aktuellen Windows XP-Design.  
  
```  
virtual BOOL DrawPushButtonWinXP(
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
 `TRUE`Wenn die API-Design aktiviert ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetbasethemecolora--cmfcvisualmanageroffice2003getbasethemecolor"></a><a name="getbasethemecolor"></a>CMFCVisualManagerOffice2003::GetBaseThemeColor  
 Ruft die Designfarbe des Basis.  
  
```  
virtual COLORREF GetBaseThemeColor();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Designfarbe des grundlegenden Designs, sofern festgelegt oder die Farbleiste Oberfläche Farbe zurück.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegethighlightmenuitemcolora--cmfcvisualmanageroffice2003gethighlightmenuitemcolor"></a><a name="gethighlightmenuitemcolor"></a>CMFCVisualManagerOffice2003::GetHighlightMenuItemColor  
 Ruft die Farbe für den markierten Menüelements ab.  
  
```  
virtual COLORREF GetHighlightMenuItemColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Farbe für den markierten Menüelements zurück.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetpropertygridgroupcolora--cmfcvisualmanageroffice2003getpropertygridgroupcolor"></a><a name="getpropertygridgroupcolor"></a>CMFCVisualManagerOffice2003::GetPropertyGridGroupColor  
 Das Framework ruft diese Methode, um die Hintergrundfarbe einer Eigenschaftenliste abgerufen.  
  
```  
virtual COLORREF GetPropertyGridGroupColor(CMFCPropertyGridCtrl* pPropList);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pPropList`  
 Ein Zeiger auf die Eigenschaftenliste, die das Framework gezeichnet wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Hintergrundfarbe des `pPropList`.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, um die Hintergrundfarbe der Eigenschaftenliste in Ihrer Anwendung anpassen.  
  
##  <a name="a-namegetpropertygridgrouptextcolora--cmfcvisualmanageroffice2003getpropertygridgrouptextcolor"></a><a name="getpropertygridgrouptextcolor"></a>CMFCVisualManagerOffice2003::GetPropertyGridGroupTextColor  
 Das Framework ruft diese Methode, um die Textfarbe der Eigenschaftenliste abzurufen.  
  
```  
virtual COLORREF GetPropertyGridGroupTextColor(CMFCPropertyGridCtrl* pPropList);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pPropList`  
 Ein Zeiger auf die Eigenschaftenliste.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Textfarbe der Liste der angegebenen Eigenschaft zurück.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, um die Textfarbe der Eigenschaftenliste in Ihrer Anwendung anpassen.  
  
##  <a name="a-namegetshowallmenuitemsheighta--cmfcvisualmanageroffice2003getshowallmenuitemsheight"></a><a name="getshowallmenuitemsheight"></a>CMFCVisualManagerOffice2003::GetShowAllMenuItemsHeight  
 Gibt die Höhe aller Menüelemente.  
  
```  
virtual int GetShowAllMenuItemsHeight(
    CDC* pDC,  
    const CSize& sizeDefault);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger auf den Gerätekontext.  
  
 [in] `sizeDefault`  
 Menü-Standardgröße.  
  
### <a name="return-value"></a>Rückgabewert  
 Als Standard wird die Höhe aller Menübilder zuzüglich der Ränder zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetsmartdockingbaseguidecolorsa--cmfcvisualmanageroffice2003getsmartdockingbaseguidecolors"></a><a name="getsmartdockingbaseguidecolors"></a>CMFCVisualManagerOffice2003::GetSmartDockingBaseGuideColors  
 Legt das angegebene Basisgruppe Hintergrundfarbe und Farbe des Rahmens.  
  
```  
virtual void GetSmartDockingBaseGuideColors(
    COLORREF& clrBaseGroupBackground,  
    COLORREF& clrBaseGroupBorder);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `clrBaseGroupBackground`  
 Ein Verweis auf eine [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) für die Hintergrundfarbe festzulegen.  
  
 [in] `clrBaseGroupBorder`  
 Ein Verweis auf eine [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) für die Farbe des Rahmens fest.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetsmartdockinghighlighttonecolora--cmfcvisualmanageroffice2003getsmartdockinghighlighttonecolor"></a><a name="getsmartdockinghighlighttonecolor"></a>CMFCVisualManagerOffice2003::GetSmartDockingHighlightToneColor  
 Gibt die Hervorhebungsfarbe für Ton zurück.  
  
```  
virtual COLORREF GetSmartDockingHighlightToneColor();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt eine [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) , enthält die Hervorhebungsfarbe Ton zu ändern.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegettabframecolorsa--cmfcvisualmanageroffice2003gettabframecolors"></a><a name="gettabframecolors"></a>CMFCVisualManagerOffice2003::GetTabFrameColors  
 Das Framework ruft diese Funktion bei der Satz von Farben für das Zeichnen einer im Registerkartenfenster abzurufen.  
  
```  
virtual void GetTabFrameColors(
    const CMFCBaseTabCtrl* pTabWnd,  
    COLORREF& clrDark,  
    COLORREF& clrBlack,  
    COLORREF& clrHighlight,  
    COLORREF& clrFace,  
    COLORREF& clrDarkShadow,  
    COLORREF& clrLight,  
    CBrush*& pbrFace,  
    CBrush*& pbrBlack);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pTabWnd`  
 Ein Zeiger auf das Fenster im Registerkartenformat, der Rahmen eine Registerkarte zeichnen.  
  
 [out] `clrDark`  
 Ein Verweis auf eine [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) , in dem diese Methode die dunklen Rahmenfarbe einer Registerkarte speichert, Parameter.  
  
 [out] `clrBlack`  
 Ein Verweis auf eine `COLORREF` , in dem diese Methode die Farbe für den Rahmen des Fensters Registerkarte speichert, Parameter. Die Standardfarbe für den Rahmen ist schwarz.  
  
 [out] `clrHighlight`  
 Ein Verweis auf eine `COLORREF` , in dem diese Methode die Farbe für die Hervorhebung-Status des Fensters Registerkarte speichert, Parameter.  
  
 [out] `clrFace`  
 Ein Verweis auf eine `COLORREF` , in dem diese Methode die Farbe für die Fläche des Fensters Registerkarte speichert, Parameter.  
  
 [out] `clrDarkShadow`  
 Ein Verweis auf eine `COLORREF` , in dem diese Methode die Farbe des Schattens des Fensters Registerkarte speichert, Parameter.  
  
 [out] `clrLight`  
 Ein Verweis auf eine `COLORREF` , in dem diese Methode die Farbe für das Licht Rand des Fensters Registerkarte speichert, Parameter.  
  
 [out] `pbrFace`  
 Ein Zeiger auf einen Verweis für einen Pinsel. Diese Methode speichert den Pinsel, den verwendet wird, um die Fläche des Fensters Registerkarte in diesem Parameter zu füllen.  
  
 [out] `pbrBlack`  
 Ein Zeiger auf einen Verweis für einen Pinsel. Diese Methode speichert den Pinsel aus, die zum Ausfüllen der schwarzen Randes des Fensters Registerkarte in diesem Parameter verwendet.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegettoolbarcustomizebuttonmargina--cmfcvisualmanageroffice2003gettoolbarcustomizebuttonmargin"></a><a name="gettoolbarcustomizebuttonmargin"></a>CMFCVisualManagerOffice2003::GetToolBarCustomizeButtonMargin  
 Ruft den Rand für das Symbolleisten-Schaltfläche anpassen.  
  
```  
virtual int GetToolBarCustomizeButtonMargin() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Rand für das Symbolleisten-Schaltfläche anpassen.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegettoolbardisabledcolora--cmfcvisualmanageroffice2003gettoolbardisabledcolor"></a><a name="gettoolbardisabledcolor"></a>CMFCVisualManagerOffice2003::GetToolbarDisabledColor  
 Ruft die Farbe deaktivierte für die Symbolleiste.  
  
```  
virtual COLORREF GetToolbarDisabledColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt eine [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) , die die deaktivierte Farbe enthält.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegettooltipinfoa--cmfcvisualmanageroffice2003gettooltipinfo"></a><a name="gettooltipinfo"></a>CMFCVisualManagerOffice2003::GetToolTipInfo  
 Aufgerufen, um QuickInfo-Informationen zu erhalten.  
  
```  
virtual BOOL GetToolTipInfo(
    CMFCToolTipInfo& params,  
    UINT nType = (UINT)(-1));
```  
  
### <a name="parameters"></a>Parameter  
 [out] `params`  
 Ein Verweis auf eine [CMFCToolTipInfo Klasse](../../mfc/reference/cmfctooltipinfo-class.md) Objekt diese Methode, in dem QuickInfo-Informationen zurückgibt.  
  
 [in] `nType`  
 Geben Sie Informationen für die QuickInfo-Informationen zurückgegeben werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `TRUE` QuickInfo-Informationen zurückgegeben wird, und `FALSE` andernfalls.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameisdefaultwinxpcolorsenableda--cmfcvisualmanageroffice2003isdefaultwinxpcolorsenabled"></a><a name="isdefaultwinxpcolorsenabled"></a>CMFCVisualManagerOffice2003::IsDefaultWinXPColorsEnabled  
 Gibt an, ob es sich bei der visuelle Manager Designfarben verwendet, die systemeigene Windows XP sind.  
  
```  
static BOOL IsDefaultWinXPColorsEnabled();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der visuelle Manager einheitliche Farben verwendet. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu systemeigenen Farben, finden Sie unter [CMFCVisualManagerOffice2003::SetDefaultWinXPColors](#setdefaultwinxpcolors).  
  
##  <a name="a-nameisdockingtabhasbordera--cmfcvisualmanageroffice2003isdockingtabhasborder"></a><a name="isdockingtabhasborder"></a>CMFCVisualManagerOffice2003::IsDockingTabHasBorder  
 Gibt zurück, ob die aktuelle visuelle Manager Rahmen um Bereiche zeichnet, die im Registerkartenformat und angedockt sind.  
  
```  
virtual BOOL IsDockingTabHasBorder();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der visuelle Manager Rahmen um Bereiche, die mit Registerkarten und angedockt sind zeichnet; `FALSE` andernfalls.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameishighlightonenotetabsa--cmfcvisualmanageroffice2003ishighlightonenotetabs"></a><a name="ishighlightonenotetabs"></a>CMFCVisualManagerOffice2003::IsHighlightOneNoteTabs  
 Gibt an, ob es sich bei OneNote Registerkarten markiert werden sollte.  
  
```  
virtual BOOL IsHighlightOneNoteTabs() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `TRUE`zurück.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameisoffsetpressedbuttona--cmfcvisualmanageroffice2003isoffsetpressedbutton"></a><a name="isoffsetpressedbutton"></a>CMFCVisualManagerOffice2003::IsOffsetPressedButton  
 Beim Zeichnen einer Symbolleisten-Schaltfläche vom Framework aufgerufen.  
  
```  
virtual BOOL IsOffsetPressedButton() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
 Die Standardimplementierung gibt `FALSE` zurück.  
  
##  <a name="a-nameisstatusbarofficexplooka--cmfcvisualmanageroffice2003isstatusbarofficexplook"></a><a name="isstatusbarofficexplook"></a>CMFCVisualManagerOffice2003::IsStatusBarOfficeXPLook  
 Gibt an, ob eine Statusleiste mit einer Darstellung des Office XP ist.  
  
```  
static BOOL __stdcall IsStatusBarOfficeXPLook();
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
 Gibt `TRUE` befindet sich eine Statusleiste mit einem Blick Office XP oder `FALSE` ist dies nicht.  
  
##  <a name="a-nameistoolbarroundshapea--cmfcvisualmanageroffice2003istoolbarroundshape"></a><a name="istoolbarroundshape"></a>CMFCVisualManagerOffice2003::IsToolbarRoundShape  
 Gibt an, ob eine angegebene Symbolleiste runden ist.  
  
```  
virtual BOOL IsToolbarRoundShape(CMFCToolBar* pToolBar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pToolBar`  
 Ein Zeiger auf die betreffende Symbolleiste.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `TRUE` wird die Symbolleiste runde oder `FALSE` ist eine Menüleiste.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameisuseglobalthemea--cmfcvisualmanageroffice2003isuseglobaltheme"></a><a name="isuseglobaltheme"></a>CMFCVisualManagerOffice2003::IsUseGlobalTheme  
 Gibt an, ob Ihre Anwendung ein Windows XP-Design verwendet.  
  
```  
static BOOL IsUseGlobalTheme();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der visuelle Manager einen Windows XP-Design verwendet. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie die Methode [CMFCVisualManagerOffice2003::SetUseGlobalTheme](#setuseglobaltheme) ändern, ob der visuelle Manager einen Windows XP-Design verwendet.  
  
##  <a name="a-nameiswindowsthemingsupporteda--cmfcvisualmanageroffice2003iswindowsthemingsupported"></a><a name="iswindowsthemingsupported"></a>CMFCVisualManagerOffice2003::IsWindowsThemingSupported  
 Gibt an, ob Windows-Designs unterstützt wird.  
  
```  
virtual BOOL IsWindowsThemingSupported() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `TRUE` Wenn Windows-Designs unterstützt wird, oder `FALSE` ist dies nicht.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameondrawautohidebuttonbordera--cmfcvisualmanageroffice2003ondrawautohidebuttonborder"></a><a name="ondrawautohidebuttonborder"></a>CMFCVisualManagerOffice2003::OnDrawAutoHideButtonBorder  
 Das Framework ruft diese Methode auf, wenn es den Rahmen einer Schaltfläche zum automatischen Ausblenden zeichnet.  
  
```  
virtual void OnDrawAutoHideButtonBorder(
    CDC* pDC,  
    CRect rectBounds,  
    CRect rectBorderSize,  
    CMFCAutoHideButton* pButton);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `rectBounds`  
 Die Größe und Position der Schaltfläche automatisch im Hintergrund.  
  
 [in] `rectBorderSize`  
 Die Größe des Rahmens.  
  
 [in] `pButton`  
 Ein Zeiger auf die Schaltfläche automatisch im Hintergrund. Das Framework ist den Rahmen für diese Schaltfläche zeichnen.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse, wenn Sie die Darstellung des Rahmens einer Schaltfläche automatisch im Hintergrund anpassen möchten. Standardmäßig füllt diese Methode einen flachen Rahmen mit der Standard-Schattenfarbe für Ihre Anwendung.  
  
 Die `rectBorderSize` Parameter enthält nicht die Koordinaten des Rahmens. Es enthält die Größe des Rahmens in der `top`, `bottom`, `left`, und `right` -Datenmember. Ein Wert kleiner oder gleich 0 gibt kein Rahmen auf dieser Seite der Schaltfläche automatisch im Hintergrund an.  
  
##  <a name="a-nameondrawbargrippera--cmfcvisualmanageroffice2003ondrawbargripper"></a><a name="ondrawbargripper"></a>CMFCVisualManagerOffice2003::OnDrawBarGripper  
 Vom Framework aufgerufen, wenn sie den Ziehpunkt für eine Steuerleiste zeichnet.  
  
```  
virtual void OnDrawBarGripper(
    CDC* pDC,  
    CRect rectGripper,  
    BOOL bHorz,  
    CBasePane* pBar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger auf den Gerätekontext für eine Steuerleiste.  
  
 [in] `rectGripper`  
 Das umschließende Rechteck für die Steuerleiste.  
  
 [in] `bHorz`  
 Ein boolescher Parameter, der angibt, ob die Steuerleiste horizontal oder vertikal angedockt ist.  
  
 [in] `pBar`  
 Ein Zeiger auf eine Steuerleiste. Visuelle Manager zeichnet die Ziehpunkte dieser Steuerleiste.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung dieser Methode wird die standardmäßige Ziehpunkte angezeigt. Um die Darstellung des ziehelements anzupassen, überschreiben Sie diese Methode in einer benutzerdefinierten Klasse aus der [CMFCVisualManagerOffice2003](../../mfc/reference/cmfcvisualmanageroffice2003-class.md) Klasse.  
  
##  <a name="a-nameondrawbrowsebuttona--cmfcvisualmanageroffice2003ondrawbrowsebutton"></a><a name="ondrawbrowsebutton"></a>CMFCVisualManagerOffice2003::OnDrawBrowseButton  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnDrawBrowseButton(
    CDC* pDC,  
    CRect rect,  
    CMFCEditBrowseCtrl* pEdit,  
    CMFCVisualManager::AFX_BUTTON_STATE state,  
    COLORREF& clrText);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 [in] `rect`  
 [in] `pEdit`  
 [in] `state`  
 [in] `clrText`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameondrawbuttonbordera--cmfcvisualmanageroffice2003ondrawbuttonborder"></a><a name="ondrawbuttonborder"></a>CMFCVisualManagerOffice2003::OnDrawButtonBorder  
 Das Framework ruft diese Methode auf, wenn sie den Rahmen einer Symbolleisten-Schaltfläche zeichnet.  
  
```  
virtual void OnDrawButtonBorder(
    CDC* pDC,  
    CMFCToolBarButton* pButton,  
    CRect rect,  
    CMFCVisualManager::AFX_BUTTON_STATE state);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger auf den Gerätekontext, der eine Symbolleisten-Schaltfläche.  
  
 [in] `pButton`  
 Ein Zeiger auf eine Symbolleisten-Schaltfläche. Das Framework zeichnet den Rahmen dieser Schaltfläche.  
  
 [in] `rect`  
 Ein Rechteck, das die Grenzen der Symbolleisten-Schaltfläche angibt.  
  
 [in] `state`  
 Enumerierten Datentyps, der den aktuellen Status der Symbolleisten-Schaltfläche angibt.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung dieser Methode wird der standardmäßigen Rahmen angezeigt. Überschreiben Sie diese Methode in einer abgeleiteten visuellen Manager anpassen die Darstellung des Rahmens für eine Symbolleisten-Schaltfläche.  
  
 Sind die möglichen Zustände einer Symbolleisten-Schaltfläche `ButtonsIsRegular`, `ButtonsIsPressed`, oder `ButtonsIsHighlighted`.  
  
##  <a name="a-nameondrawcaptionbarbordera--cmfcvisualmanageroffice2003ondrawcaptionbarborder"></a><a name="ondrawcaptionbarborder"></a>CMFCVisualManagerOffice2003::OnDrawCaptionBarBorder  
 Das Framework ruft diese Methode, wenn der Rahmen gezeichnet ein [CMFCCaptionBar Class](../../mfc/reference/cmfccaptionbar-class.md) Objekt.  
  
```  
virtual void OnDrawCaptionBarBorder(
    CDC* pDC,  
    CMFCCaptionBar* pBar,  
    CRect rect,  
    COLORREF clrBarBorder,  
    BOOL bFlatBorder);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `pBar`  
 Ein Zeiger auf eine [CMFCCaptionBar Class](../../mfc/reference/cmfccaptionbar-class.md) Objekt. Das Framework zeichnet diese Titelleiste.  
  
 [in] `rect`  
 Ein Rechteck, das die Grenzen der Titelleiste angibt.  
  
 [in] `clrBarBorder`  
 Die Farbe des Rahmens.  
  
 [in] `bFlatBorder`  
 `TRUE`Wenn der Rahmen eine flache, 2D Darstellung hat oder `FALSE` ist dies nicht.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse die Darstellung des Rahmens der Titelleiste anpassen.  
  
##  <a name="a-nameondrawcheckboxexa--cmfcvisualmanageroffice2003ondrawcheckboxex"></a><a name="ondrawcheckboxex"></a>CMFCVisualManagerOffice2003::OnDrawCheckBoxEx  
 Wird vom Framework aufgerufen, wenn ein Kontrollkästchen zeichnen.  
  
```  
virtual void OnDrawCheckBoxEx(
    CDC* pDC,  
    CRect rect,  
    int nState,  
    BOOL bHighlighted,  
    BOOL bPressed,  
    BOOL bEnabled);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Zeiger zu einem Gerätekontext.  
  
 [in] `rect`  
 Das umschließende Rechteck des Kontrollkästchens.  
  
 [in] `nState`  
 Der Status des Kontrollkästchens: 0, wenn Sie deaktiviert ist, 1, wenn aktiviert, 2, wenn gemischten aktiviert.  
  
 [in] `bHighlighted`  
 `TRUE`Wenn das Kontrollkästchen markiert ist, oder `FALSE` ist dies nicht.  
  
 [in] `bPressed`  
 `TRUE`Wenn das Kontrollkästchen gedrückt wird, oder `FALSE` ist dies nicht.  
  
 [in] `bEnabled`  
 `TRUE`Wenn das Kontrollkästchen aktiviert ist, oder `FALSE` ist dies nicht.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameondrawcombobordera--cmfcvisualmanageroffice2003ondrawcomboborder"></a><a name="ondrawcomboborder"></a>CMFCVisualManagerOffice2003::OnDrawComboBorder  
 Das Framework ruft diese Methode, wenn es den Rahmen um eine Instanz des zeichnet einen [CMFCToolBarComboBoxButton Klasse](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md).  
  
```  
virtual void OnDrawComboBorder(
    CDC* pDC,  
    CRect rect,  
    BOOL bDisabled,  
    BOOL bIsDropped,  
    BOOL bIsHighlighted,  
    CMFCToolBarComboBoxButton* pButton);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger auf den Gerätekontext des Kombinationsfelds-Schaltfläche.  
  
 [in] `rect`  
 Ein Rechteck, das die Grenzen der kombinationsfeldschaltfläche angibt.  
  
 [in] `bDisabled`  
 Ein boolescher Parameter, der angibt, ob die Kombinationsfelds-Schaltfläche nicht verfügbar ist.  
  
 [in] `bIsDropped`  
 Ein boolescher Parameter, der angibt, ob das Kombinationsfeld unten gelöscht wird.  
  
 [in] `bIsHighlighted`  
 Ein boolescher Parameter, der angibt, ob der kombinationsfeldschaltfläche hervorgehoben wird.  
  
 [in] `pButton`  
 Ein Zeiger auf ein `CMFCToolBarComboBoxButton` Objekt. Das Framework zeichnet diese Kombinationsfelds-Schaltfläche.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in der abgeleiteten visuellen Manager anpassen die Darstellung des Rahmens des Kombinationsfelds.  
  
##  <a name="a-nameondrawcombodropbuttona--cmfcvisualmanageroffice2003ondrawcombodropbutton"></a><a name="ondrawcombodropbutton"></a>CMFCVisualManagerOffice2003::OnDrawComboDropButton  
 Das Framework ruft diese Methode auf, wenn sie die Dropdownschaltfläche des zeichnet einen [CMFCToolBarComboBoxButton Klasse](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md).  
  
```  
virtual void OnDrawComboDropButton(
    CDC* pDC,  
    CRect rect,  
    BOOL bDisabled,  
    BOOL bIsDropped,  
    BOOL bIsHighlighted,  
    CMFCToolBarComboBoxButton* pButton);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `rect`  
 Ein Rechteck, das die Grenzen der Dropdown-Schaltfläche angibt.  
  
 [in] `bDisabled`  
 Ein boolescher Parameter, der angibt, ob die Dropdown-Schaltfläche nicht verfügbar ist.  
  
 [in] `bIsDropped`  
 Ein boolescher Parameter, der angibt, ob das Kombinationsfeld unten gelöscht wird.  
  
 [in] `bIsHighlighted`  
 Ein boolescher Parameter, der angibt, ob die Dropdown-Schaltfläche hervorgehoben wird.  
  
 [in] `pButton`  
 Ein Zeiger auf ein `CMFCToolBarComboBoxButton` Objekt. Das Framework zeichnet die Dropdown-Schaltfläche für dieses Kombinationsfelds-Schaltfläche  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in der abgeleiteten visuellen Manager zum Anpassen der Darstellung der Dropdown-Schaltfläche des Kombinationsfelds-Schaltfläche.  
  
##  <a name="a-nameondrawcontrolbordera--cmfcvisualmanageroffice2003ondrawcontrolborder"></a><a name="ondrawcontrolborder"></a>CMFCVisualManagerOffice2003::OnDrawControlBorder  
 Das Framework ruft diese Methode auf, wenn sie den Rand eines Steuerelements zeichnet.  
  
```  
virtual void OnDrawControlBorder(CWnd* pWndCtrl);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWndCtrl`  
 Zeiger auf eine [CWnd-Klasse](../../mfc/reference/cwnd-class.md) Objekt, das das Steuerelement für die zum Zeichnen des Rahmens darstellt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameondrawexpandingboxa--cmfcvisualmanageroffice2003ondrawexpandingbox"></a><a name="ondrawexpandingbox"></a>CMFCVisualManagerOffice2003::OnDrawExpandingBox  
 Beim Zeichnen von einem erweiterbaren Feld vom Framework aufgerufen.  
  
```  
virtual void OnDrawExpandingBox(
    CDC* pDC,  
    CRect rect,  
    BOOL bIsOpened,  
    COLORREF colorBox);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger auf die Anzeigekontext, in dem das erweiterbare Feld gezeichnet werden soll.  
  
 [in] `rect`  
 Das umschließende Rechteck des erweiterbaren Felds gezeichnet werden.  
  
 [in] `bIsOpened`  
 `TRUE`Wenn das zu zeichnende geöffnet ist, oder `FALSE` ist dies nicht.  
  
 [in] `colorBox`  
 Die Farbe des Rahmens außerhalb des Felds gezeichnet werden.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameondrawheaderctrlbordera--cmfcvisualmanageroffice2003ondrawheaderctrlborder"></a><a name="ondrawheaderctrlborder"></a>CMFCVisualManagerOffice2003::OnDrawHeaderCtrlBorder  
 Das Framework ruft diese Methode, wenn es den Rahmen um eine Instanz der zeichnet die [CMFCHeaderCtrl Klasse](../../mfc/reference/cmfcheaderctrl-class.md).  
  
```  
virtual void OnDrawHeaderCtrlBorder(
    CMFCHeaderCtrl* pCtrl,  
    CDC* pDC,  
    CRect& rect,  
    BOOL bIsPressed,  
    BOOL bIsHighlighted);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pCtrl`  
 Ein Zeiger auf eine [CMFCHeaderCtrl Klasse](../../mfc/reference/cmfcheaderctrl-class.md) Objekt. Das Framework zeichnet den Rahmen dieses Steuerelement.  
  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `rect`  
 Ein Rechteck, das die Grenzen des dem Kopfzeilen-Steuerelement angibt.  
  
 [in] `bIsPressed`  
 [in] `bIsHighlighted`  
 Ein boolescher Parameter, der angibt, ob das Kopfzeilen-Steuerelement geklickt wird.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einem abgeleiteten visual-Manager auf den Rahmen des Headersteuerelements anpassen.  
  
##  <a name="a-nameondrawmenubordera--cmfcvisualmanageroffice2003ondrawmenuborder"></a><a name="ondrawmenuborder"></a>CMFCVisualManagerOffice2003::OnDrawMenuBorder  
 Das Framework ruft diese Methode, wenn der Rahmen gezeichnet ein [CMFCPopupMenu Klasse](../../mfc/reference/cmfcpopupmenu-class.md).  
  
```  
virtual void OnDrawMenuBorder(
    CDC* pDC,  
    CMFCPopu* pMenu,  
    CRect rect);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger auf den Gerätekontext für eine [CMFCPopupMenu Klasse](../../mfc/reference/cmfcpopupmenu-class.md) Objekt.  
  
 [in] `pMenu`  
 Ein Zeiger auf eine [CMFCPopupMenu Klasse](../../mfc/reference/cmfcpopupmenu-class.md) Objekt. Das Framework zeichnet einen Rahmen um das Popup-Menü.  
  
 [in] `rect`  
 Ein Rechteck, das die Grenzen des Popupmenüs angibt.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung dieser Methode wird der Standardmenü Rahmen angezeigt. Überschreiben Sie diese Methode in einer abgeleiteten visuellen Manager zum Anpassen der Darstellung des Rahmens im Menü.  
  
##  <a name="a-nameondrawoutlookbarsplittera--cmfcvisualmanageroffice2003ondrawoutlookbarsplitter"></a><a name="ondrawoutlookbarsplitter"></a>CMFCVisualManagerOffice2003::OnDrawOutlookBarSplitter  
 Das Framework ruft diese Methode auf, wenn den Splitter für eine Outlook-Leiste gezeichnet.  
  
```  
virtual void OnDrawOutlookBarSplitter(
    CDC* pDC,  
    CRect rectSplitter);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `rectSplitter`  
 Ein Rechteck, das die Grenzen des Splitters angibt.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einem abgeleiteten visual-Manager, um die Darstellung von Bereichen auf eine Outlook-Leiste anzupassen.  
  
##  <a name="a-nameondrawoutlookpagebuttonbordera--cmfcvisualmanageroffice2003ondrawoutlookpagebuttonborder"></a><a name="ondrawoutlookpagebuttonborder"></a>CMFCVisualManagerOffice2003::OnDrawOutlookPageButtonBorder  
 Wird vom Framework aufgerufen, wenn es den Rahmen einer Outlook-Seite-Schaltfläche zeichnet.  
  
```  
virtual void OnDrawOutlookPageButtonBorder(
    CDC* pDC,  
    CRect& rectBtn,  
    BOOL bIsHighlighted,  
    BOOL bIsPressed);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `rectBtn`  
 Ein Rechteck mit der Grenze der Seitenschaltfläche Outlook.  
  
 [in] `bIsHighlighted`  
 Ein boolescher Wert, der angibt, ob die Schaltfläche hervorgehoben ist.  
  
 [in] `bIsPressed`  
 Ein boolescher Wert, der angibt, ob die Schaltfläche geklickt wird.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einen benutzerdefinierten visuellen Manager, ändern Sie die Darstellung der Schaltfläche Seite Outlook.  
  
##  <a name="a-nameondrawpanebordera--cmfcvisualmanageroffice2003ondrawpaneborder"></a><a name="ondrawpaneborder"></a>CMFCVisualManagerOffice2003::OnDrawPaneBorder  
 Das Framework ruft diese Methode, wenn der Rahmen gezeichnet ein [CPane-Klasse](../../mfc/reference/cpane-class.md) Objekt.  
  
```  
virtual void OnDrawPaneBorder(
    CDC* pDC,  
    CBasePane* pBar,  
    CRect& rect);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger auf den Gerätekontext einer Steuerleiste.  
  
 [in] `pBar`  
 Ein Zeiger auf einen Bereich. Visuelle Manager zeichnet den Rahmen dieses Bereichs.  
  
 [in] `rect`  
 Ein Rechteck, das die Grenzen des Bereichs angibt.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung dieser Methode wird der standardmäßigen Rahmen angezeigt. Überschreiben Sie diese Methode in einer abgeleiteten Klasse die Darstellung des Rahmens anpassen.  
  
##  <a name="a-nameondrawpanecaptiona--cmfcvisualmanageroffice2003ondrawpanecaption"></a><a name="ondrawpanecaption"></a>CMFCVisualManagerOffice2003::OnDrawPaneCaption  
 Das Framework ruft diese Methode auf, wenn sie eine Beschriftung für zeichnet einen [CDockablePane-Klasse](../../mfc/reference/cdockablepane-class.md) Objekt.  
  
```  
virtual COLORREF OnDrawPaneCaption(
    CDC* pDC,  
    CDockablePane* pBar,  
    BOOL bActive,  
    CRect rectCaption,  
    CRect rectButtons);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `pBar`  
 Ein Zeiger auf eine [CDockablePane-Klasse](../../mfc/reference/cdockablepane-class.md) Objekt. Das Framework zeichnet die Beschriftung für diesen Bereich.  
  
 [in] `bActive`  
 Ein boolescher Parameter, der angibt, ob die Steuerleiste aktiv ist.  
  
 [in] `rectCaption`  
 Ein Rechteck, das die Grenzen der Beschriftung angibt.  
  
 [in] `rectButtons`  
 Ein Rechteck, das die Grenzen der Titelleistenschaltflächen angibt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) Parameter, der die Textfarbe der Beschriftung angibt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameondrawpopupwindowbordera--cmfcvisualmanageroffice2003ondrawpopupwindowborder"></a><a name="ondrawpopupwindowborder"></a>CMFCVisualManagerOffice2003::OnDrawPopupWindowBorder  
 Das Framework ruft diese Methode auf, wenn sie den Rahmen eines Popup-Fensters zeichnet.  
  
```  
virtual void OnDrawPopupWindowBorder(
    CDC* pDC,  
    CRect rect);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger auf den Gerätekontext, der das Popupfenster.  
  
 [in] `rect`  
 Das umschließende Rechteck der Popup-Fenster.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameondrawpopupwindowbuttonbordera--cmfcvisualmanageroffice2003ondrawpopupwindowbuttonborder"></a><a name="ondrawpopupwindowbuttonborder"></a>CMFCVisualManagerOffice2003::OnDrawPopupWindowButtonBorder  
 Das Framework ruft diese Methode auf, wenn sie den Rahmen der Schaltfläche in einem Popupfenster zeichnet.  
  
```  
virtual void OnDrawPopupWindowButtonBorder(
    CDC* pDC,  
    CRect rectClient,  
    CMFCDesktopAlertWndButton* pButton);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger auf den Gerätekontext, der Schaltfläche.  
  
 [in] `rectClient`  
 Umschließende Rechteck der Schaltfläche.  
  
 [in] `pButton`  
 Zeiger auf die Schaltfläche (ein [CMFCDesktopAlertWndButton Klasse](../../mfc/reference/cmfcdesktopalertwndbutton-class.md) Objekt).  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameondrawpopupwindowcaptiona--cmfcvisualmanageroffice2003ondrawpopupwindowcaption"></a><a name="ondrawpopupwindowcaption"></a>CMFCVisualManagerOffice2003::OnDrawPopupWindowCaption  
 Das Framework ruft diese Methode auf, wenn sie die Beschriftung des ein Popup-Fenster zeichnet.  
  
```  
virtual COLORREF OnDrawPopupWindowCaption(
    CDC* pDC,  
    CRect rectCaption,  
    CMFCDesktopAlertWnd* pPopupWnd);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger auf den Gerätekontext, der Beschriftung.  
  
 [in] `rectCaption`  
 Umschließende Rechteck der Beschriftung.  
  
 [in] `pPopupWnd`  
 Ein Zeiger auf die Popup-Fenster für das ist die Beschriftung, gezeichnet werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Textfarbe der Beschriftung.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten visuellen Manager anpassen die Darstellung der Popup-Fenster Beschriftungen.  
  
##  <a name="a-nameondrawribbonbuttonsgroupa--cmfcvisualmanageroffice2003ondrawribbonbuttonsgroup"></a><a name="ondrawribbonbuttonsgroup"></a>CMFCVisualManagerOffice2003::OnDrawRibbonButtonsGroup  
 Das Framework ruft diese Methode auf, wenn sie eine Gruppe von Schaltflächen auf der Multifunktionsleiste zeichnet.  
  
```  
virtual COLORREF OnDrawRibbonButtonsGroup(
    CDC* pDC,  
    CMFCRibbonButtonsGroup* pGroup,  
    CRect rectGroup);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `pGroup`  
 Ein Zeiger auf eine Gruppe von Schaltflächen auf der Multifunktionsleiste. Das Framework zeichnet diese Gruppe von Schaltflächen.  
  
 [in] `rectGroup`  
 Ein Rechteck, das die Grenzen der Gruppe angibt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein reservierter Wert. Die Standardimplementierung gibt -1 zurück.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einem abgeleiteten visual-Manager, um die Darstellung einer Gruppe von Schaltflächen auf der Multifunktionsleiste anzupassen.  
  
##  <a name="a-nameondrawribboncategorycaptiona--cmfcvisualmanageroffice2003ondrawribboncategorycaption"></a><a name="ondrawribboncategorycaption"></a>CMFCVisualManagerOffice2003::OnDrawRibbonCategoryCaption  
 Das Framework ruft diese Methode auf, wenn sie auf die Titelleiste für eine Menübandkategorie zeichnet.  
  
```  
virtual COLORREF OnDrawRibbonCategoryCaption(
    CDC* pDC,  
    CMFCRibbonContextCaption* pContextCaption);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger auf den Gerätekontext, der Menübandkategorie.  
  
 [in] `pContextCaption`  
 Ein Zeiger auf die Titelleiste. Visuelle Manager zeichnet diese [CMFCRibbonContextCaption Klasse](../../mfc/reference/cmfcribboncontextcaption-class.md).  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) Parameter, der die Farbe des Texts auf der Titelleiste angibt.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse, um die Darstellung der Titelleiste für eine Menübandkategorie anzupassen.  
  
##  <a name="a-nameondrawribboncategorytaba--cmfcvisualmanageroffice2003ondrawribboncategorytab"></a><a name="ondrawribboncategorytab"></a>CMFCVisualManagerOffice2003::OnDrawRibbonCategoryTab  
 Das Framework ruft diese Methode auf, wenn sie die Registerkarte für eine Menübandkategorie zeichnet.  
  
```  
virtual COLORREF OnDrawRibbonCategoryTab(
    CDC* pDC,  
    CMFCRibbonTab* pTab,  
    BOOL bIsActive);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `pTab`  
 Ein Zeiger auf ein Objekt der Menüband-Registerkarte. Das Framework zeichnet diese Registerkarte.  
  
 [in] `bIsActive`  
 `TRUE`Wenn die Registerkarte aktiv ist oder `FALSE` ist dies nicht.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Farbe, die für den Text auf der Registerkarte des Menübands Kategorie verwendet wird.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten visuellen Manager zum Anpassen der Darstellung einer Registerkarte des Menübands Kategorie.  
  
##  <a name="a-nameondrawribbonprogressbara--cmfcvisualmanageroffice2003ondrawribbonprogressbar"></a><a name="ondrawribbonprogressbar"></a>CMFCVisualManagerOffice2003::OnDrawRibbonProgressBar  
 Das Framework ruft diese Methode auf, wenn er zeichnet einen [CMFCRibbonProgressBar Klasse](../../mfc/reference/cmfcribbonprogressbar-class.md)Objekt.  
  
```  
virtual void OnDrawRibbonProgressBar(
    CDC* pDC,  
    CMFCRibbonProgressBar* pProgress,  
    CRect rectProgress,  
    CRect rectChunk,  
    BOOL bInfiniteMode);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `pProgress`  
 Ein Zeiger auf eine [CMFCRibbonProgressBar Klasse](../../mfc/reference/cmfcribbonprogressbar-class.md) Objekt. Das Framework zeichnet diese Statusanzeige.  
  
 [in] `rectProgress`  
 Ein Rechteck, das die Grenzen der Statusanzeige angibt.  
  
 [in] `rectChunk`  
 Ein Rechteck, das die Grenzen des Bereichs der Statusanzeige um angibt.  
  
 [in] `bInfiniteMode`  
 `TRUE`Wenn die Leiste im Modus "unendlich" ist oder `FALSE` ist dies nicht. Die standardmäßige Implementierung wird dieser Parameter nicht verwendet.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse zum Anpassen der Darstellung einer Statusanzeige  
  
##  <a name="a-nameondrawribbonquickaccesstoolbarseparatora--cmfcvisualmanageroffice2003ondrawribbonquickaccesstoolbarseparator"></a><a name="ondrawribbonquickaccesstoolbarseparator"></a>CMFCVisualManagerOffice2003::OnDrawRibbonQuickAccessToolBarSeparator  
 Das Framework ruft diese Methode auf, wenn es eine Trennzeichen auf der Symbolleiste für den Schnellzugriff eines Menübands zeichnet.  
  
```  
virtual void OnDrawRibbonQuickAccessToolBarSeparator(
    CDC* pDC,  
    CMFCRibbonSeparator* pSeparator,  
    CRect rect);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `pSeparator`  
 Ein Zeiger auf eine [CMFCRibbonSeparator Klasse](../../mfc/reference/cmfcribbonseparator-class.md) Objekt. Das Framework zeichnet das Menüband-Trennzeichen.  
  
 [in] `rect`  
 Ein Rechteck, das die Grenzen des Trennzeichens angibt.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse zum Anpassen der Darstellung der Menüband-Trennzeichen auf der Symbolleiste für den Schnellzugriff.  
  
##  <a name="a-nameondrawribbonsliderchannela--cmfcvisualmanageroffice2003ondrawribbonsliderchannel"></a><a name="ondrawribbonsliderchannel"></a>CMFCVisualManagerOffice2003::OnDrawRibbonSliderChannel  
 Das Framework ruft diese Methode auf, wenn sie den Kanal des zeichnet einen [CMFCRibbonSlider Klasse](../../mfc/reference/cmfcribbonslider-class.md).  
  
```  
virtual void OnDrawRibbonSliderChannel(
    CDC* pDC,  
    CMFCRibbonSlider* pSlider,  
    CRect rect);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Zeiger zu einem Gerätekontext.  
  
 [in] `pSlider`  
 Ein Zeiger auf eine [CMFCRibbonSlider Klasse](../../mfc/reference/cmfcribbonslider-class.md) Objekt. Das Framework zeichnet den Kanal für den Schieberegler für die Multifunktionsleiste.  
  
 [in] `rect`  
 Ein Rechteck, das die Grenzen für den Kanal des Schiebereglers Menüband angibt.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse die Darstellung des Kanals des Schiebereglers Menüband anpassen.  
  
##  <a name="a-nameondrawribbonsliderthumba--cmfcvisualmanageroffice2003ondrawribbonsliderthumb"></a><a name="ondrawribbonsliderthumb"></a>CMFCVisualManagerOffice2003::OnDrawRibbonSliderThumb  
 Das Framework ruft diese Methode auf, wenn sie den Ziehpunkt des zeichnet einen [CMFCRibbonSlider Klasse](../../mfc/reference/cmfcribbonslider-class.md) Objekt  
  
```  
virtual void OnDrawRibbonSliderThumb(
    CDC* pDC,  
    CMFCRibbonSlider* pSlider,  
    CRect rect,  
    BOOL bIsHighlighted,  
    BOOL bIsPressed,  
    BOOL bIsDisabled);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `pSlider`  
 Ein Zeiger auf eine [CMFCRibbonSlider Klasse](../../mfc/reference/cmfcribbonslider-class.md). Das Framework zeichnet das Thumb-Steuerelement für den Schieberegler für die Multifunktionsleiste.  
  
 [in] `rect`  
 Ein Rechteck, das die Grenzen des Ziehpunkts für den Schieberegler Menüband angibt.  
  
 [in] `bIsHighlighted`  
 Ein boolescher Parameter, der angibt, ob das Thumb-Steuerelement hervorgehoben wird.  
  
 [in] `bIsPressed`  
 Ein boolescher Parameter, der angibt, ob das Thumb-Steuerelement geklickt wird.  
  
 [in] `bIsDisabled`  
 Ein boolescher Parameter, der angibt, ob das Thumb-Steuerelement nicht verfügbar ist.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einem abgeleiteten visual-Manager die Darstellung des Ziehpunkts für ein Menüband-Schieberegler anpassen.  
  
##  <a name="a-nameondrawribbonsliderzoombuttona--cmfcvisualmanageroffice2003ondrawribbonsliderzoombutton"></a><a name="ondrawribbonsliderzoombutton"></a>CMFCVisualManagerOffice2003::OnDrawRibbonSliderZoomButton  
 Das Framework ruft diese Methode auf, wenn sie den Zoom-Schaltflächen für zeichnet einen [CMFCRibbonSlider Klasse](../../mfc/reference/cmfcribbonslider-class.md) Objekt.  
  
```  
virtual void OnDrawRibbonSliderZoomButton(
    CDC* pDC,  
    CMFCRibbonSlider* pSlider,  
    CRect rect,  
    BOOL bIsZoomOut,  
    BOOL bIsHighlighted,  
    BOOL bIsPressed,  
    BOOL bIsDisabled);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `pSlider`  
 Ein Zeiger auf eine [CMFCRibbonSlider Klasse](../../mfc/reference/cmfcribbonslider-class.md) Objekt. Dieses Menüband zeichnet das Framework.  
  
 [in] `rect`  
 Ein Rechteck, das die Grenzen des Zoom-Schaltflächen auf dem Menüband-Schieberegler angibt.  
  
 [in] `bIsZoomOut`  
 `TRUE`Wenn die linke Maustaste mit Rahmen gezeichnet werden soll ein " ** - **" für verkleinern, oder `FALSE` , wenn das Framework, mit die rechte Maustaste zeichnen soll ein " ** + **" für vergrößern.  
  
 [in] `bIsHighlighted`  
 Ein boolescher Parameter, der angibt, ob die Schaltfläche hervorgehoben ist.  
  
 [in] `bIsPressed`  
 Ein boolescher Parameter, der angibt, ob die Schaltfläche geklickt wird.  
  
 [in] `bIsDisabled`  
 Ein boolescher Parameter, der angibt, ob die Schaltfläche nicht verfügbar ist.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig sind die Zoom-Schaltflächen auf dem Menüband-Schieberegler ein Kreis mit einem ** + ** oder ** - ** melden Sie sich in der Mitte. Überschreiben Sie diese Methode in einem abgeleiteten visual-Manager, um die Darstellung des Zoom-Schaltflächen.  
  
##  <a name="a-nameondrawribbonstatusbarpanea--cmfcvisualmanageroffice2003ondrawribbonstatusbarpane"></a><a name="ondrawribbonstatusbarpane"></a>CMFCVisualManagerOffice2003::OnDrawRibbonStatusBarPane  
 Das Framework ruft diese Methode auf, wenn sie einen Bereich auf der Statusleiste zeichnet.  
  
```  
virtual COLORREF OnDrawRibbonStatusBarPane(
    CDC* pDC,  
    CMFCRibbonStatusBar* pBar,  
    CMFCRibbonStatusBarPane* pPane);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `pBar`  
 Ein Zeiger auf der Statusleiste angezeigt, das den Bereich enthält.  
  
 [in] `pPane`  
 Ein Zeiger auf eine Leiste Statusbereich. Das Framework wird hierdurch [CMFCRibbonStatusBarPane Klasse](../../mfc/reference/cmfcribbonstatusbarpane-class.md) Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein reservierter Wert. Die Standardimplementierung gibt -1 zurück.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten visuellen Manager anpassen die Darstellung eines Bereichs in der Statusleiste angezeigt.  
  
##  <a name="a-nameondrawscrollbuttonsa--cmfcvisualmanageroffice2003ondrawscrollbuttons"></a><a name="ondrawscrollbuttons"></a>CMFCVisualManagerOffice2003::OnDrawScrollButtons  
 Das Framework ruft diese Methode auf, wenn es Bildlaufschaltflächen zeichnet.  
  
```  
virtual void OnDrawScrollButtons(
    CDC* pDC,  
    const CRect& rect,  
    const int nBorderSize,  
    int iImage,  
    BOOL bHilited);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Zeiger zu einem Gerätekontext.  
  
 [in] `rect`  
 Das umschließende Rechteck der Scroll-Schaltflächen.  
  
 [in] `nBorderSize`  
 Die Größe des Rahmens um die Bildlaufschaltflächen gezeichnet werden soll.  
  
 [in] `iImage`  
 Ein Bezeichner des Bildes, das in die Bildlaufschaltflächen zeichnen.  
  
 [in] `bHilited`  
 `TRUE`Wenn die Bildlaufschaltflächen markiert sind, oder `FALSE` ist dies nicht.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameondrawseparatora--cmfcvisualmanageroffice2003ondrawseparator"></a><a name="ondrawseparator"></a>CMFCVisualManagerOffice2003::OnDrawSeparator  
 Das Framework ruft diese Methode auf, wenn es eine Trennzeichen zeichnet.  
  
```  
virtual void OnDrawSeparator(
    CDC* pDC,  
    CBasePane* pBar,  
    CRect rect,  
    BOOL bIsHoriz);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger auf den Gerätekontext für eine Steuerleiste.  
  
 [in] `pBar`  
 Ein Zeiger auf einen Bereich, der den Trennzeichen enthält.  
  
 [in] `rect`  
 Ein Rechteck, das die Grenzen des Trennzeichens angibt.  
  
 [in] `bIsHoriz`  
 `TRUE`Wenn der Bereich horizontal angedockt ist oder `FALSE` Wenn Bereich vertikal angedockt ist.  
  
### <a name="remarks"></a>Hinweise  
 Trennzeichen werden auf Steuerleisten verwendet, um Gruppen von verwandten Symbole trennen. Die standardmäßige Implementierung für diese Methode zeigt den standardmäßigen an. Überschreiben Sie diese Methode in einem abgeleiteten visual-Manager, um die Darstellung des Strichs anzupassen.  
  
##  <a name="a-nameondrawshowallmenuitemsa--cmfcvisualmanageroffice2003ondrawshowallmenuitems"></a><a name="ondrawshowallmenuitems"></a>CMFCVisualManagerOffice2003::OnDrawShowAllMenuItems  
 Das Framework ruft diese Methode auf, wenn sie alle Elemente in einem Menü zeichnet  
  
```  
virtual void OnDrawShowAllMenuItems(
    CDC* pDC,  
    CRect rect,  
    CMFCVisualManager::AFX_BUTTON_STATE state);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Zeiger zu einem Gerätekontext.  
  
 [in] `rect`  
 Das umschließende Rechteck des Menüs gezeichnet werden.  
  
 [in] `state`  
 Der Zustand der Schaltfläche.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameondrawstatusbarpanebordera--cmfcvisualmanageroffice2003ondrawstatusbarpaneborder"></a><a name="ondrawstatusbarpaneborder"></a>CMFCVisualManagerOffice2003::OnDrawStatusBarPaneBorder  
 Das Framework ruft diese Methode, wenn es den Rahmen für zeichnet einen [CMFCStatusBar-Klasse](../../mfc/reference/cmfcstatusbar-class.md) Objekt.  
  
```  
virtual void OnDrawStatusBarPaneBorder(
    CDC* pDC,  
    CMFCStatusBar* pBar,  
    CRect rectPane,  
    UINT uiID,  
    UINT nStyle);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `pBar`  
 Ein Zeiger auf eine [CMFCStatusBar-Klasse](../../mfc/reference/cmfcstatusbar-class.md) Objekt. Das Framework zeichnet diese Status Bar-Objekt.  
  
 [in] `rectPane`  
 Ein Rechteck, das die Grenzen der Statusleiste angibt.  
  
 [in] `uiID`  
 Die ID der Statusleiste.  
  
 [in] `nStyle`  
 Der Stil der Statusleiste.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten visuellen Manager anpassen die Darstellung des Rahmens für ein `CMFCStatusBar` Objekt.  
  
##  <a name="a-nameondrawstatusbarprogressa--cmfcvisualmanageroffice2003ondrawstatusbarprogress"></a><a name="ondrawstatusbarprogress"></a>CMFCVisualManagerOffice2003::OnDrawStatusBarProgress  
 Das Framework ruft diese Methode, wenn die Statusanzeige gezeichnet wird, auf die [CMFCStatusBar-Klasse](../../mfc/reference/cmfcstatusbar-class.md) Objekt  
  
```  
virtual void OnDrawStatusBarProgress(
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
 Ein Zeiger auf den Gerätekontext für die Statusleiste  
  
 [in] `pStatusBar`  
 Die [CMFCStatusBar-Klasse](../../mfc/reference/cmfcstatusbar-class.md) -Objekt, das die Statusanzeige enthält.  
  
 [in] `rectProgress`  
 Ein Rechteck, das die Grenzen der Statusanzeige angibt.  
  
 [in] `nProgressTotal`  
 Die Gesamtanzahl für die Statusanzeige zu bewegen.  
  
 [in] `nProgressCurr`  
 Der aktuelle Fortschritt für die Statusanzeige.  
  
 [in] `clrBar`  
 Die ursprüngliche Farbe für die Statusanzeige. Der Wert ist entweder am Anfang ein Farbverlauf oder die vollständige Farbe der Statusanzeige.  
  
 [in] `clrProgressBarDest`  
 [in] `clrProgressText`  
 [in] `bProgressText`  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten visuellen Manager anpassen die Darstellung der Statusanzeige auf der Statusleiste.  
  
##  <a name="a-nameondrawstatusbarsizeboxa--cmfcvisualmanageroffice2003ondrawstatusbarsizebox"></a><a name="ondrawstatusbarsizebox"></a>CMFCVisualManagerOffice2003::OnDrawStatusBarSizeBox  
 Das Framework ruft diese Methode auf, wenn es für das Größeneinstellungsfeld zeichnet einen [CMFCStatusBar-Klasse](../../mfc/reference/cmfcstatusbar-class.md).  
  
```  
virtual void OnDrawStatusBarSizeBox(
    CDC* pDC,  
    CMFCStatusBar* pStatBar,  
    CRect rectSizeBox);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `pStatBar`  
 Ein Zeiger auf eine Statusleiste angezeigt. Das Framework zeichnet das Größeneinstellungsfeld für diese Statusleiste.  
  
 [in] `rectSizeBox`  
 Ein Rechteck, das die Grenzen des Größeneinstellungsfeld angibt.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten visuellen Manager anpassen die Darstellung von Feld eine Statusleiste.  
  
##  <a name="a-nameondrawtaba--cmfcvisualmanageroffice2003ondrawtab"></a><a name="ondrawtab"></a>CMFCVisualManagerOffice2003::OnDrawTab  
 Das Framework ruft diese Methode auf, wenn sie die Registerkarten zeichnet einen [CMFCBaseTabCtrl-Klasse](../../mfc/reference/cmfcbasetabctrl-class.md) Objekt.  
  
```  
virtual void OnDrawTab(
    CDC* pDC,  
    CRect rectTab,  
    int iTab,  
    BOOL bIsActive,  
    const CMFCBaseTabCtrl* pTabWnd);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `rectTab`  
 Ein Rechteck, das die Grenzen des Registersteuerelements angibt.  
  
 [in] `iTab`  
 Der Index der Registerkarte, die das Framework zeichnet.  
  
 [in] `bIsActive`  
 Ein boolescher Parameter, der angibt, ob die Registerkarte aktiv ist.  
  
 [in] `pTabWnd`  
 Ein Zeiger auf eine [CMFCBaseTabCtrl-Klasse](../../mfc/reference/cmfcbasetabctrl-class.md) Objekt. Das Framework zeichnet diese Registerkarten-Steuerelement.  
  
### <a name="remarks"></a>Hinweise  
 Ein `CMFCBaseTabCtrl` Objekt ruft diese Methode beim Verarbeiten der `WM_PAINT` Nachricht. Überschreiben Sie diese Methode in einer abgeleiteten Klasse zum Anpassen der Darstellung der Registerkarten.  
  
##  <a name="a-nameondrawtabsbuttonbordera--cmfcvisualmanageroffice2003ondrawtabsbuttonborder"></a><a name="ondrawtabsbuttonborder"></a>CMFCVisualManagerOffice2003::OnDrawTabsButtonBorder  
 Das Framework ruft diese Methode auf, wenn sie den Rahmen einer Registerkarte Schaltfläche zeichnet.  
  
```  
virtual void OnDrawTabsButtonBorder(
    CDC* pDC,  
    CRect& rect,  
    CMFCButton* pButton,  
    UINT uiState,  
    CMFCBaseTabCtrl* pWndTab);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `rect`  
 Ein Rechteck, das die Grenzen der Schaltfläche Registerkarte angibt.  
  
 [in] `pButton`  
 Ein Zeiger auf die [CMFCButton Klasse](../../mfc/reference/cmfcbutton-class.md) für die das Framework zeichnet den Rahmen.  
  
 [in] `uiState`  
 Der Status der Schaltfläche (siehe [CButton::GetState](../../mfc/reference/cbutton-class.md#getstate)).  
  
 [in] `pWndTab`  
 Ein Zeiger auf die Registerkarte übergeordneten Fensters.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einem abgeleiteten visual-Manager die Darstellung des Rahmens der Schaltfläche Registerkarte anpassen.  
  
##  <a name="a-nameondrawtaska--cmfcvisualmanageroffice2003ondrawtask"></a><a name="ondrawtask"></a>CMFCVisualManagerOffice2003::OnDrawTask  
 Das Framework ruft diese Methode auf, wenn er zeichnet einen [Cmfctaskspanetask-Klasse](../../mfc/reference/cmfctaskspanetask-class.md) Objekt.  
  
```  
virtual void OnDrawTask(
    CDC* pDC,  
    CMFCTasksPaneTask* pTask,  
    CImageList* pIcons,  
    BOOL bIsHighlighted = FALSE,  
    BOOL bIsSelected = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `pTask`  
 Ein Zeiger auf eine [Cmfctaskspanetask-Klasse](../../mfc/reference/cmfctaskspanetask-class.md) Objekt. Das Framework zeichnet diese Aufgabe.  
  
 [in] `pIcons`  
 Ein Zeiger auf die Bildliste des Aufgabenbereichs zugeordnet. Jede Aufgabe enthält einen Index für ein Bild in dieser Liste.  
  
 [in] `bIsHighlighted`  
 Ein boolescher Parameter, der angibt, ob die angezeigten Aufgabe hervorgehoben wird.  
  
 [in] `bIsSelected`  
 Ein boolescher Parameter, der angibt, ob die angezeigten Aufgabe ausgewählt ist.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework werden Tasks auf der Taskleiste als ein Symbol und Text angezeigt. Die `pIcons` Parameter enthält das Symbol für die Aufgabe, die durch angegebene `pTask`. Überschreiben Sie diese Methode in einer abgeleiteten Klasse zum Anpassen der Darstellung der Aufgaben in der Taskleiste.  
  
##  <a name="a-nameondrawtasksgroupareabordera--cmfcvisualmanageroffice2003ondrawtasksgroupareaborder"></a><a name="ondrawtasksgroupareaborder"></a>CMFCVisualManagerOffice2003::OnDrawTasksGroupAreaBorder  
 Das Framework ruft diese Methode, wenn er zeichnet einen Rahmen um eine Gruppe, auf einem [CMFCTasksPane Klasse](../../mfc/reference/cmfctaskspane-class.md) Objekt.  
  
```  
virtual void OnDrawTasksGroupAreaBorder(
    CDC* pDC,  
    CRect rect,  
    BOOL bSpecial = FALSE,  
    BOOL bNoTitle = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `rect`  
 Ein Rechteck, das die Grenzen des Gruppenbereichs im Aufgabenbereich angibt.  
  
 [in] `bSpecial`  
 Ein boolescher Parameter, der angibt, ob der Rahmen hervorgehoben ist. Der Wert `TRUE` gibt an, dass der Rahmen hervorgehoben ist.  
  
 [in] `bNoTitle`  
 Ein boolescher Parameter, der angibt, ob der Bereich über einen Titel verfügt. Der Wert `TRUE` gibt an, dass der Bereich nicht über einen Titel verfügt.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion in einer abgeleiteten Klasse den Rahmen um einen Bereich im Aufgabenbereich anpassen.  
  
##  <a name="a-nameondrawtasksgroupcaptiona--cmfcvisualmanageroffice2003ondrawtasksgroupcaption"></a><a name="ondrawtasksgroupcaption"></a>CMFCVisualManagerOffice2003::OnDrawTasksGroupCaption  
 Das Framework ruft diese Methode auf, wenn sie die Beschriftung für zeichnet einen [CMFCTasksPaneTaskGroup-Klasse](../../mfc/reference/cmfctaskspanetaskgroup-class.md) Objekt.  
  
```  
virtual void OnDrawTasksGroupCaption(
    CDC* pDC,  
    CMFCTasksPaneTaskGroup* pGroup,  
    BOOL bIsHighlighted = FALSE,  
    BOOL bIsSelected = FALSE,  
    BOOL bCanCollapse = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `pGroup`  
 Ein Zeiger auf eine [CMFCTasksPaneTaskGroup-Klasse](../../mfc/reference/cmfctaskspanetaskgroup-class.md) Objekt. Das Framework zeichnet die Beschriftung für diese Gruppe.  
  
 [in] `bIsHighlighted`  
 Ein boolescher Parameter, der angibt, ob die Gruppe markiert ist.  
  
 [in] `bIsSelected`  
 Ein boolescher Parameter, der angibt, ob die Gruppe gerade ausgewählt ist.  
  
 [in] `bCanCollapse`  
 Ein boolescher Parameter, der angibt, ob die Gruppe reduziert werden kann.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse zum Anpassen der Beschriftung für ein `CMFCTasksPaneTaskGroup`.  
  
##  <a name="a-nameondrawtearoffcaptiona--cmfcvisualmanageroffice2003ondrawtearoffcaption"></a><a name="ondrawtearoffcaption"></a>CMFCVisualManagerOffice2003::OnDrawTearOffCaption  
 Das Framework ruft diese Methode auf, wenn sie die Beschriftung für zeichnet einen [CMFCPopupMenu Klasse](../../mfc/reference/cmfcpopupmenu-class.md) Objekt.  
  
```  
virtual void OnDrawTearOffCaption(
    CDC* pDC,  
    CRect rect,  
    BOOL bIsActive);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `rect`  
 Ein Rechteck, das die Grenzen der Beschriftung angibt.  
  
 [in] `bIsActive`  
 `TRUE`Wenn die Beschriftung aktiv ist. `FALSE` andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird vom Framework aufgerufen wenn eine [CMFCPopupMenu Klasse](../../mfc/reference/cmfcpopupmenu-class.md) -Objekt Prozesse eine `WM_PAINT` Meldung und eine Beschriftung abtrennbare zeichnen muss.  
  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse zum Anpassen der Darstellung von Beschriftungen für abtrennbare Balken.  
  
##  <a name="a-nameonerasepopupwindowbuttona--cmfcvisualmanageroffice2003onerasepopupwindowbutton"></a><a name="onerasepopupwindowbutton"></a>CMFCVisualManagerOffice2003::OnErasePopupWindowButton  
 Das Framework ruft diese Methode auf, wenn eine Schaltfläche in einem Popupfenster gelöscht.  
  
```  
virtual void OnErasePopupWindowButton(
    CDC* pDC,  
    CRect rectClient,  
    CMFCDesktopAlertWndButton* pButton);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `rectClient`  
 Das Rechteck, das den Clientbereich des Popup-Fensters angibt.  
  
 [in] `pButton`  
 Ein Zeiger auf die Schaltfläche gelöscht werden soll.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonerasetabsareaa--cmfcvisualmanageroffice2003onerasetabsarea"></a><a name="onerasetabsarea"></a>CMFCVisualManagerOffice2003::OnEraseTabsArea  
 Das Framework ruft diese Methode, wenn die Registerkarte Clientbereich eines Fensters Registerkarte gelöscht.  
  
```  
virtual void OnEraseTabsArea(
    CDC* pDC,  
    CRect rect,  
    const CMFCBaseTabCtrl* pTabWnd);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `rect`  
 Ein Rechteck, das die Grenzen des Registerkartenbereichs angibt.  
  
 [in] `pTabWnd`  
 Ein Zeiger auf eine im Registerkartenfenster. Das Framework löscht den Registerkartenbereich für die angegebene Registerkartenfenster.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird vom Framework aufgerufen wenn eine [CMFCBaseTabCtrl-Klasse](../../mfc/reference/cmfcbasetabctrl-class.md) -Objekt Prozesse eine `WM_PAINT` Nachricht und löscht den Registerkartenbereich.  
  
 Überschreiben Sie diese Methode in einer abgeleiteten visuellen Manager zum Anpassen der Darstellung der Registerkarten.  
  
##  <a name="a-nameonerasetabsbuttona--cmfcvisualmanageroffice2003onerasetabsbutton"></a><a name="onerasetabsbutton"></a>CMFCVisualManagerOffice2003::OnEraseTabsButton  
 Das Framework ruft diese Methode auf, wenn sie den Text und das Symbol einer Schaltfläche Registerkarte löscht.  
  
```  
virtual void OnEraseTabsButton(
    CDC* pDC,  
    CRect rect,  
    CMFCButton* pButton,  
    CMFCBaseTabCtrl* pWndTab);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `rect`  
 Ein Rechteck, das die Grenzen der Schaltfläche Registerkarte angibt.  
  
 [in] `pButton`  
 Ein Zeiger auf eine Registerkarte-Schaltfläche. Das Framework löscht den Text und das Symbol für diese Schaltfläche.  
  
 [in] `pWndTab`  
 Ein Zeiger auf das Registerkarten-Steuerelement, das die Schaltfläche Registerkarte enthält.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework löscht den Text und Symbol für eine Schaltfläche bei einem [CMFCBaseTabCtrl-Klasse](../../mfc/reference/cmfcbasetabctrl-class.md) -Objekt Prozesse der `WM_ERASEBKGND` Nachricht  
  
 Überschreiben Sie diese Methode in einem abgeleiteten visual-Manager die Darstellung der Registerkartenschaltflächen anpassen.  
  
##  <a name="a-nameonerasetabsframea--cmfcvisualmanageroffice2003onerasetabsframe"></a><a name="onerasetabsframe"></a>CMFCVisualManagerOffice2003::OnEraseTabsFrame  
 Das Framework ruft diese Methode auf, wenn sie einen Frame auf Löscht eine [CMFCBaseTabCtrl-Klasse](../../mfc/reference/cmfcbasetabctrl-class.md) Objekt.  
  
```  
virtual BOOL OnEraseTabsFrame(
    CDC* pDC,  
    CRect rect,  
    const CMFCBaseTabCtrl* pTabWnd);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `rect`  
 Ein Rechteck, das die Grenzen des Fensters Registerkarte angibt.  
  
 [in] `pTabWnd`  
 Ein Zeiger auf eine im Registerkartenfenster. Das Framework Löscht einen Rahmen für diese [CMFCBaseTabCtrl-Klasse](../../mfc/reference/cmfcbasetabctrl-class.md).  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Methode erfolgreich ist oder `FALSE` ist dies nicht.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode füllt den Bereich, der durch angegebenen `rect` mit der Hintergrundfarbe der aktiven Registerkarte. Wird aufgerufen, wenn ein `CMFCBaseTabCtrl` -Objekt Prozesse eine `WM_PAINT` Nachricht und löscht einen Registerkarte Frame.  
  
##  <a name="a-nameonfillautohidebuttonbackgrounda--cmfcvisualmanageroffice2003onfillautohidebuttonbackground"></a><a name="onfillautohidebuttonbackground"></a>CMFCVisualManagerOffice2003::OnFillAutoHideButtonBackground  
 Das Framework ruft diese Methode auf, wenn es den Hintergrund einer Schaltfläche zum automatischen Ausblenden füllt.  
  
```  
virtual void OnFillAutoHideButtonBackground(
    CDC* pDC,  
    CRect rect,  
    CMFCAutoHideButton* pButton);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `rect`  
 Ein Rechteck, das die Grenzen der Schaltfläche automatisch im Hintergrund angibt.  
  
 [in] `pButton`  
 Ein Zeiger auf eine [CMFCAutoHideButton Klasse](../../mfc/reference/cmfcautohidebutton-class.md) Objekt. Das Framework füllt den Hintergrund für diese Schaltfläche automatisch im Hintergrund.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten visuellen Manager zum Anpassen der Darstellung einer Schaltfläche automatisch im Hintergrund.  
  
##  <a name="a-nameonfillbarbackgrounda--cmfcvisualmanageroffice2003onfillbarbackground"></a><a name="onfillbarbackground"></a>CMFCVisualManagerOffice2003::OnFillBarBackground  
 Das Framework ruft diese Methode auf, wenn sie den Hintergrund des füllt eine [CBasePane-Klasse](../../mfc/reference/cbasepane-class.md) Objekt.  
  
```  
virtual void OnFillBarBackground(
    CDC* pDC,  
    CBasePane* pBar,  
    CRect rectClient,  
    CRect rectClip,  
    BOOL bNCArea = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger auf den Gerätekontext für eine Steuerleiste.  
  
 [in] `pBar`  
 Ein Zeiger auf eine [CBasePane-Klasse](../../mfc/reference/cbasepane-class.md) Objekt. Das Framework füllt den Hintergrund des in diesem Bereich.  
  
 [in] `rectClient`  
 Ein Rechteck, das die Grenzen des Bereichs angibt.  
  
 [in] `rectClip`  
 Ein Rechteck, Clippingbereichs des Bereichs angibt.  
  
 [in] `bNCArea`  
 Ein reservierter Wert.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung dieser Methode füllt den Hintergrund der Leiste mit der 3d Hintergrundfarbe aus der globalen Variablen `afxGlobalData`.  
  
 Überschreiben Sie diese Methode in einem abgeleiteten visual-Manager auf den Hintergrund eines Bereichs anpassen.  
  
##  <a name="a-nameonfillbuttoninteriora--cmfcvisualmanageroffice2003onfillbuttoninterior"></a><a name="onfillbuttoninterior"></a>CMFCVisualManagerOffice2003::OnFillButtonInterior  
 Das Framework ruft diese Methode auf, wenn sie den Hintergrund einer Symbolleisten-Schaltfläche ausfüllt.  
  
```  
virtual void OnFillButtonInterior(
    CDC* pDC,  
    CMFCToolBarButton* pButton,  
    CRect rect,  
    CMFCVisualManager::AFX_BUTTON_STATE state);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger auf den Gerätekontext, der eine Symbolleisten-Schaltfläche.  
  
 [in] `pButton`  
 Ein Zeiger auf die Schaltfläche für die Framework Hintergrund gefüllt ist.  
  
 [in] `rect`  
 Ein Rechteck, das die Grenzen der Symbolleisten-Schaltfläche angibt.  
  
 [in] `state`  
 Der Status der Symbolleisten-Schaltfläche (sind die möglichen Zustände einer Symbolleisten-Schaltfläche `ButtonsIsRegular`, `ButtonsIsPressed`, oder `ButtonsIsHighlighted`).  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung dieser Methode verwendet die Standardfarbe zum ausfüllen. Überschreiben Sie diese Methode in einem abgeleiteten visual-Manager, um den Hintergrund einer Symbolleisten-Schaltfläche anzupassen.  
  
##  <a name="a-nameonfillcommandslistbackgrounda--cmfcvisualmanageroffice2003onfillcommandslistbackground"></a><a name="onfillcommandslistbackground"></a>CMFCVisualManagerOffice2003::OnFillCommandsListBackground  
 Das Framework ruft diese Methode auf, wenn sie den Hintergrund einer Symbolleisten-Schaltfläche ausfüllt, der eine Befehlsliste gehört. Dieser Befehlsliste ist Teil des im Dialogfeld Anpassen.  
  
```  
virtual COLORREF OnFillCommandsListBackground(
    CDC* pDC,  
    CRect rect,  
    BOOL bIsSelected = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `rect`  
 Ein Rechteck, das die Grenzen der Schaltfläche angibt.  
  
 [in] `bIsSelected`  
 Ein boolescher Parameter, der angibt, ob die Schaltfläche aktiviert ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Textfarbe für das Symbolleisten-Schaltfläche.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu der Liste Anpassung, finden Sie unter [CMFCToolBarButton::OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist). Die standardmäßige Implementierung für diese Methode füllt den Hintergrund basierend auf das Farbschema des aktuell ausgewählten Designs.  
  
##  <a name="a-nameonfillheaderctrlbackgrounda--cmfcvisualmanageroffice2003onfillheaderctrlbackground"></a><a name="onfillheaderctrlbackground"></a>CMFCVisualManagerOffice2003::OnFillHeaderCtrlBackground  
 Das Framework ruft diese Methode auf, wenn sie den Hintergrund eines Steuerelements Header ausfüllt.  
  
```  
virtual void OnFillHeaderCtrlBackground(
    CMFCHeaderCtrl* pCtrl,  
    CDC* pDC,  
    CRect rect);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pCtrl`  
 Ein Zeiger auf eine [CMFCHeaderCtrl Klasse](../../mfc/reference/cmfcheaderctrl-class.md) Objekt. Das Framework füllt den Hintergrund für dieses Steuerelement.  
  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `rect`  
 Ein Rechteck, das die Grenzen des dem Kopfzeilen-Steuerelement angibt.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten visuellen Manager anpassen die Darstellung von einem Kopfzeilen-Steuerelement.  
  
##  <a name="a-nameonfillhighlightedareaa--cmfcvisualmanageroffice2003onfillhighlightedarea"></a><a name="onfillhighlightedarea"></a>CMFCVisualManagerOffice2003::OnFillHighlightedArea  
 Das Framework ruft diese Methode auf, wenn es sich um den markierten Bereich einer Symbolleistenschaltfläche ausfüllt.  
  
```  
virtual void OnFillHighlightedArea(
    CDC* pDC,  
    CRect rect,  
    CBrush* pBrush,  
    CMFCToolBarButton* pButton);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Zeiger zu einem Gerätekontext.  
  
 [in] `rect`  
 Das umschließende Rechteck für den markierten Bereich ausfüllen.  
  
 [in] `pBrush`  
 Der Pinsel mit den markierten Bereich auszufüllen.  
  
 [in] `pButton`  
 Zeiger auf die [CMFCToolBarButton Klasse](../../mfc/reference/cmfctoolbarbutton-class.md) Objekt für den markierten Bereich ausfüllen.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonfilloutlookbarcaptiona--cmfcvisualmanageroffice2003onfilloutlookbarcaption"></a><a name="onfilloutlookbarcaption"></a>CMFCVisualManagerOffice2003::OnFillOutlookBarCaption  
 Das Framework ruft diese Methode auf, wenn sie den Hintergrund einer Outlook-Titelleiste ausfüllt.  
  
```  
virtual void OnFillOutlookBarCaption(
    CDC* pDC,  
    CRect rectCaption,  
    COLORREF& clrText);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `rectCaption`  
 Ein Rechteck, das die Grenzen der Titelleiste angibt.  
  
 [out] `clrText`  
 Ein Verweis auf ein `COLORREF` Objekt, zu dem diese Methode die Farbe des Texts in der Titelleiste schreibt.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung dieser Methode füllt die Titelleiste mit der Farbe für Schatten basierend auf das aktuelle Design.  
  
 Überschreiben Sie diese Methode in einem abgeleiteten visual-Manager, um die Farbe von der Outlook-Titelleiste anpassen.  
  
##  <a name="a-nameonfilloutlookpagebuttona--cmfcvisualmanageroffice2003onfilloutlookpagebutton"></a><a name="onfilloutlookpagebutton"></a>CMFCVisualManagerOffice2003::OnFillOutlookPageButton  
 Das Framework ruft diese Methode auf, wenn sie das Innere einer Outlook-Schaltfläche Seite ausfüllt.  
  
```  
virtual void OnFillOutlookPageButton(
    CDC* pDC,  
    const CRect& rect,  
    BOOL bIsHighlighted,  
    BOOL bIsPressed,  
    COLORREF& clrText);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `rect`  
 Ein Rechteck, das die Grenzen der Schaltfläche Seite Outlook angibt.  
  
 [in] `bIsHighlighted`  
 Ein boolescher Parameter, der angibt, ob die Schaltfläche hervorgehoben ist.  
  
 [in] `bIsPressed`  
 Ein boolescher Parameter, der angibt, ob die Schaltfläche geklickt wird.  
  
 [out] `clrText`  
 Ein Verweis auf ein `COLORREF` Objekt, in dem diese Methode die Textfarbe der Outlook-Seite-Schaltfläche speichert.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion in einem abgeleiteten visuellen Manager zum Anpassen der Darstellung der Schaltflächen der Outlook-Seite.  
  
##  <a name="a-nameonfillpopupwindowbackgrounda--cmfcvisualmanageroffice2003onfillpopupwindowbackground"></a><a name="onfillpopupwindowbackground"></a>CMFCVisualManagerOffice2003::OnFillPopupWindowBackground  
 Das Framework ruft diese Methode auf, wenn sie den Hintergrund eines Popupfensters ausfüllt.  
  
```  
virtual void OnFillPopupWindowBackground(
    CDC* pDC,  
    CRect rect);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `rect`  
 Ein Rechteck, das die Grenzen der Popup-Fenster angibt.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten visuellen Manager zum Anpassen der Darstellung von Popup-Fenstern.  
  
##  <a name="a-nameonfilltaba--cmfcvisualmanageroffice2003onfilltab"></a><a name="onfilltab"></a>CMFCVisualManagerOffice2003::OnFillTab  
 Das Framework ruft diese Methode auf, wenn sie den Hintergrund eines Fensters Registerkarte ausfüllt.  
  
```  
virtual void OnFillTab(
    CDC* pDC,  
    CRect rectFill,  
    CBrush* pbrFill,  
    int iTab,  
    BOOL bIsActive,  
    const CMFCBaseTabCtrl* pTabWnd);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `rectFill`  
 Ein Rechteck, das die Grenzen für das Registerkartenfenster angibt.  
  
 [in] `pbrFill`  
 Ein Zeiger auf den Pinsel, den das Framework verwendet wird, auf die Registerkartenfenster auszufüllen.  
  
 [in] `iTab`  
 Der nullbasierte Registerkartenindex einer Registerkarte für die das Framework den Hintergrund ausgefüllt wird.  
  
 [in] `bIsActive`  
 `TRUE`Wenn die Registerkarte aktiv ist oder `FALSE` ist dies nicht.  
  
 [in] `pTabWnd`  
 Ein Zeiger auf den übergeordneten Registerkarten-Steuerelement.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten visuellen Manager zum Anpassen der Darstellung der Registerkarten.  
  
##  <a name="a-nameonfilltasksgroupinteriora--cmfcvisualmanageroffice2003onfilltasksgroupinterior"></a><a name="onfilltasksgroupinterior"></a>CMFCVisualManagerOffice2003::OnFillTasksGroupInterior  
 Das Framework ruft diese Methode auf, wenn es das innere füllt eine [CMFCTasksPaneTaskGroup-Klasse](../../mfc/reference/cmfctaskspanetaskgroup-class.md) Objekt.  
  
```  
virtual void OnFillTasksGroupInterior(
    CDC* pDC,  
    CRect rect,  
    BOOL bSpecial = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `rect`  
 Ein Rechteck, das die Grenzen der Aufgabengruppe angibt.  
  
 [in] `bSpecial`  
 Ein boolescher Wert, der angibt, ob das innere mit einer besonderen Farbe ausgefüllt wird.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten visuellen Manager anpassen die Darstellung von einer Aufgabengruppe.  
  
##  <a name="a-nameonfilltaskspanebackgrounda--cmfcvisualmanageroffice2003onfilltaskspanebackground"></a><a name="onfilltaskspanebackground"></a>CMFCVisualManagerOffice2003::OnFillTasksPaneBackground  
 Das Framework ruft diese Methode auf, wenn sie den Hintergrund des füllt eine [CMFCTasksPane Klasse](../../mfc/reference/cmfctaskspane-class.md) Steuerelement.  
  
```  
virtual void OnFillTasksPaneBackground(
    CDC* pDC,  
    CRect rectWorkArea);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `rectWorkArea`  
 Ein Rechteck, das die Grenzen des Aufgabenbereichs angibt.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten visuellen Manager anpassen die Darstellung von einer [CMFCTasksPane Klasse](../../mfc/reference/cmfctaskspane-class.md) Objekt.  
  
##  <a name="a-nameonhighlightquickcustomizemenubuttona--cmfcvisualmanageroffice2003onhighlightquickcustomizemenubutton"></a><a name="onhighlightquickcustomizemenubutton"></a>CMFCVisualManagerOffice2003::OnHighlightQuickCustomizeMenuButton  
 Das Framework ruft diese Methode, wenn es eine hervorgehobene zeichnet Quick-anpassen-Schaltfläche.  
  
```  
virtual void OnHighlightQuickCustomizeMenuButton(
    CDC* pDC,  
    CMFCToolBarMenuButton* pButton,  
    CRect rect);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger auf den Gerätekontext für die Schaltfläche.  
  
 [in] `pButton`  
 Ein Zeiger auf die Schaltfläche.  
  
 [in] `rect`  
 Das umschließende Rechteck der Schaltfläche.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonhighlightrarelyusedmenuitemsa--cmfcvisualmanageroffice2003onhighlightrarelyusedmenuitems"></a><a name="onhighlightrarelyusedmenuitems"></a>CMFCVisualManagerOffice2003::OnHighlightRarelyUsedMenuItems  
 Das Framework ruft diese Methode auf, wenn es einen hervorgehobenen Befehl zeichnet.  
  
```  
virtual void OnHighlightRarelyUsedMenuItems(
    CDC* pDC,  
    CRect rectRarelyUsed);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `rectRarelyUsed`  
 Ein Rechteck, das die Grenzen der den hervorgehobenen Befehl angibt.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten visuellen Manager zum Anpassen der Darstellung der markierten Menübefehle.  
  
##  <a name="a-nameonupdatesystemcolorsa--cmfcvisualmanageroffice2003onupdatesystemcolors"></a><a name="onupdatesystemcolors"></a>CMFCVisualManagerOffice2003::OnUpdateSystemColors  
 Das Framework ruft diese Funktion auf, wenn sich die Systemfarben ändern.  
  
```  
virtual void OnUpdateSystemColors();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode als Teil der Verarbeitung der `WM_SYSCOLORCHANGE` Nachricht. Überschreiben Sie diese Methode in einer abgeleiteten visuellen Manager, wenn Sie benutzerdefinierten Code auszuführen, wenn die Farben in Ihrer Anwendung ändern möchten.  
  
##  <a name="a-namesetdefaultwinxpcolorsa--cmfcvisualmanageroffice2003setdefaultwinxpcolors"></a><a name="setdefaultwinxpcolors"></a>CMFCVisualManagerOffice2003::SetDefaultWinXPColors  
 Gibt an, ob die visuelle Manager sollten systemeigene Windows XP-Design-Farben verwenden oder Farben abgerufenes [GetSysColor](http://msdn.microsoft.com/library/windows/desktop/ms724371).  
  
```  
static void SetDefaultWinXPColors(BOOL bDefaultWinXPColors = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bDefaultWinXPColors`  
 Gibt an, ob es sich bei den visuellen Manager systemeigene Windows XP-Farben verwenden wird.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `bDefaultWinXPColors` ist `TRUE`, visuelle Manager verwendet die systemeigene Windows XP-Farben, z. B. Blau, Olivgrün oder Silber. Visuelle Manager verwenden Sie andernfalls die Farben abgerufenes `GetSysColor`. Visuelle Manager verwendet visuelle Elemente, wie z. B. `COLOR_3DFACE`, `COLOR_3DSHADOW`, `COLOR_3DHIGHLIGHT`, `COLOR_3DDKSHADOW`, und `COLOR_3DLIGHT`.  
  
 In der Standardeinstellung ein `CMFCVisualManagerOffice2003` Objekt systemeigene Windows XP Designfarben verwendet.  
  
##  <a name="a-namesetstatusbarofficexplooka--cmfcvisualmanageroffice2003setstatusbarofficexplook"></a><a name="setstatusbarofficexplook"></a>CMFCVisualManagerOffice2003::SetStatusBarOfficeXPLook  
 Gibt an, dass die globalen Windows XP-Designs verwendet werden soll.  
  
```  
static void __stdcall SetStatusBarOfficeXPLook(BOOL bStatusBarOfficeXPLook = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bStatusBarOfficeXPLook`  
 `TRUE`Wenn das globale Windows XP-Design werden sollen (Standardeinstellung), verwendet oder `FALSE` ist dies nicht.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namesetuseglobalthemea--cmfcvisualmanageroffice2003setuseglobaltheme"></a><a name="setuseglobaltheme"></a>CMFCVisualManagerOffice2003::SetUseGlobalTheme  
 Gibt an, ob die visuelle Manager ein globales Design verwendet.  
  
```  
static void SetUseGlobalTheme(BOOL bUseGlobalTheme = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bUseGlobalTheme`  
 `TRUE`Wenn den visuellen Manager, ein globales Design verwendet werden soll; `FALSE` andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein `CMFCVisualManagerOffice2003` Objekt verwendet ein globales Design, zeichnet er die GUI-Elemente mithilfe der [CMFCVisualManagerWindows Klasse](../../mfc/reference/cmfcvisualmanagerwindows-class.md).  
  
 Wenn ein `CMFCVisualManagerOffice2003` Objekt ein globales Design nicht verwendet wird, zeichnet er die GUI-Elemente mithilfe der [CMFCVisualManagerOfficeXP Klasse](../../mfc/reference/cmfcvisualmanagerofficexp-class.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCVisualManager-Klasse](../../mfc/reference/cmfcvisualmanager-class.md)   
 [CMFCVisualManagerOfficeXP-Klasse](../../mfc/reference/cmfcvisualmanagerofficexp-class.md)   
 [CMFCVisualManagerWindows-Klasse](../../mfc/reference/cmfcvisualmanagerwindows-class.md)


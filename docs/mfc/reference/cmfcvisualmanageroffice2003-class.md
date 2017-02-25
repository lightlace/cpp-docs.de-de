---
title: "CMFCVisualManagerOffice2003 Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCVisualManagerOffice2003"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCVisualManagerOffice2003 class"
ms.assetid: 115482cd-e349-450a-8dc4-c6023d092aab
caps.latest.revision: 31
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 33
---
# CMFCVisualManagerOffice2003 Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCVisualManagerOffice2003` gibt einer Anwendung eine Microsoft Office 2003\-Darstellung.  
  
## Syntax  
  
```  
class CMFCVisualManagerOffice2003 : public CMFCVisualManagerOfficeXP  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CMFCVisualManagerOffice2003::DrawComboBorderWinXP](../Topic/CMFCVisualManagerOffice2003::DrawComboBorderWinXP.md)|Zeichnet den Kombinationsfeldrahmen mithilfe des aktuellen Windows XP\-Designs.  \(Überschreibungen [CMFCVisualManager::DrawComboBorderWinXP](../Topic/CMFCVisualManager::DrawComboBorderWinXP.md).\)|  
|[CMFCVisualManagerOffice2003::DrawComboDropButtonWinXP](../Topic/CMFCVisualManagerOffice2003::DrawComboDropButtonWinXP.md)|Zeichnet eine Kombinationsfelddropdownschaltfläche mithilfe des aktuellen Windows XP\-Designs.  \(Überschreibungen [CMFCVisualManager::DrawComboDropButtonWinXP](../Topic/CMFCVisualManager::DrawComboDropButtonWinXP.md).\)|  
|[CMFCVisualManagerOffice2003::DrawCustomizeButton](../Topic/CMFCVisualManagerOffice2003::DrawCustomizeButton.md)|Zeichnet eine Anpassensschaltfläche.|  
|[CMFCVisualManagerOffice2003::DrawPushButtonWinXP](../Topic/CMFCVisualManagerOffice2003::DrawPushButtonWinXP.md)|Zeichnet eine Schaltfläche mithilfe des aktuellen Windows XP\-Designs.  \(Überschreibungen [CMFCVisualManager::DrawPushButtonWinXP](../Topic/CMFCVisualManager::DrawPushButtonWinXP.md).\)|  
|[CMFCVisualManagerOffice2003::GetBaseThemeColor](../Topic/CMFCVisualManagerOffice2003::GetBaseThemeColor.md)|Ruft die Designfarbe ab.|  
|[CMFCVisualManagerOffice2003::GetHighlightMenuItemColor](../Topic/CMFCVisualManagerOffice2003::GetHighlightMenuItemColor.md)|Ruft die Farbe ab, die für das markierte Menüelement verwendet wird.|  
|[CMFCVisualManagerOffice2003::GetPropertyGridGroupColor](../Topic/CMFCVisualManagerOffice2003::GetPropertyGridGroupColor.md)|Das Framework ruft diese Methode auf, um die Hintergrundfarbe einer Eigenschaftenliste abzurufen.  \(Überschreibungen `CMFCVisualManagerOfficeXP::GetPropertyGridGroupColor`.\)|  
|[CMFCVisualManagerOffice2003::GetPropertyGridGroupTextColor](../Topic/CMFCVisualManagerOffice2003::GetPropertyGridGroupTextColor.md)|Das Framework ruft diese Methode auf, um die Textfarbe einer Eigenschaftenliste abzurufen.  \(Überschreibungen `CMFCVisualManagerOfficeXP::GetPropertyGridGroupTextColor`.\)|  
|[CMFCVisualManagerOffice2003::GetShowAllMenuItemsHeight](../Topic/CMFCVisualManagerOffice2003::GetShowAllMenuItemsHeight.md)|Gibt die Höhe aller Menüelemente zurück.  \(Überschreibungen [CMFCVisualManager::GetShowAllMenuItemsHeight](../Topic/CMFCVisualManager::GetShowAllMenuItemsHeight.md).\)|  
|[CMFCVisualManagerOffice2003::GetSmartDockingBaseGuideColors](../Topic/CMFCVisualManagerOffice2003::GetSmartDockingBaseGuideColors.md)|Legt die angegebene Hintergrundfarbe und die Rahmenfarbe der grundlegenden Gruppe fest.  \(Überschreibungen `CMFCVisualManagerOfficeXP::GetSmartDockingBaseGuideColors`.\)|  
|[CMFCVisualManagerOffice2003::GetSmartDockingHighlightToneColor](../Topic/CMFCVisualManagerOffice2003::GetSmartDockingHighlightToneColor.md)|Ruft die Hervorhebungstonfarbe ab.  \(Überschreibungen [CMFCVisualManager::GetSmartDockingHighlightToneColor](../Topic/CMFCVisualManager::GetSmartDockingHighlightToneColor.md).\)|  
|[CMFCVisualManagerOffice2003::GetTabFrameColors](../Topic/CMFCVisualManagerOffice2003::GetTabFrameColors.md)|Das Framework ruft diese Funktion auf, wenn er den Satz von Farben für das Zeichnen eines Registerkartenfensters abrufen muss.  \(Überschreibungen [CMFCVisualManager::GetTabFrameColors](../Topic/CMFCVisualManager::GetTabFrameColors.md).\)|  
|[CMFCVisualManagerOffice2003::GetToolBarCustomizeButtonMargin](../Topic/CMFCVisualManagerOffice2003::GetToolBarCustomizeButtonMargin.md)|Ruft den Rand der Symbolleiste anpassen Schaltfläche ab.  \(Überschreibungen `CMFCVisualManager::GetToolBarCustomizeButtonMargin`.\)|  
|[CMFCVisualManagerOffice2003::GetToolbarDisabledColor](../Topic/CMFCVisualManagerOffice2003::GetToolbarDisabledColor.md)|Ruft die Behindertfarbe für die Symbolleiste ab.  \(Überschreibungen `CMFCVisualManager::GetToolbarDisabledColor`.\)|  
|[CMFCVisualManagerOffice2003::GetToolTipInfo](../Topic/CMFCVisualManagerOffice2003::GetToolTipInfo.md)|Aufgerufen durch das Framework, um QuickInfo\-Informationen abzurufen.  \(Überschreibungen [CMFCVisualManager::GetToolTipInfo](../Topic/CMFCVisualManager::GetToolTipInfo.md).\)|  
|[CMFCVisualManagerOffice2003::IsDefaultWinXPColorsEnabled](../Topic/CMFCVisualManagerOffice2003::IsDefaultWinXPColorsEnabled.md)|Gibt an, ob der visuelle Manager systemeigene Windows XP\-Designfarben verwendet.|  
|[CMFCVisualManagerOffice2003::IsDockingTabHasBorder](../Topic/CMFCVisualManagerOffice2003::IsDockingTabHasBorder.md)|Gibt zurück, ob der aktuelle visuelle Manager Rahmen um Bereiche zeichnet, die angedockt und mit der TAB\-TASTE werden.  \(Überschreibungen [CMFCVisualManager::IsDockingTabHasBorder](../Topic/CMFCVisualManager::IsDockingTabHasBorder.md).\)|  
|[CMFCVisualManagerOffice2003::IsHighlightOneNoteTabs](../Topic/CMFCVisualManagerOffice2003::IsHighlightOneNoteTabs.md)|Gibt an, ob OneNote\-Registerkarten hervorgehoben werden sollen.  \(Überschreibungen `CMFCVisualManager::IsHighlightOneNoteTabs`.\)|  
|[CMFCVisualManagerOffice2003::IsOffsetPressedButton](../Topic/CMFCVisualManagerOffice2003::IsOffsetPressedButton.md)|Aufgerufen vom Framework, wenn eine Symbolleisten\-Schaltfläche gezeichnet wird.  \(Überschreibungen `CMFCVisualManager::IsOffsetPressedButton`.\)|  
|[CMFCVisualManagerOffice2003::IsStatusBarOfficeXPLook](../Topic/CMFCVisualManagerOffice2003::IsStatusBarOfficeXPLook.md)|Gibt an, ob eine Statusleiste mit einem Office XP\-Blick gibt.|  
|[CMFCVisualManagerOffice2003::IsToolbarRoundShape](../Topic/CMFCVisualManagerOffice2003::IsToolbarRoundShape.md)|Gibt an, ob eine angegebene Symbolleiste eine öffnende Form hat.  \(Überschreibungen [CMFCVisualManager::IsToolbarRoundShape](../Topic/CMFCVisualManager::IsToolbarRoundShape.md).\)|  
|[CMFCVisualManagerOffice2003::IsUseGlobalTheme](../Topic/CMFCVisualManagerOffice2003::IsUseGlobalTheme.md)|Gibt an, ob ein globales Windows XP\-Design verwendet wird.|  
|[CMFCVisualManagerOffice2003::IsWindowsThemingSupported](../Topic/CMFCVisualManagerOffice2003::IsWindowsThemingSupported.md)|Gibt an, ob Windows\-Designverwendung unterstützt wird.  \(Überschreibungen [CMFCVisualManager::IsWindowsThemingSupported](../Topic/CMFCVisualManager::IsWindowsThemingSupported.md).\)|  
|[CMFCVisualManagerOffice2003::OnDrawAutoHideButtonBorder](../Topic/CMFCVisualManagerOffice2003::OnDrawAutoHideButtonBorder.md)|Das Framework ruft diese Methode auf, wenn der Kontext einer Schaltfläche der automatische Ausblendenen automatische Ausblenden zeichnet.  \(Überschreibungen [CMFCVisualManager::OnDrawAutoHideButtonBorder](../Topic/CMFCVisualManager::OnDrawAutoHideButtonBorder.md).\)|  
|[CMFCVisualManagerOffice2003::OnDrawBarGripper](../Topic/CMFCVisualManagerOffice2003::OnDrawBarGripper.md)|Aufgerufen vom Framework, wenn es den Ziehpunkt für eine Steuerleiste zeichnet.  \(Überschreibungen `CMFCVisualManagerOfficeXP::OnDrawBarGripper`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawBrowseButton](../Topic/CMFCVisualManagerOffice2003::OnDrawBrowseButton.md)|Das Framework ruft diese Methode auf, wenn die Schaltfläche Durchsuchen für ein Bearbeitungssteuerelement zeichnet.  \(Überschreibungen `CMFCVisualManagerOfficeXP::OnDrawBrowseButton`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawButtonBorder](../Topic/CMFCVisualManagerOffice2003::OnDrawButtonBorder.md)|Das Framework ruft diese Methode auf, wenn der Kontext einer Symbolleisten\-Schaltfläche zeichnet.  \(Überschreibungen `CMFCVisualManagerOfficeXP::OnDrawButtonBorder`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawCaptionBarBorder](../Topic/CMFCVisualManagerOffice2003::OnDrawCaptionBarBorder.md)|Das Framework ruft diese Methode auf, wenn der Kontext eines Objekts [CMFCCaptionBar\-Klasse](../../mfc/reference/cmfccaptionbar-class.md) zeichnet.  \(Überschreibungen [CMFCVisualManager::OnDrawCaptionBarBorder](../Topic/CMFCVisualManager::OnDrawCaptionBarBorder.md).\)|  
|[CMFCVisualManagerOffice2003::OnDrawCheckBoxEx](../Topic/CMFCVisualManagerOffice2003::OnDrawCheckBoxEx.md)|Das Framework ruft diese Methode auf, wenn ein Kontrollkästchen zeichnet.  \(Überschreibungen [CMFCVisualManager::OnDrawCheckBoxEx](../Topic/CMFCVisualManager::OnDrawCheckBoxEx.md).\)|  
|[CMFCVisualManagerOffice2003::OnDrawComboBorder](../Topic/CMFCVisualManagerOffice2003::OnDrawComboBorder.md)|Das Framework ruft diese Methode auf, wenn der Rahmen um ein [CMFCToolBarComboBoxButton Class](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)\-Objekt zeichnet.  \(Überschreibungen `CMFCVisualManagerOfficeXP::OnDrawComboBorder`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawComboDropButton](../Topic/CMFCVisualManagerOffice2003::OnDrawComboDropButton.md)|Das Framework ruft diese Methode auf, wenn die Ablagenschaltfläche von [CMFCToolBarComboBoxButton Class](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md) zeichnet.  \(Überschreibungen `CMFCVisualManagerOfficeXP::OnDrawComboDropButton`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawControlBorder](../Topic/CMFCVisualManagerOffice2003::OnDrawControlBorder.md)|Das Framework ruft diese Methode auf, wenn der Kontext eines Steuerelements gezeichnet wird.  \(Überschreibungen [CMFCVisualManager::OnDrawControlBorder](../Topic/CMFCVisualManager::OnDrawControlBorder.md).\)|  
|[CMFCVisualManagerOffice2003::OnDrawExpandingBox](../Topic/CMFCVisualManagerOffice2003::OnDrawExpandingBox.md)|Das Framework ruft diese Methode auf, wenn ein breiteres Feld zeichnet.  \(Überschreibungen [CMFCVisualManager::OnDrawExpandingBox](../Topic/CMFCVisualManager::OnDrawExpandingBox.md).\)|  
|[CMFCVisualManagerOffice2003::OnDrawHeaderCtrlBorder](../Topic/CMFCVisualManagerOffice2003::OnDrawHeaderCtrlBorder.md)|Das Framework ruft diese Methode auf, wenn der Rahmen um eine Instanz [CMFCHeaderCtrl Class](../../mfc/reference/cmfcheaderctrl-class.md) zeichnet.  \(Überschreibungen [CMFCVisualManager::OnDrawHeaderCtrlBorder](../Topic/CMFCVisualManager::OnDrawHeaderCtrlBorder.md).\)|  
|[CMFCVisualManagerOffice2003::OnDrawMenuBorder](../Topic/CMFCVisualManagerOffice2003::OnDrawMenuBorder.md)|Das Framework ruft diese Methode auf, wenn der Kontext von [CMFCPopupMenu Class](../../mfc/reference/cmfcpopupmenu-class.md) zeichnet.  \(Überschreibungen `CMFCVisualManagerOfficeXP::OnDrawMenuBorder`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawOutlookBarSplitter](../Topic/CMFCVisualManagerOffice2003::OnDrawOutlookBarSplitter.md)|Das Framework ruft diese Methode auf, wenn der Splitter für eine Outlook\-Leiste zeichnet.  \(Überschreibungen [CMFCVisualManager::OnDrawOutlookBarSplitter](../Topic/CMFCVisualManager::OnDrawOutlookBarSplitter.md).\)|  
|[CMFCVisualManagerOffice2003::OnDrawOutlookPageButtonBorder](../Topic/CMFCVisualManagerOffice2003::OnDrawOutlookPageButtonBorder.md)|Aufgerufen vom Framework, wenn der Kontext einer Outlook\-Seitenschaltfläche zeichnet.  \(Überschreibungen [CMFCVisualManager::OnDrawOutlookPageButtonBorder](../Topic/CMFCVisualManager::OnDrawOutlookPageButtonBorder.md).\)|  
|[CMFCVisualManagerOffice2003::OnDrawPaneBorder](../Topic/CMFCVisualManagerOffice2003::OnDrawPaneBorder.md)|Das Framework ruft diese Methode auf, wenn der Kontext eines Objekts [CPane Class](../../mfc/reference/cpane-class.md) zeichnet.  \(Überschreibungen `CMFCVisualManagerOfficeXP::OnDrawPaneBorder`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawPaneCaption](../Topic/CMFCVisualManagerOffice2003::OnDrawPaneCaption.md)|Das Framework ruft diese Methode auf, wenn eine Beschriftung für ein [CDockablePane Class](../../mfc/reference/cdockablepane-class.md)\-Objekt zeichnet.  \(Überschreibungen `CMFCVisualManagerOfficeXP::OnDrawPaneCaption`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawPopupWindowBorder](../Topic/CMFCVisualManagerOffice2003::OnDrawPopupWindowBorder.md)|Das Framework ruft diese Methode auf, wenn der Kontext eines Fensters von Popups zeichnet.  \(Überschreibungen `CMFCVisualManagerOfficeXP::OnDrawPopupWindowBorder`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawPopupWindowButtonBorder](../Topic/CMFCVisualManagerOffice2003::OnDrawPopupWindowButtonBorder.md)|Das Framework ruft diese Methode auf, wenn der Kontext einer Schaltfläche in einem Popupfenster zeichnet.  \(Überschreibungen `CMFCVisualManagerOfficeXP::OnDrawPopupWindowButtonBorder`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawPopupWindowCaption](../Topic/CMFCVisualManagerOffice2003::OnDrawPopupWindowCaption.md)|Das Framework ruft diese Methode auf, wenn die Beschriftung eines Fensters von Popups zeichnet.  \(Überschreibungen `CMFCVisualManagerOfficeXP::OnDrawPopupWindowCaption`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawRibbonButtonsGroup](../Topic/CMFCVisualManagerOffice2003::OnDrawRibbonButtonsGroup.md)|Das Framework ruft diese Methode auf, wenn eine Gruppe Schaltflächen auf dem Menüband zeichnet.  \(Überschreibungen [CMFCVisualManager::OnDrawRibbonButtonsGroup](../Topic/CMFCVisualManager::OnDrawRibbonButtonsGroup.md).\)|  
|[CMFCVisualManagerOffice2003::OnDrawRibbonCategoryCaption](../Topic/CMFCVisualManagerOffice2003::OnDrawRibbonCategoryCaption.md)|Das Framework ruft diese Methode auf, wenn die Titelleiste für eine Menübandkategorie zeichnet.  \(Überschreibungen [CMFCVisualManager::OnDrawRibbonCategoryCaption](../Topic/CMFCVisualManager::OnDrawRibbonCategoryCaption.md).\)|  
|[CMFCVisualManagerOffice2003::OnDrawRibbonCategoryTab](../Topic/CMFCVisualManagerOffice2003::OnDrawRibbonCategoryTab.md)|Das Framework ruft diese Methode auf, wenn die Registerkarte für eine Menübandkategorie zeichnet.  \(Überschreibungen [CMFCVisualManager::OnDrawRibbonCategoryTab](../Topic/CMFCVisualManager::OnDrawRibbonCategoryTab.md).\)|  
|[CMFCVisualManagerOffice2003::OnDrawRibbonProgressBar](../Topic/CMFCVisualManagerOffice2003::OnDrawRibbonProgressBar.md)|Das Framework ruft diese Methode auf, wenn [CMFCRibbonProgressBar Class](../../mfc/reference/cmfcribbonprogressbar-class.md) zeichnet.  \(Überschreibungen [CMFCVisualManager::OnDrawRibbonProgressBar](../Topic/CMFCVisualManager::OnDrawRibbonProgressBar.md).\)|  
|[CMFCVisualManagerOffice2003::OnDrawRibbonQuickAccessToolBarSeparator](../Topic/CMFCVisualManagerOffice2003::OnDrawRibbonQuickAccessToolBarSeparator.md)|Das Framework ruft diese Methode auf, wenn ein Trennzeichen auf der Symbolleiste für den Schnellzugriff eines Menübands zeichnet.  \(Überschreibungen `CMFCVisualManagerOfficeXP::OnDrawRibbonQuickAccessToolBarSeparator`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawRibbonSliderChannel](../Topic/CMFCVisualManagerOffice2003::OnDrawRibbonSliderChannel.md)|Das Framework ruft diese Methode auf, wenn der Kanal von [CMFCRibbonSlider Class](../../mfc/reference/cmfcribbonslider-class.md) zeichnet.  \(Überschreibungen [CMFCVisualManager::OnDrawRibbonSliderChannel](../Topic/CMFCVisualManager::OnDrawRibbonSliderChannel.md).\)|  
|[CMFCVisualManagerOffice2003::OnDrawRibbonSliderThumb](../Topic/CMFCVisualManagerOffice2003::OnDrawRibbonSliderThumb.md)|Das Framework ruft diese Methode auf, wenn den Ziehpunkt eines Objekts [CMFCRibbonSlider](../../mfc/reference/cmfcribbonslider-class.md) zeichnet.  \(Überschreibungen [CMFCVisualManager::OnDrawRibbonSliderThumb](../Topic/CMFCVisualManager::OnDrawRibbonSliderThumb.md).\)|  
|[CMFCVisualManagerOffice2003::OnDrawRibbonSliderZoomButton](../Topic/CMFCVisualManagerOffice2003::OnDrawRibbonSliderZoomButton.md)|Das Framework ruft diese Methode auf, wenn die Zoomschaltflächen für ein [CMFCRibbonSlider](../../mfc/reference/cmfcribbonslider-class.md)\-Objekt zeichnet.  \(Überschreibungen [CMFCVisualManager::OnDrawRibbonSliderZoomButton](../Topic/CMFCVisualManager::OnDrawRibbonSliderZoomButton.md).\)|  
|[CMFCVisualManagerOffice2003::OnDrawRibbonStatusBarPane](../Topic/CMFCVisualManagerOffice2003::OnDrawRibbonStatusBarPane.md)|Das Framework ruft diese Methode auf, wenn ein Bereich auf der Statusleiste zeichnet.  \(Überschreibungen `CMFCVisualManagerOfficeXP::OnDrawRibbonStatusBarPane`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawScrollButtons](../Topic/CMFCVisualManagerOffice2003::OnDrawScrollButtons.md)|Das Framework ruft diese Methode auf, wenn Bildlaufschaltflächen zeichnet.  \(Überschreibungen `CMFCVisualManagerOfficeXP::OnDrawScrollButtons`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawSeparator](../Topic/CMFCVisualManagerOffice2003::OnDrawSeparator.md)|Das Framework ruft diese Methode auf, wenn ein Trennzeichen zeichnet.  \(Überschreibungen `CMFCVisualManagerOfficeXP::OnDrawSeparator`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawShowAllMenuItems](../Topic/CMFCVisualManagerOffice2003::OnDrawShowAllMenuItems.md)|Das Framework ruft diese Methode auf, wenn alle Elemente in einem Menü zeichnet.  \(Überschreibungen [CMFCVisualManager::OnDrawShowAllMenuItems](../Topic/CMFCVisualManager::OnDrawShowAllMenuItems.md).\)|  
|[CMFCVisualManagerOffice2003::OnDrawStatusBarPaneBorder](../Topic/CMFCVisualManagerOffice2003::OnDrawStatusBarPaneBorder.md)|Das Framework ruft diese Methode auf, wenn der Kontext für ein [CMFCStatusBar Class](../../mfc/reference/cmfcstatusbar-class.md)\-Objekt zeichnet.  \(Überschreibungen `CMFCVisualManagerOfficeXP::OnDrawStatusBarPaneBorder`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawStatusBarProgress](../Topic/CMFCVisualManagerOffice2003::OnDrawStatusBarProgress.md)|Das Framework ruft diese Methode auf, wenn die Statusanzeige auf dem [CMFCStatusBar](../../mfc/reference/cmfcstatusbar-class.md)\-Objekt zeichnet.  \(Überschreibungen [CMFCVisualManager::OnDrawStatusBarProgress](../Topic/CMFCVisualManager::OnDrawStatusBarProgress.md).\)|  
|[CMFCVisualManagerOffice2003::OnDrawStatusBarSizeBox](../Topic/CMFCVisualManagerOffice2003::OnDrawStatusBarSizeBox.md)|Das Framework ruft diese Methode auf, wenn das Größenfeld für [CMFCStatusBar](../../mfc/reference/cmfcstatusbar-class.md) zeichnet.  \(Überschreibungen [CMFCVisualManager::OnDrawStatusBarSizeBox](../Topic/CMFCVisualManager::OnDrawStatusBarSizeBox.md).\)|  
|[CMFCVisualManagerOffice2003::OnDrawTab](../Topic/CMFCVisualManagerOffice2003::OnDrawTab.md)|Das Framework ruft diese Methode auf, wenn die Registerkarten für ein [CMFCBaseTabCtrl Class](../../mfc/reference/cmfcbasetabctrl-class.md)\-Objekt zeichnet.  \(Überschreibungen `CMFCVisualManagerOfficeXP::OnDrawTab`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawTabsButtonBorder](../Topic/CMFCVisualManagerOffice2003::OnDrawTabsButtonBorder.md)|Das Framework ruft diese Methode auf, wenn der Kontext einer Registerkartenschaltfläche zeichnet.  \(Überschreibungen `CMFCVisualManagerOfficeXP::OnDrawTabsButtonBorder`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawTask](../Topic/CMFCVisualManagerOffice2003::OnDrawTask.md)|Das Framework ruft diese Methode auf, wenn ein [CMFCTasksPaneTask Class](../../mfc/reference/cmfctaskspanetask-class.md)\-Objekt zeichnet.  \(Überschreibungen `CMFCVisualManagerOfficeXP::OnDrawTask`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawTasksGroupAreaBorder](../Topic/CMFCVisualManagerOffice2003::OnDrawTasksGroupAreaBorder.md)|Das Framework ruft diese Methode auf, wenn einen Rahmen um eine Gruppe auf einem [CMFCTasksPane Class](../../mfc/reference/cmfctaskspane-class.md)\-Objekt zeichnet.  \(Überschreibungen `CMFCVisualManagerOfficeXP::OnDrawTasksGroupAreaBorder`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawTasksGroupCaption](../Topic/CMFCVisualManagerOffice2003::OnDrawTasksGroupCaption.md)|Das Framework ruft diese Methode auf, wenn die Beschriftung für ein [CMFCTasksPaneTaskGroup Class](../../mfc/reference/cmfctaskspanetaskgroup-class.md)\-Objekt zeichnet.  \(Überschreibungen `CMFCVisualManagerOfficeXP::OnDrawTasksGroupCaption`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawTearOffCaption](../Topic/CMFCVisualManagerOffice2003::OnDrawTearOffCaption.md)|Das Framework ruft diese Methode auf, wenn die Beschriftung für ein [CMFCPopupMenu Class](../../mfc/reference/cmfcpopupmenu-class.md)\-Objekt zeichnet.  \(Überschreibungen `CMFCVisualManagerOfficeXP::OnDrawTearOffCaption`.\)|  
|[CMFCVisualManagerOffice2003::OnErasePopupWindowButton](../Topic/CMFCVisualManagerOffice2003::OnErasePopupWindowButton.md)|Das Framework ruft diese Methode auf, wenn eine Schaltfläche in einem Popupfenster gelöscht wird.  \(Überschreibungen `CMFCVisualManagerOfficeXP::OnErasePopupWindowButton`.\)|  
|[CMFCVisualManagerOffice2003::OnEraseTabsArea](../Topic/CMFCVisualManagerOffice2003::OnEraseTabsArea.md)|Das Framework ruft diese Methode auf, wenn der Registerkartenbereich eines Registerkartenfensters gelöscht wird.  \(Überschreibungen `CMFCVisualManagerOfficeXP::OnEraseTabsArea`.\)|  
|[CMFCVisualManagerOffice2003::OnEraseTabsButton](../Topic/CMFCVisualManagerOffice2003::OnEraseTabsButton.md)|Das Framework ruft diese Methode auf, wenn der Text und das Symbol einer Registerkartenschaltfläche gelöscht wird.  \(Überschreibungen `CMFCVisualManagerOfficeXP::OnEraseTabsButton`.\)|  
|[CMFCVisualManagerOffice2003::OnEraseTabsFrame](../Topic/CMFCVisualManagerOffice2003::OnEraseTabsFrame.md)|Das Framework ruft diese Methode auf, wenn Frames auf [CMFCBaseTabCtrl Class](../../mfc/reference/cmfcbasetabctrl-class.md) gelöscht wird.  \(Überschreibungen [CMFCVisualManager::OnEraseTabsFrame](../Topic/CMFCVisualManager::OnEraseTabsFrame.md).\)|  
|[CMFCVisualManagerOffice2003::OnFillAutoHideButtonBackground](../Topic/CMFCVisualManagerOffice2003::OnFillAutoHideButtonBackground.md)|Das Framework ruft diese Methode auf, wenn den Hintergrund einer Schaltfläche der automatische Ausblendenen automatische Ausblenden ausfüllt.  \(Überschreibungen [CMFCVisualManager::OnFillAutoHideButtonBackground](../Topic/CMFCVisualManager::OnFillAutoHideButtonBackground.md).\)|  
|[CMFCVisualManagerOffice2003::OnFillBarBackground](../Topic/CMFCVisualManagerOffice2003::OnFillBarBackground.md)|Das Framework ruft diese Methode auf, wenn der Hintergrund eines Objekts [CBasePane Class](../../mfc/reference/cbasepane-class.md) ausfüllt.  \(Überschreibungen `CMFCVisualManagerOfficeXP::OnFillBarBackground`.\)|  
|[CMFCVisualManagerOffice2003::OnFillButtonInterior](../Topic/CMFCVisualManagerOffice2003::OnFillButtonInterior.md)|Das Framework ruft diese Methode auf, wenn den Hintergrund einer Symbolleisten\-Schaltfläche ausfüllt.  \(Überschreibungen `CMFCVisualManagerOfficeXP::OnFillButtonInterior`.\)|  
|[CMFCVisualManagerOffice2003::OnFillCommandsListBackground](../Topic/CMFCVisualManagerOffice2003::OnFillCommandsListBackground.md)|Das Framework ruft diese Methode auf, wenn den Hintergrund einer Symbolleisten\-Schaltfläche ausfüllt, die einer Befehlsliste gehört.  \(Überschreibungen `CMFCVisualManagerOfficeXP::OnFillCommandsListBackground`.\)|  
|[CMFCVisualManagerOffice2003::OnFillHeaderCtrlBackground](../Topic/CMFCVisualManagerOffice2003::OnFillHeaderCtrlBackground.md)|Das Framework ruft diese Methode auf, wenn der Hintergrund eines Header\-Steuerelements ausfüllt.  \(Überschreibungen [CMFCVisualManager::OnFillHeaderCtrlBackground](../Topic/CMFCVisualManager::OnFillHeaderCtrlBackground.md).\)|  
|[CMFCVisualManagerOffice2003::OnFillHighlightedArea](../Topic/CMFCVisualManagerOffice2003::OnFillHighlightedArea.md)|Das Framework ruft diese Methode auf, wenn den markierten Bereich einer Symbolleistenschaltfläche ausfüllt.  \(Überschreibungen `CMFCVisualManagerOfficeXP::OnFillHighlightedArea`.\)|  
|[CMFCVisualManagerOffice2003::OnFillOutlookBarCaption](../Topic/CMFCVisualManagerOffice2003::OnFillOutlookBarCaption.md)|Das Framework ruft diese Methode auf, wenn den Hintergrund einer Outlook\-Beschriftungsleiste ausfüllt.  \(Überschreibungen [CMFCVisualManager::OnFillOutlookBarCaption](../Topic/CMFCVisualManager::OnFillOutlookBarCaption.md).\)|  
|[CMFCVisualManagerOffice2003::OnFillOutlookPageButton](../Topic/CMFCVisualManagerOffice2003::OnFillOutlookPageButton.md)|Das Framework ruft diese Methode auf, wenn das Innere einer Outlook\-Seitenschaltfläche ausfüllt.  \(Überschreibungen [CMFCVisualManager::OnFillOutlookPageButton](../Topic/CMFCVisualManager::OnFillOutlookPageButton.md).\)|  
|[CMFCVisualManagerOffice2003::OnFillPopupWindowBackground](../Topic/CMFCVisualManagerOffice2003::OnFillPopupWindowBackground.md)|Das Framework ruft diese Methode auf, wenn der Hintergrund eines Popupfensters ausfüllt.  \(Überschreibungen `CMFCVisualManagerOfficeXP::OnFillPopupWindowBackground`.\)|  
|[CMFCVisualManagerOffice2003::OnFillTab](../Topic/CMFCVisualManagerOffice2003::OnFillTab.md)|Das Framework ruft diese Methode auf, wenn der Hintergrund eines Registerkartenfensters ausfüllt.  \(Überschreibungen `CMFCVisualManagerOfficeXP::OnFillTab`.\)|  
|[CMFCVisualManagerOffice2003::OnFillTasksGroupInterior](../Topic/CMFCVisualManagerOffice2003::OnFillTasksGroupInterior.md)|Das Framework ruft diese Methode auf, wenn das Innere eines Objekts [CMFCTasksPaneTaskGroup Class](../../mfc/reference/cmfctaskspanetaskgroup-class.md) ausfüllt.  \(Überschreibungen `CMFCVisualManagerOfficeXP::OnFillTasksGroupInterior`.\)|  
|[CMFCVisualManagerOffice2003::OnFillTasksPaneBackground](../Topic/CMFCVisualManagerOffice2003::OnFillTasksPaneBackground.md)|Das Framework ruft diese Methode auf, wenn der Hintergrund eines Steuerelements [CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md) ausfüllt.  \(Überschreibungen [CMFCVisualManager::OnFillTasksPaneBackground](../Topic/CMFCVisualManager::OnFillTasksPaneBackground.md).\)|  
|[CMFCVisualManagerOffice2003::OnHighlightQuickCustomizeMenuButton](../Topic/CMFCVisualManagerOffice2003::OnHighlightQuickCustomizeMenuButton.md)|Das Framework ruft diese Methode auf, wenn ein als Quick\-anpasst Menüschaltfläche zeichnet.  \(Überschreibungen `CMFCVisualManagerOfficeXP::OnHighlightQuickCustomizeMenuButton`.\)|  
|[CMFCVisualManagerOffice2003::OnHighlightRarelyUsedMenuItems](../Topic/CMFCVisualManagerOffice2003::OnHighlightRarelyUsedMenuItems.md)|Das Framework ruft diese Methode auf, wenn ein Menübefehl markierten zeichnet.  \(Überschreibungen `CMFCVisualManagerOfficeXP::OnHighlightRarelyUsedMenuItems`.\)|  
|[CMFCVisualManagerOffice2003::OnUpdateSystemColors](../Topic/CMFCVisualManagerOffice2003::OnUpdateSystemColors.md)|Das Framework ruft diese Funktion auf, wenn die Systemfarben ändern.  \(Überschreibungen `CMFCVisualManagerOfficeXP::OnUpdateSystemColors`.\)|  
|[CMFCVisualManagerOffice2003::SetDefaultWinXPColors](../Topic/CMFCVisualManagerOffice2003::SetDefaultWinXPColors.md)|Gibt an, ob der visuelle Manager systemeigene Windows XP\-Designfarben verwenden soll, oder Farben von [GetSysColor](http://msdn.microsoft.com/library/windows/desktop/ms724371) erworben haben.|  
|[CMFCVisualManagerOffice2003::SetStatusBarOfficeXPLook](../Topic/CMFCVisualManagerOffice2003::SetStatusBarOfficeXPLook.md)|Gibt an, dass das globale Design Windows XPs verwendet werden soll.|  
|[CMFCVisualManagerOffice2003::SetUseGlobalTheme](../Topic/CMFCVisualManagerOffice2003::SetUseGlobalTheme.md)|Gibt an, ob der visuelle Manager ein globales Design verwendet.|  
  
## Hinweise  
 Sie verwenden die `CMFCVisualManagerOffice2003`\-Klasse, um das Aussehen und Verhalten der Anwendung zu ändern, Microsoft Office 2003 ähnelt.  
  
## Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie der visuellen Manager des Büros 2003 festgelegt.  Dieser Codeausschnitt ist Teil [Desktop\-wachsames Demobeispiel](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_DesktopAlertDemo#6](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_DesktopAlertDemo#6)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCBaseVisualManager](../../mfc/reference/cmfcbasevisualmanager-class.md)  
  
 [CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md)  
  
 [CMFCVisualManagerOfficeXP](../../mfc/reference/cmfcvisualmanagerofficexp-class.md)  
  
 [CMFCVisualManagerOffice2003](../../mfc/reference/cmfcvisualmanageroffice2003-class.md)  
  
## Anforderungen  
 **Header:** afxvisualmanageroffice2003.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCVisualManager Class](../../mfc/reference/cmfcvisualmanager-class.md)   
 [CMFCVisualManagerOfficeXP Class](../../mfc/reference/cmfcvisualmanagerofficexp-class.md)   
 [CMFCVisualManagerWindows Class](../../mfc/reference/cmfcvisualmanagerwindows-class.md)   
 [CMFCVisualManager::SetDefaultManager](../Topic/CMFCVisualManager::SetDefaultManager.md)
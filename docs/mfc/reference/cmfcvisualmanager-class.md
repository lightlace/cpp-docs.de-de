---
title: "CMFCVisualManager Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCVisualManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCVisualManager class"
ms.assetid: beed80f7-36a2-4d64-9f09-e807cfefc3fe
caps.latest.revision: 58
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 60
---
# CMFCVisualManager Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bietet Unterstützung zum Ändern der Darstellung der Anwendung auf einer globalen Ebene.  Die `CMFCVisualManager`\-Klasse funktioniert zusammen mit einer Klasse, die Anweisungen enthält, die GUI\-Steuerelemente der Anwendung mit einem konsistenten Format zu zeichnen.  Diese anderen Klassen bezeichnet, als visuell Manager und sie erben von `CMFCBaseVisualManager`.  
  
## Syntax  
  
```  
class CMFCVisualManager : public CMFCBaseVisualManager  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|`CMFCVisualManager::CMFCVisualManager`|Standardkonstruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCVisualManager::AdjustFrames](../Topic/CMFCVisualManager::AdjustFrames.md)||  
|[CMFCVisualManager::AdjustToolbars](../Topic/CMFCVisualManager::AdjustToolbars.md)||  
|[CMFCVisualManager::AlwaysHighlight3DTabs](../Topic/CMFCVisualManager::AlwaysHighlight3DTabs.md)|Aufgerufen vom Framework, um zu bestimmen, ob 3D\-Registerkarten immer gezeichnet werden sollen, indem eine Hervorhebungsfarbe verwendet.|  
|[CMFCVisualManager::DestroyInstance](../Topic/CMFCVisualManager::DestroyInstance.md)||  
|[CMFCVisualManager::DoDrawHeaderSortArrow](../Topic/CMFCVisualManager::DoDrawHeaderSortArrow.md)||  
|[CMFCVisualManager::DrawComboDropButtonWinXP](../Topic/CMFCVisualManager::DrawComboDropButtonWinXP.md)||  
|[CMFCVisualManager::DrawPushButtonWinXP](../Topic/CMFCVisualManager::DrawPushButtonWinXP.md)||  
|[CMFCVisualManager::DrawTextOnGlass](../Topic/CMFCVisualManager::DrawTextOnGlass.md)||  
|[CMFCVisualManager::GetAutoHideButtonTextColor](../Topic/CMFCVisualManager::GetAutoHideButtonTextColor.md)|Aufgerufen vom Framework, um die Textfarbe für eine Schaltfläche der automatische Ausblendenen automatische Ausblenden abzurufen.|  
|[CMFCVisualManager::GetButtonExtraBorder](../Topic/CMFCVisualManager::GetButtonExtraBorder.md)|Aufgerufen durch das Framework, um die erweiterte Schaltflächengröße abzurufen, die der aktuelle visuelle Manager benötigt, um eine Schaltfläche zu zeichnen.|  
|[CMFCVisualManager::GetCaptionBarTextColor](../Topic/CMFCVisualManager::GetCaptionBarTextColor.md)|Aufgerufen vom Framework, um die Textfarbe einer Titelleiste abzurufen.|  
|[CMFCVisualManager::GetDockingTabsBordersSize](../Topic/CMFCVisualManager::GetDockingTabsBordersSize.md)|Aufgerufen vom Framework, um die Größe für den Kontext einer angedockten Leiste im Registerkartenformat abzurufen.|  
|[CMFCVisualManager::GetHighlightedMenuItemTextColor](../Topic/CMFCVisualManager::GetHighlightedMenuItemTextColor.md)||  
|[CMFCVisualManager::GetInstance](../Topic/CMFCVisualManager::GetInstance.md)|Gibt einen Zeiger auf `CMFCVisualManager`\-Objekt zurück.|  
|[CMFCVisualManager::GetMDITabsBordersSize](../Topic/CMFCVisualManager::GetMDITabsBordersSize.md)|Aufgerufen durch das Framework, um die Rahmengröße des MDITabs\-Fensters abzurufen.|  
|[CMFCVisualManager::GetMenuItemTextColor](../Topic/CMFCVisualManager::GetMenuItemTextColor.md)||  
|[CMFCVisualManager::GetMenuShadowDepth](../Topic/CMFCVisualManager::GetMenuShadowDepth.md)|Gibt einen Wert zurück, der die Breite und Höhe eines Menüschattens bestimmt.|  
|[CMFCVisualManager::GetNcBtnSize](../Topic/CMFCVisualManager::GetNcBtnSize.md)|Aufgerufen durch das Framework, um die Größe des Systems Schaltflächen zu bestimmen auf Grundlage des aktuellen visuellen Manager.  Die Systemschaltflächen sind die Schaltflächen in der Titelleiste des Großrechners, die auf Befehle **Schließen**, **Minimieren**, **Maximieren** und **Wiederherstellen** zuordnen.|  
|[CMFCVisualManager::GetPopupMenuBorderSize](../Topic/CMFCVisualManager::GetPopupMenuBorderSize.md)|Aufgerufen durch das Framework, um die Größe des Rahmens für ein Popupmenü abzurufen.|  
|[CMFCVisualManager::GetPropertyGridGroupColor](../Topic/CMFCVisualManager::GetPropertyGridGroupColor.md)|Aufgerufen durch das Framework, um die Hintergrundfarbe einer Eigenschaftenliste abzurufen.|  
|[CMFCVisualManager::GetPropertyGridGroupTextColor](../Topic/CMFCVisualManager::GetPropertyGridGroupTextColor.md)|Aufgerufen vom Framework, um die Textfarbe einer Eigenschaftenliste abzurufen.|  
|[CMFCVisualManager::GetRibbonHyperlinkTextColor](../Topic/CMFCVisualManager::GetRibbonHyperlinkTextColor.md)||  
|[CMFCVisualManager::GetRibbonPopupBorderSize](../Topic/CMFCVisualManager::GetRibbonPopupBorderSize.md)||  
|[CMFCVisualManager::GetRibbonQuickAccessToolBarTextColor](../Topic/CMFCVisualManager::GetRibbonQuickAccessToolBarTextColor.md)||  
|[CMFCVisualManager::GetRibbonSliderColors](../Topic/CMFCVisualManager::GetRibbonSliderColors.md)||  
|[CMFCVisualManager::GetShowAllMenuItemsHeight](../Topic/CMFCVisualManager::GetShowAllMenuItemsHeight.md)||  
|[CMFCVisualManager::GetSmartDockingBaseGuideColors](../Topic/CMFCVisualManager::GetSmartDockingBaseGuideColors.md)||  
|[CMFCVisualManager::GetSmartDockingHighlightToneColor](../Topic/CMFCVisualManager::GetSmartDockingHighlightToneColor.md)||  
|[CMFCVisualManager::GetSmartDockingTheme](../Topic/CMFCVisualManager::GetSmartDockingTheme.md)|Gibt ein Design zurück, das verwendet wird, um intelligente andockbare Markierung anzuzeigen.|  
|[CMFCVisualManager::GetStatusBarPaneTextColor](../Topic/CMFCVisualManager::GetStatusBarPaneTextColor.md)||  
|[CMFCVisualManager::GetTabFrameColors](../Topic/CMFCVisualManager::GetTabFrameColors.md)|Aufgerufen vom Framework, um den Satz von Farben abzurufen, um zu verwenden, wenn er Registerkartenframe zeichnet.|  
|[CMFCVisualManager::GetTabTextColor](../Topic/CMFCVisualManager::GetTabTextColor.md)||  
|[CMFCVisualManager::GetToolbarButtonTextColor](../Topic/CMFCVisualManager::GetToolbarButtonTextColor.md)|Aufgerufen vom Framework, um die aktuelle Farbe des Texts in der Symbolleisten\-Schaltfläche abzurufen.  Diese Farbe richtet sich nach der aktuellen visuellen Manager und den Schaltflächenzustand.|  
|[CMFCVisualManager::GetToolbarDisabledTextColor](../Topic/CMFCVisualManager::GetToolbarDisabledTextColor.md)|Aufgerufen vom Framework, um die Farbe des Texts zu bestimmen, der auf deaktivierten Symbolleistenelementen angezeigt wird.|  
|[CMFCVisualManager::GetToolbarHighlightColor](../Topic/CMFCVisualManager::GetToolbarHighlightColor.md)||  
|[CMFCVisualManager::GetToolTipInfo](../Topic/CMFCVisualManager::GetToolTipInfo.md)||  
|[CMFCVisualManager::HasOverlappedAutoHideButtons](../Topic/CMFCVisualManager::HasOverlappedAutoHideButtons.md)|Gibt an, ob Schaltflächen der automatische Ausblendenen automatische Ausblenden überschneiden.|  
|[CMFCVisualManager::IsDockingTabHasBorder](../Topic/CMFCVisualManager::IsDockingTabHasBorder.md)|Gibt an, ob der aktuelle visuelle Manager einen Rahmen um andockbare Balken im Registerkartenformat zeichnet.|  
|[CMFCVisualManager::IsEmbossDisabledImage](../Topic/CMFCVisualManager::IsEmbossDisabledImage.md)|Gibt an, ob deaktivierte Bilder geprägt werden sollten.|  
|[CMFCVisualManager::IsFadeInactiveImage](../Topic/CMFCVisualManager::IsFadeInactiveImage.md)|Aufgerufen vom Framework, um zu bestimmen, ob inaktive Bilder auf einer Symbolleiste oder einem Menü abgeblendet angezeigt.|  
|[CMFCVisualManager::IsMenuFlatLook](../Topic/CMFCVisualManager::IsMenuFlatLook.md)|Gibt an, ob Menüschaltflächen eine vereinfachte Darstellung haben.|  
|[CMFCVisualManager::IsOfficeXPStyleMenus](../Topic/CMFCVisualManager::IsOfficeXPStyleMenus.md)|Gibt an, ob der visuelle Manager Office\-XP\-Format Menüs implementiert.|  
|[CMFCVisualManager::IsOwnerDrawCaption](../Topic/CMFCVisualManager::IsOwnerDrawCaption.md)|Gibt an, ob der aktuelle visuelle Manager Ownerdrawnbeschriftungen eines Rahmenfensters implementiert.|  
|[CMFCVisualManager::IsShadowHighlightedImage](../Topic/CMFCVisualManager::IsShadowHighlightedImage.md)|Gibt an, ob ein Bild als einen Schatten verfügt.|  
|[CMFCVisualManager::OnDrawAutoHideButtonBorder](../Topic/CMFCVisualManager::OnDrawAutoHideButtonBorder.md)|Aufgerufen vom Framework, wenn der Kontext für eine Schaltfläche der automatische Ausblendenen automatische Ausblenden zeichnet.|  
|[CMFCVisualManager::OnDrawBarGripper](../Topic/CMFCVisualManager::OnDrawBarGripper.md)|Aufgerufen vom Framework, wenn es den Ziehpunkt einer Steuerleiste zeichnet.  Der Benutzer muss auf den Ziehpunkt klicken, um die Steuerleiste zu setzen.|  
|[CMFCVisualManager::OnDrawBrowseButton](../Topic/CMFCVisualManager::OnDrawBrowseButton.md)|Aufgerufen vom Framework, wenn sie Schaltfläche Durchsuchen zeichnet, die einem Bearbeitungssteuerelement \([CMFCEditBrowseCtrl Class](../../mfc/reference/cmfceditbrowsectrl-class.md)\) gehört.|  
|[CMFCVisualManager::OnDrawButtonBorder](../Topic/CMFCVisualManager::OnDrawButtonBorder.md)|Aufgerufen vom Framework, wenn der Kontext einer Symbolleisten\-Schaltfläche zeichnet.|  
|[CMFCVisualManager::OnDrawButtonSeparator](../Topic/CMFCVisualManager::OnDrawButtonSeparator.md)||  
|[CMFCVisualManager::OnDrawCaptionBarBorder](../Topic/CMFCVisualManager::OnDrawCaptionBarBorder.md)|Aufgerufen vom Framework, wenn der Beschriftungsleisterahmen zeichnet.|  
|[CMFCVisualManager::OnDrawCaptionBarButtonBorder](../Topic/CMFCVisualManager::OnDrawCaptionBarButtonBorder.md)||  
|[CMFCVisualManager::OnDrawCaptionBarInfoArea](../Topic/CMFCVisualManager::OnDrawCaptionBarInfoArea.md)||  
|[CMFCVisualManager::OnDrawCaptionButton](../Topic/CMFCVisualManager::OnDrawCaptionButton.md)|Aufgerufen vom Framework, wenn eine Beschriftungsschaltfläche zeichnet.|  
|[CMFCVisualManager::OnDrawCheckBox](../Topic/CMFCVisualManager::OnDrawCheckBox.md)||  
|[CMFCVisualManager::OnDrawCheckBoxEx](../Topic/CMFCVisualManager::OnDrawCheckBoxEx.md)||  
|[CMFCVisualManager::OnDrawComboBorder](../Topic/CMFCVisualManager::OnDrawComboBorder.md)|Aufgerufen vom Framework, wenn der Kontext einer Kombinationsfeldschaltfläche zeichnet.|  
|[CMFCVisualManager::OnDrawComboDropButton](../Topic/CMFCVisualManager::OnDrawComboDropButton.md)|Aufgerufen vom Framework, wenn eine Kombinationsfeldablagenschaltfläche zeichnet.|  
|[CMFCVisualManager::OnDrawControlBorder](../Topic/CMFCVisualManager::OnDrawControlBorder.md)||  
|[CMFCVisualManager::OnDrawDefaultRibbonImage](../Topic/CMFCVisualManager::OnDrawDefaultRibbonImage.md)|Aufgerufen vom Framework, wenn das standardmäßige Menübandimage zeichnet.|  
|[CMFCVisualManager::OnDrawEditBorder](../Topic/CMFCVisualManager::OnDrawEditBorder.md)|Aufgerufen vom Framework, wenn es einen Rahmen um ein [CMFCToolBarEditBoxButton](../../mfc/reference/cmfctoolbareditboxbutton-class.md)\-Objekt zeichnet.|  
|[CMFCVisualManager::OnDrawExpandingBox](../Topic/CMFCVisualManager::OnDrawExpandingBox.md)||  
|[CMFCVisualManager::OnDrawFloatingToolbarBorder](../Topic/CMFCVisualManager::OnDrawFloatingToolbarBorder.md)|Aufgerufen vom Framework, wenn die Rahmen einer beweglichen Symbolleiste zeichnet.  Die unverankerte Symbolleiste ist eine Symbolleiste, die als Minirahmenfenster angezeigt wird.|  
|[CMFCVisualManager::OnDrawHeaderCtrlBorder](../Topic/CMFCVisualManager::OnDrawHeaderCtrlBorder.md)|Aufgerufen vom Framework, wenn sie den Rahmen zeichnet, der das Header\-Steuerelement enthält.|  
|[CMFCVisualManager::OnDrawHeaderCtrlSortArrow](../Topic/CMFCVisualManager::OnDrawHeaderCtrlSortArrow.md)|Aufgerufen vom Framework, wenn er den Header\-Steuerelement\-Sortierungspfeil zeichnet.|  
|[CMFCVisualManager::OnDrawMenuArrowOnCustomizeList](../Topic/CMFCVisualManager::OnDrawMenuArrowOnCustomizeList.md)||  
|[CMFCVisualManager::OnDrawMenuBorder](../Topic/CMFCVisualManager::OnDrawMenuBorder.md)|Aufgerufen vom Framework, wenn er einen Menürahmen zeichnet.|  
|[CMFCVisualManager::OnDrawMenuCheck](../Topic/CMFCVisualManager::OnDrawMenuCheck.md)||  
|[CMFCVisualManager::OnDrawMenuItemButton](../Topic/CMFCVisualManager::OnDrawMenuItemButton.md)||  
|[CMFCVisualManager::OnDrawMenuLabel](../Topic/CMFCVisualManager::OnDrawMenuLabel.md)||  
|[CMFCVisualManager::OnDrawMenuResizeBar](../Topic/CMFCVisualManager::OnDrawMenuResizeBar.md)||  
|[CMFCVisualManager::OnDrawMenuScrollButton](../Topic/CMFCVisualManager::OnDrawMenuScrollButton.md)|Aufgerufen vom Framework, wenn er eine Menübildlaufschaltfläche zeichnet.|  
|[CMFCVisualManager::OnDrawMenuShadow](../Topic/CMFCVisualManager::OnDrawMenuShadow.md)||  
|[CMFCVisualManager::OnDrawMenuSystemButton](../Topic/CMFCVisualManager::OnDrawMenuSystemButton.md)|Aufgerufen vom Framework, wenn zeichnet, Schaltflächen das Menüsystem **Schließen**, **Minimieren**, **Maximieren** und **Wiederherstellen**.|  
|[CMFCVisualManager::OnDrawMiniFrameBorder](../Topic/CMFCVisualManager::OnDrawMiniFrameBorder.md)||  
|[CMFCVisualManager::OnDrawOutlookBarSplitter](../Topic/CMFCVisualManager::OnDrawOutlookBarSplitter.md)|Aufgerufen vom Framework, wenn der Splitter für eine Outlook\-Leiste zeichnet.  Der Splitter ist eine horizontale Leiste, die für Group\-Steuerelemente verwendet wird.|  
|[CMFCVisualManager::OnDrawOutlookPageButtonBorder](../Topic/CMFCVisualManager::OnDrawOutlookPageButtonBorder.md)|Aufgerufen vom Framework, wenn der Kontext einer Outlook\-Seitenschaltfläche zeichnet.  Outlook\-Seitenschaltflächen angezeigt werden, wenn der Outlook\-Leistebereich weitere Schaltflächen enthält, als es anzeigen können.|  
|[CMFCVisualManager::OnDrawPaneBorder](../Topic/CMFCVisualManager::OnDrawPaneBorder.md)|Aufgerufen vom Framework, wenn der Kontext von [CPane Class](../../mfc/reference/cpane-class.md) zeichnet.|  
|[CMFCVisualManager::OnDrawPaneCaption](../Topic/CMFCVisualManager::OnDrawPaneCaption.md)|Aufgerufen vom Framework, wenn die Beschriftung für `CPane` zeichnet.|  
|[CMFCVisualManager::OnDrawPaneDivider](../Topic/CMFCVisualManager::OnDrawPaneDivider.md)||  
|[CMFCVisualManager::OnDrawPopupWindowBorder](../Topic/CMFCVisualManager::OnDrawPopupWindowBorder.md)||  
|[CMFCVisualManager::OnDrawPopupWindowButtonBorder](../Topic/CMFCVisualManager::OnDrawPopupWindowButtonBorder.md)||  
|[CMFCVisualManager::OnDrawPopupWindowCaption](../Topic/CMFCVisualManager::OnDrawPopupWindowCaption.md)||  
|[CMFCVisualManager::OnDrawRibbonApplicationButton](../Topic/CMFCVisualManager::OnDrawRibbonApplicationButton.md)|Aufgerufen vom Framework, wenn sie **Hauptschaltfläche** auf dem Menüband zeichnet.|  
|[CMFCVisualManager::OnDrawRibbonButtonBorder](../Topic/CMFCVisualManager::OnDrawRibbonButtonBorder.md)|Aufgerufen vom Framework, wenn sie den Kontext einer Menübandschaltfläche zeichnet.|  
|[CMFCVisualManager::OnDrawRibbonButtonsGroup](../Topic/CMFCVisualManager::OnDrawRibbonButtonsGroup.md)|Aufgerufen vom Framework, wenn sie eine Gruppe Schaltflächen auf dem Menüband zeichnet.|  
|[CMFCVisualManager::OnDrawRibbonCaption](../Topic/CMFCVisualManager::OnDrawRibbonCaption.md)|Aufgerufen vom Framework, wenn sie die Beschriftung des Großrechners zeichnet, sondern wenn die Menübandleiste mit den Frame integriert ist.|  
|[CMFCVisualManager::OnDrawRibbonCaptionButton](../Topic/CMFCVisualManager::OnDrawRibbonCaptionButton.md)|Aufgerufen vom Framework, wenn sie eine Beschriftungsschaltfläche auf der Menübandleiste zeichnet.|  
|[CMFCVisualManager::OnDrawRibbonCategory](../Topic/CMFCVisualManager::OnDrawRibbonCategory.md)|Aufgerufen vom Framework, wenn sie eine Menübandkategorie zeichnet.|  
|[CMFCVisualManager::OnDrawRibbonCategoryCaption](../Topic/CMFCVisualManager::OnDrawRibbonCategoryCaption.md)|Aufgerufen vom Framework, wenn sie die Beschriftung für eine Menübandkategorie zeichnet.|  
|[CMFCVisualManager::OnDrawRibbonCategoryScroll](../Topic/CMFCVisualManager::OnDrawRibbonCategoryScroll.md)||  
|[CMFCVisualManager::OnDrawRibbonCategoryTab](../Topic/CMFCVisualManager::OnDrawRibbonCategoryTab.md)|Aufgerufen vom Framework, wenn sie die Registerkarte für eine Menübandkategorie zeichnet.|  
|[CMFCVisualManager::OnDrawRibbonCheckBoxOnList](../Topic/CMFCVisualManager::OnDrawRibbonCheckBoxOnList.md)||  
|[CMFCVisualManager::OnDrawRibbonColorPaletteBox](../Topic/CMFCVisualManager::OnDrawRibbonColorPaletteBox.md)||  
|[CMFCVisualManager::OnDrawRibbonDefaultPaneButtonContext](../Topic/CMFCVisualManager::OnDrawRibbonDefaultPaneButtonContext.md)||  
|[CMFCVisualManager::OnDrawRibbonDefaultPaneButton](../Topic/CMFCVisualManager::OnDrawRibbonDefaultPaneButton.md)|Aufgerufen vom Framework, wenn sie die Menübandbereichsstandardschaltfläche zeichnet.  Die Standardschaltfläche angezeigt wird, wenn der Benutzer einen Favoritenmenübandbereich verkleinert wird, damit er zu klein ist, die Menübandelemente anzuzeigen.  Die Standardschaltfläche wird stattdessen gezeichnet und die Menübandelemente werden als Elemente in einem Dropdownmenü hinzugefügt.|  
|[CMFCVisualManager::OnDrawRibbonDefaultPaneButtonIndicator](../Topic/CMFCVisualManager::OnDrawRibbonDefaultPaneButtonIndicator.md)||  
|[CMFCVisualManager::OnDrawRibbonGalleryBorder](../Topic/CMFCVisualManager::OnDrawRibbonGalleryBorder.md)||  
|[CMFCVisualManager::OnDrawRibbonGalleryButton](../Topic/CMFCVisualManager::OnDrawRibbonGalleryButton.md)||  
|[CMFCVisualManager::OnDrawRibbonKeyTip](../Topic/CMFCVisualManager::OnDrawRibbonKeyTip.md)||  
|[CMFCVisualManager::OnDrawRibbonLabel](../Topic/CMFCVisualManager::OnDrawRibbonLabel.md)|Aufgerufen vom Framework, wenn die Menübandbezeichnung zeichnet.|  
|[CMFCVisualManager::OnDrawRibbonMainPanelButtonBorder](../Topic/CMFCVisualManager::OnDrawRibbonMainPanelButtonBorder.md)|Aufgerufen vom Framework, wenn sie den Kontext einer Menübandschaltfläche zeichnet, die auf dem Bereich **Hauptframe** positioniert wird.  Der Bereich **Hauptframe** ist der Bereich, der angezeigt wird, wenn ein Benutzer auf **Hauptschaltfläche** klickt.|  
|[CMFCVisualManager::OnDrawRibbonMainPanelFrame](../Topic/CMFCVisualManager::OnDrawRibbonMainPanelFrame.md)|Aufgerufen vom Framework, wenn sie den Rahmen um den Bereich **Hauptframe** zeichnet.|  
|[CMFCVisualManager::OnDrawRibbonMenuCheckFrame](../Topic/CMFCVisualManager::OnDrawRibbonMenuCheckFrame.md)||  
|[CMFCVisualManager::OnDrawRibbonPanel](../Topic/CMFCVisualManager::OnDrawRibbonPanel.md)|Aufgerufen vom Framework, wenn sie einen Favoritenmenübandbereich zeichnet.|  
|[CMFCVisualManager::OnDrawRibbonPanelCaption](../Topic/CMFCVisualManager::OnDrawRibbonPanelCaption.md)|Aufgerufen vom Framework, wenn sie die Beschriftung eines Menübandbereichs zeichnet.|  
|[CMFCVisualManager::OnDrawRibbonProgressBar](../Topic/CMFCVisualManager::OnDrawRibbonProgressBar.md)|Aufgerufen vom Framework, wenn ein [CMFCRibbonProgressBar](../../mfc/reference/cmfcribbonprogressbar-class.md)\-Objekt zeichnet.|  
|[CMFCVisualManager::OnDrawRibbonQuickAccessToolBarSeparator](../Topic/CMFCVisualManager::OnDrawRibbonQuickAccessToolBarSeparator.md)|Aufgerufen vom Framework, wenn ein Trennzeichen auf **Symbolleiste für den Schnellzugriff** eines Menübands zeichnet.|  
|[CMFCVisualManager::OnDrawRibbonRecentFilesFrame](../Topic/CMFCVisualManager::OnDrawRibbonRecentFilesFrame.md)|Aufgerufen vom Framework, wenn sie Rahmen um eine neue Dateiliste zeichnet.|  
|[CMFCVisualManager::OnDrawRibbonSliderChannel](../Topic/CMFCVisualManager::OnDrawRibbonSliderChannel.md)|Aufgerufen vom Framework, wenn der Kanal [CMFCRibbonSlider](../../mfc/reference/cmfcribbonslider-class.md) eines Objekts gezeichnet werden.|  
|[CMFCVisualManager::OnDrawRibbonSliderThumb](../Topic/CMFCVisualManager::OnDrawRibbonSliderThumb.md)|Aufgerufen vom Framework, wenn es den Ziehpunkt eines Objekts `CMFCRibbonSlider` zeichnet.|  
|[CMFCVisualManager::OnDrawRibbonSliderZoomButton](../Topic/CMFCVisualManager::OnDrawRibbonSliderZoomButton.md)|Aufgerufen vom Framework, wenn die Zoomschaltflächen eines Objekts `CMFCRibbonSlider` zeichnet.|  
|[CMFCVisualManager::OnDrawRibbonStatusBarPane](../Topic/CMFCVisualManager::OnDrawRibbonStatusBarPane.md)|Aufgerufen vom Framework, wenn der Statusleistenbereich eines Menübands zeichnet.|  
|[CMFCVisualManager::OnDrawRibbonTabsFrame](../Topic/CMFCVisualManager::OnDrawRibbonTabsFrame.md)|Aufgerufen vom Framework, wenn Rahmen um einen Satz von Menübandregisterkarten zeichnet.|  
|[CMFCVisualManager::OnDrawScrollButtons](../Topic/CMFCVisualManager::OnDrawScrollButtons.md)||  
|[CMFCVisualManager::OnDrawSeparator](../Topic/CMFCVisualManager::OnDrawSeparator.md)|Aufgerufen vom Framework, wenn es ein Trennzeichen zeichnet.  Das Trennzeichen wird normalerweise auf einer Steuerleiste verwendet, um Gruppen Symbole zu trennen.|  
|[CMFCVisualManager::OnDrawShowAllMenuItems](../Topic/CMFCVisualManager::OnDrawShowAllMenuItems.md)||  
|[CMFCVisualManager::OnDrawSpinButtons](../Topic/CMFCVisualManager::OnDrawSpinButtons.md)|Aufgerufen vom Framework, wenn Drehfelder zeichnet.|  
|[CMFCVisualManager::OnDrawSplitterBorder](../Topic/CMFCVisualManager::OnDrawSplitterBorder.md)|Aufgerufen vom Framework, wenn der Kontext eines geteilten Fenster zeichnet.|  
|[CMFCVisualManager::OnDrawSplitterBox](../Topic/CMFCVisualManager::OnDrawSplitterBox.md)|Aufgerufen vom Framework, wenn der Splitterunterkasten für ein getrenntes Fenster zeichnet.|  
|[CMFCVisualManager::OnDrawStatusBarPaneBorder](../Topic/CMFCVisualManager::OnDrawStatusBarPaneBorder.md)|Aufgerufen vom Framework, wenn der Kontext für einen Statusleistenbereich zeichnet.|  
|[CMFCVisualManager::OnDrawStatusBarProgress](../Topic/CMFCVisualManager::OnDrawStatusBarProgress.md)|Aufgerufen vom Framework, wenn die Statusleistenstatusanzeige zeichnet.|  
|[CMFCVisualManager::OnDrawStatusBarSizeBox](../Topic/CMFCVisualManager::OnDrawStatusBarSizeBox.md)|Aufgerufen vom Framework, wenn das Statusleistengrößenfeld zeichnet.|  
|[CMFCVisualManager::OnDrawTab](../Topic/CMFCVisualManager::OnDrawTab.md)|Aufgerufen vom Framework, wenn ein [CMFCTabCtrl](../../mfc/reference/cmfctabctrl-class.md)\-Objekt zeichnet.|  
|[CMFCVisualManager::OnDrawTabCloseButton](../Topic/CMFCVisualManager::OnDrawTabCloseButton.md)|Aufgerufen vom Framework, wenn er die Schaltfläche **Schließen** auf der aktiven Registerkarte erfasst.|  
|[CMFCVisualManager::OnDrawTabContent](../Topic/CMFCVisualManager::OnDrawTabContent.md)|Aufgerufen vom Framework, wenn er den Registerkarteninnenraum \(Bilder, Texte\) zeichnet.|  
|[CMFCVisualManager::OnDrawTabsButtonBorder](../Topic/CMFCVisualManager::OnDrawTabsButtonBorder.md)|Aufgerufen vom Framework, wenn er den Kontext einer Registerkartenschaltfläche zeichnet.|  
|[CMFCVisualManager::OnDrawTask](../Topic/CMFCVisualManager::OnDrawTask.md)|Aufgerufen vom Framework, wenn er eine Aufgabe im Aufgabenbereich zeichnet.|  
|[CMFCVisualManager::OnDrawTasksGroupAreaBorder](../Topic/CMFCVisualManager::OnDrawTasksGroupAreaBorder.md)|Aufgerufen vom Framework, wenn er einen Rahmen um einen Gruppenbereich im Aufgabenbereich zeichnet.|  
|[CMFCVisualManager::OnDrawTasksGroupCaption](../Topic/CMFCVisualManager::OnDrawTasksGroupCaption.md)|Aufgerufen vom Framework, wenn er die Beschriftung für eine Aufgabengruppe im Aufgabenbereich zeichnet.|  
|[CMFCVisualManager::OnDrawTasksGroupIcon](../Topic/CMFCVisualManager::OnDrawTasksGroupIcon.md)||  
|[CMFCVisualManager::OnDrawTearOffCaption](../Topic/CMFCVisualManager::OnDrawTearOffCaption.md)|Aufgerufen vom Framework, wenn er die Tearoffe Beschriftung für eine Tearoffe Leiste zeichnet.|  
|[CMFCVisualManager::OnDrawToolBoxFrame](../Topic/CMFCVisualManager::OnDrawToolBoxFrame.md)||  
|[CMFCVisualManager::OnEraseMDIClientArea](../Topic/CMFCVisualManager::OnEraseMDIClientArea.md)|Aufgerufen vom Framework, wenn er den MDI\-Clientbereich gelöscht wird.|  
|[CMFCVisualManager::OnErasePopupWindowButton](../Topic/CMFCVisualManager::OnErasePopupWindowButton.md)||  
|[CMFCVisualManager::OnEraseTabsArea](../Topic/CMFCVisualManager::OnEraseTabsArea.md)|Aufgerufen vom Framework, wenn er den Registerkartenbereich in einem Registerkartenfenster gelöscht wird.|  
|[CMFCVisualManager::OnEraseTabsButton](../Topic/CMFCVisualManager::OnEraseTabsButton.md)|Aufgerufen vom Framework, wenn das Symbol und den Text einer Registerkartenschaltfläche gelöscht wird.|  
|[CMFCVisualManager::OnEraseTabsFrame](../Topic/CMFCVisualManager::OnEraseTabsFrame.md)|Aufgerufen vom Framework, wenn er Registerkartenframe gelöscht wird.|  
|[CMFCVisualManager::OnFillAutoHideButtonBackground](../Topic/CMFCVisualManager::OnFillAutoHideButtonBackground.md)|Aufgerufen vom Framework, wenn er den Hintergrund einer Schaltfläche der automatische Ausblendenen automatische Ausblenden ausfüllt.|  
|[CMFCVisualManager::OnFillBarBackground](../Topic/CMFCVisualManager::OnFillBarBackground.md)|Aufgerufen vom Framework, wenn er den Hintergrund einer Steuerleiste ausfüllt.|  
|[CMFCVisualManager::OnFillButtonInterior](../Topic/CMFCVisualManager::OnFillButtonInterior.md)|Aufgerufen vom Framework, wenn er den Hintergrund einer Symbolleisten\-Schaltfläche ausfüllt.|  
|[CMFCVisualManager::OnFillCaptionBarButton](../Topic/CMFCVisualManager::OnFillCaptionBarButton.md)||  
|[CMFCVisualManager::OnFillCommandsListBackground](../Topic/CMFCVisualManager::OnFillCommandsListBackground.md)|Aufgerufen vom Framework, wenn er den Hintergrund einer Symbolleisten\-Schaltfläche ausfüllt, die einer Befehlsliste gehört, die wiederum ein Teil eines Anpassungsdialogfelds ist.|  
|[CMFCVisualManager::OnFillHeaderCtrlBackground](../Topic/CMFCVisualManager::OnFillHeaderCtrlBackground.md)|Aufgerufen vom Framework, wenn sie den Hintergrund eines Header\-Steuerelements ausfüllt.|  
|[CMFCVisualManager::OnFillMiniFrameCaption](../Topic/CMFCVisualManager::OnFillMiniFrameCaption.md)|Aufgerufen vom Framework, wenn sie die Beschriftung eines Minirahmenfensters ausfüllt.|  
|[CMFCVisualManager::OnFillOutlookBarCaption](../Topic/CMFCVisualManager::OnFillOutlookBarCaption.md)|Aufgerufen vom Framework, wenn sie den Hintergrund einer Outlook\-Leistebeschriftung ausfüllt.|  
|[CMFCVisualManager::OnFillOutlookPageButton](../Topic/CMFCVisualManager::OnFillOutlookPageButton.md)|Aufgerufen vom Framework, wenn sie das Innere einer Outlook\-Seitenschaltfläche ausfüllt.|  
|[CMFCVisualManager::OnFillPopupWindowBackground](../Topic/CMFCVisualManager::OnFillPopupWindowBackground.md)|Aufgerufen vom Framework, wenn sie den Hintergrund eines Fensters von Popups ausfüllt.|  
|[CMFCVisualManager::OnFillRibbonButton](../Topic/CMFCVisualManager::OnFillRibbonButton.md)|Aufgerufen vom Framework, wenn sie das Innere einer Menübandschaltfläche ausfüllt.|  
|[CMFCVisualManager::OnFillRibbonEdit](../Topic/CMFCVisualManager::OnFillRibbonEdit.md)|Aufgerufen vom Framework, wenn sie das Innere eines Menübandbearbeitungssteuerelements ausfüllt.|  
|[CMFCVisualManager::OnFillRibbonMainPanelButton](../Topic/CMFCVisualManager::OnFillRibbonMainPanelButton.md)|Aufgerufen vom Framework, wenn sie das Innere einer Menübandschaltfläche auf dem Bereich **Hauptframe** ausfüllt.|  
|[CMFCVisualManager::OnFillRibbonMenuFrame](../Topic/CMFCVisualManager::OnFillRibbonMenuFrame.md)|Aufgerufen vom Framework, wenn sie die Menüframe des zentralen Menübandbereichs ausfüllt.|  
|[CMFCVisualManager::OnFillRibbonQuickAccessToolBarPopup](../Topic/CMFCVisualManager::OnFillRibbonQuickAccessToolBarPopup.md)||  
|[CMFCVisualManager::OnFillSplitterBackground](../Topic/CMFCVisualManager::OnFillSplitterBackground.md)|Aufgerufen vom Framework, wenn sie den Hintergrund eines geteilten Fenster ausfüllt.|  
|[CMFCVisualManager::OnFillTab](../Topic/CMFCVisualManager::OnFillTab.md)|Aufgerufen vom Framework, wenn sie den Hintergrund einer Registerkarte ausfüllt.|  
|[CMFCVisualManager::OnFillTasksGroupInterior](../Topic/CMFCVisualManager::OnFillTasksGroupInterior.md)|Aufgerufen vom Framework, wenn das Innere eines [CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md)\-Objekts auf [CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md) ausfüllt.|  
|[CMFCVisualManager::OnFillTasksPaneBackground](../Topic/CMFCVisualManager::OnFillTasksPaneBackground.md)|Aufgerufen vom Framework, wenn es den Hintergrund eines Steuerelements `CMFCTasksPane` ausfüllt.|  
|[CMFCVisualManager::OnHighlightMenuItem](../Topic/CMFCVisualManager::OnHighlightMenuItem.md)|Aufgerufen vom Framework, wenn es als ein Menüelement zeichnet.|  
|[CMFCVisualManager::OnHighlightRarelyUsedMenuItems](../Topic/CMFCVisualManager::OnHighlightRarelyUsedMenuItems.md)|Aufgerufen vom Framework, wenn es ein als und selten verwendete Menüelement zeichnet.|  
|[CMFCVisualManager::OnNcPaint](../Topic/CMFCVisualManager::OnNcPaint.md)|Aufgerufen vom Framework, wenn der Nicht\-Clientbereich zeichnet.|  
|[CMFCVisualManager::OnSetWindowRegion](../Topic/CMFCVisualManager::OnSetWindowRegion.md)|Aufgerufen vom Framework, wenn es einen Bereich festlegen, den Frames und Popupmenüs enthält.|  
|[CMFCVisualManager::OnUpdateSystemColors](../Topic/CMFCVisualManager::OnUpdateSystemColors.md)|Aufgerufen vom Framework, wenn er die Systemfarbeneinstellung ändert.|  
|[CMFCVisualManager::RedrawAll](../Topic/CMFCVisualManager::RedrawAll.md)|Aktualisiert alle Steuerleisten in der Anwendung neu.|  
|[CMFCVisualManager::RibbonCategoryColorToRGB](../Topic/CMFCVisualManager::RibbonCategoryColorToRGB.md)||  
|[CMFCVisualManager::SetDefaultManager](../Topic/CMFCVisualManager::SetDefaultManager.md)|Legt den standardmäßigen visuellen Manager fest.|  
|[CMFCVisualManager::SetEmbossDisabledImage](../Topic/CMFCVisualManager::SetEmbossDisabledImage.md)|Aktiviert oder deaktiviert den geprägten Modus für deaktivierte Symbolleistenimages.|  
|[CMFCVisualManager::SetFadeInactiveImage](../Topic/CMFCVisualManager::SetFadeInactiveImage.md)|Aktiviert oder deaktiviert den Lichteffekt für inaktive Bilder in einem Menü oder einer Symbolleiste.|  
|[CMFCVisualManager::SetMenuFlatLook](../Topic/CMFCVisualManager::SetMenuFlatLook.md)|Legt ein Flag fest, ob die Anwendungsmenüschaltflächen eine vereinfachte Darstellung haben.|  
|[CMFCVisualManager::SetMenuShadowDepth](../Topic/CMFCVisualManager::SetMenuShadowDepth.md)|Gibt die Breite und Höhe des Menüschattens fest.|  
|[CMFCVisualManager::SetShadowHighlightedImage](../Topic/CMFCVisualManager::SetShadowHighlightedImage.md)|Legt ein Flag fest, der angibt, ob der Schatten angezeigt wird, wenn markierte Bilder gerendert wird.|  
  
## Hinweise  
 Da die `CMFCVisualManager`\-Klasse die GUI der Anwendung gesteuert, kann jede Anwendung entweder eine Instanz von `CMFCVisualManager` oder eine Instanz einer Klasse verfügen, die von `CMFCVisualManager` abgeleitet wird.  Die Anwendung kann ohne `CMFCVisualManager` auch arbeiten.  Verwenden Sie die statische Methode `GetInstance`, um ein Zeiger zu aktuellen `CMFCVisualManager` zum Abrufen von abgeleitetes Objekt.  
  
 Um die Darstellung der Anwendung zu ändern müssen Sie andere Klassen verwenden die Methoden zum Zeichnen alle visuellen Elemente der Anwendung bereitstellen.  Einige Beispiele für diese Klassen sind [CMFCVisualManagerOfficeXP Class](../../mfc/reference/cmfcvisualmanagerofficexp-class.md), [CMFCVisualManagerOffice2003 Class](../../mfc/reference/cmfcvisualmanageroffice2003-class.md) und [CMFCVisualManagerOffice2007 Class](../../mfc/reference/cmfcvisualmanageroffice2007-class.md).  Wenn Sie die Darstellung der Anwendung ändern möchten, führen Sie einen dieser visuellen Manager in die Methode `SetDefaultManager`.  Ein Beispiel dafür, wie die Anwendung die Darstellung von Microsoft Office 2003 imitieren kann, finden [CMFCVisualManagerOffice2003 Class](../../mfc/reference/cmfcvisualmanageroffice2003-class.md).  
  
 Alle Zeichenmethoden sind virtuell.  Dies ermöglicht es Ihnen, einen benutzerdefinierten visuellen Stil für das GUI Ihrer Anwendung erstellen.  Wenn Sie einen eigenen visuellen Stil erstellen möchten, leiten Sie eine Klasse von einer der visuellen Managerklassen und überschreiben Sie die Zeichenmethoden, die Sie ändern möchten.  
  
## Beispiel  
 Dieses Beispiel zeigt, wie Sie die standardmäßigen und benutzerdefinierte `CMFCVisualManager`\-Objekte instanziiert.  
  
```  
void CMFCSkinsApp::SetSkin (int iIndex)  
{   // destroy the current visual manager  
   if (CMFCVisualManager::GetInstance () != NULL)  
   {  
      delete CMFCVisualManager::GetInstance ();  
   }  
   switch (iIndex)  
  {  
   case 0:  
      CMFCVisualManager::GetInstance (); // create the standard visual manager  
      break;  
   case 1:  
      new CMyVisualManager (); // create the first custom visual manager  
      break;  
   case 2:  
      new CMacStyle ();  // create the second custom visual manager  
      break;  
   }  
  
   // access the manager and set it properly  
   CMFCVisualManager::GetInstance ()->SetLook2000 ();  
   CMFCVisualManager::GetInstance ()->RedrawAll ();  
}  
```  
  
## Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die Standardwerte `CMFCVisualManager` eines Objekts abgerufen werden.  Dieser Codeausschnitt ist Teil [Aufgabenbereichsbeispiel](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_TasksPane#1](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_TasksPane#1)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCBaseVisualManager](../../mfc/reference/cmfcbasevisualmanager-class.md)  
  
 [CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md)  
  
## Anforderungen  
 **Header:** afxvisualmanager.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCVisualManager::GetInstance](../Topic/CMFCVisualManager::GetInstance.md)   
 [Visualisierungs\-Manager](../../mfc/visualization-manager.md)
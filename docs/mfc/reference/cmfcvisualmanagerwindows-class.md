---
title: "CMFCVisualManagerWindows Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCVisualManagerWindows"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCVisualManagerWindows class"
ms.assetid: 568b6e9e-8e67-4477-9a3d-2981cbd09861
caps.latest.revision: 46
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 48
---
# CMFCVisualManagerWindows Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCVisualManagerWindows` ahmt die Darstellung von Microsoft Windows XP oder von Microsoft Vista, wenn der Benutzer ein Windows XP oder Vista\-Design auswählt.  
  
## Syntax  
  
```  
class CMFCVisualManagerWindows : public CMFCVisualManagerOfficeXP  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|`CMFCVisualManagerWindows::CMFCVisualManagerWindows`|Standardkonstruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCVisualManagerWindows::AlwaysHighlight3DTabs](../Topic/CMFCVisualManagerWindows::AlwaysHighlight3DTabs.md)|Das Framework ruft diese Methode auf, um zu bestimmen, ob 3D\-Registerkarten in der Anwendung immer hervorgehoben werden sollen.  \(Überschreibungen [CMFCVisualManager::AlwaysHighlight3DTabs](../Topic/CMFCVisualManager::AlwaysHighlight3DTabs.md).\)|  
|[CMFCVisualManagerWindows::DrawComboBorderWinXP](../Topic/CMFCVisualManagerWindows::DrawComboBorderWinXP.md)|\(Überschreibungen `CMFCVisualManager::DrawComboBorderWinXP`.\)|  
|[CMFCVisualManagerWindows::DrawComboDropButtonWinXP](../Topic/CMFCVisualManagerWindows::DrawComboDropButtonWinXP.md)|\(Überschreibungen [CMFCVisualManager::DrawComboDropButtonWinXP](../Topic/CMFCVisualManager::DrawComboDropButtonWinXP.md).\)|  
|[CMFCVisualManagerWindows::DrawPushButtonWinXP](../Topic/CMFCVisualManagerWindows::DrawPushButtonWinXP.md)|\(Überschreibungen [CMFCVisualManager::DrawPushButtonWinXP](../Topic/CMFCVisualManager::DrawPushButtonWinXP.md).\)|  
|[CMFCVisualManagerWindows::GetButtonExtraBorder](../Topic/CMFCVisualManagerWindows::GetButtonExtraBorder.md)|Das Framework ruft diese Methode auf, wenn eine Symbolleisten\-Schaltfläche zeichnet.  \(Überschreibungen [CMFCVisualManager::GetButtonExtraBorder](../Topic/CMFCVisualManager::GetButtonExtraBorder.md).\)|  
|[CMFCVisualManagerWindows::GetCaptionButtonExtraBorder](../Topic/CMFCVisualManagerWindows::GetCaptionButtonExtraBorder.md)|\(Überschreibungen [CMFCVisualManager::GetCaptionButtonExtraBorder](../Topic/CMFCVisualManager::GetCaptionButtonExtraBorder.md).\)|  
|[CMFCVisualManagerWindows::GetDockingPaneCaptionExtraHeight](../Topic/CMFCVisualManagerWindows::GetDockingPaneCaptionExtraHeight.md)|\(Überschreibungen `CMFCVisualManager::GetDockingPaneCaptionExtraHeight`.\)|  
|[CMFCVisualManagerWindows::GetHighlightedMenuItemTextColor](../Topic/CMFCVisualManagerWindows::GetHighlightedMenuItemTextColor.md)|\(Überschreibungen `CMFCVisualManagerOfficeXP::GetHighlightedMenuItemTextColor`.\)|  
|[CMFCVisualManagerWindows::GetPopupMenuGap](../Topic/CMFCVisualManagerWindows::GetPopupMenuGap.md)|\(Überschreibungen `CMFCVisualManagerOfficeXP::GetPopupMenuGap`.\)|  
|[CMFCVisualManagerWindows::GetToolbarButtonTextColor](../Topic/CMFCVisualManagerWindows::GetToolbarButtonTextColor.md)|\(Überschreibungen `CMFCVisualManagerOfficeXP::GetToolbarButtonTextColor`.\)|  
|[CMFCVisualManagerWindows::IsDefaultWinXPPopupButton](../Topic/CMFCVisualManagerWindows::IsDefaultWinXPPopupButton.md)|\(Überschreibungen [CMFCVisualManager::IsDefaultWinXPPopupButton](../Topic/CMFCVisualManager::IsDefaultWinXPPopupButton.md).\)|  
|[CMFCVisualManagerWindows::IsHighlightWholeMenuItem](../Topic/CMFCVisualManagerWindows::IsHighlightWholeMenuItem.md)|\(Überschreibungen `CMFCVisualManagerOfficeXP::IsHighlightWholeMenuItem`.\)|  
|[CMFCVisualManagerWindows::IsOfficeStyleMenus](../Topic/CMFCVisualManagerWindows::IsOfficeStyleMenus.md)||  
|[CMFCVisualManagerWindows::IsOfficeXPStyleMenus](../Topic/CMFCVisualManagerWindows::IsOfficeXPStyleMenus.md)|Gibt an, ob der visuelle Manager Office\-XP\-Format Menüs implementiert.  \(Überschreibungen [CMFCVisualManager::IsOfficeXPStyleMenus](../Topic/CMFCVisualManager::IsOfficeXPStyleMenus.md).\)|  
|[CMFCVisualManagerWindows::IsWindowsThemingSupported](../Topic/CMFCVisualManagerWindows::IsWindowsThemingSupported.md)|\(Überschreibungen `CMFCVisualManager::IsWindowsThemingSupported`.\)|  
|[CMFCVisualManagerWindows::IsWinXPThemeAvailable](../Topic/CMFCVisualManagerWindows::IsWinXPThemeAvailable.md)|Gibt an, ob ein Windows\-Design verfügbar ist.  Ein Design kann entweder ein Windows XP\-Design oder ein [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] Design sein.|  
|[CMFCVisualManagerWindows::OnDrawBarGripper](../Topic/CMFCVisualManagerWindows::OnDrawBarGripper.md)|\(Überschreibungen `CMFCVisualManagerOfficeXP::OnDrawBarGripper`.\)|  
|[CMFCVisualManagerWindows::OnDrawBrowseButton](../Topic/CMFCVisualManagerWindows::OnDrawBrowseButton.md)|\(Überschreibungen `CMFCVisualManagerOfficeXP::OnDrawBrowseButton`.\)|  
|[CMFCVisualManagerWindows::OnDrawButtonBorder](../Topic/CMFCVisualManagerWindows::OnDrawButtonBorder.md)|\(Überschreibungen `CMFCVisualManagerOfficeXP::OnDrawButtonBorder`.\)|  
|[CMFCVisualManagerWindows::OnDrawButtonSeparator](../Topic/CMFCVisualManagerWindows::OnDrawButtonSeparator.md)|\(Überschreibungen `CMFCVisualManagerOfficeXP::OnDrawButtonSeparator`.\)|  
|[CMFCVisualManagerWindows::OnDrawCaptionButton](../Topic/CMFCVisualManagerWindows::OnDrawCaptionButton.md)|\(Überschreibungen `CMFCVisualManagerOfficeXP::OnDrawCaptionButton`.\)|  
|[CMFCVisualManagerWindows::OnDrawCaptionButtonIcon](../Topic/CMFCVisualManagerWindows::OnDrawCaptionButtonIcon.md)|\(Überschreibungen `CMFCVisualManagerOfficeXP::OnDrawCaptionButtonIcon`.\)|  
|[CMFCVisualManagerWindows::OnDrawCheckBoxEx](../Topic/CMFCVisualManagerWindows::OnDrawCheckBoxEx.md)|\(Überschreibungen [CMFCVisualManager::OnDrawCheckBoxEx](../Topic/CMFCVisualManager::OnDrawCheckBoxEx.md).\)|  
|[CMFCVisualManagerWindows::OnDrawComboBorder](../Topic/CMFCVisualManagerWindows::OnDrawComboBorder.md)|\(Überschreibungen `CMFCVisualManagerOfficeXP::OnDrawComboBorder`.\)|  
|[CMFCVisualManagerWindows::OnDrawComboDropButton](../Topic/CMFCVisualManagerWindows::OnDrawComboDropButton.md)|\(Überschreibungen `CMFCVisualManagerOfficeXP::OnDrawComboDropButton`.\)|  
|[CMFCVisualManagerWindows::OnDrawControlBorder](../Topic/CMFCVisualManagerWindows::OnDrawControlBorder.md)|\(Überschreibungen [CMFCVisualManager::OnDrawControlBorder](../Topic/CMFCVisualManager::OnDrawControlBorder.md).\)|  
|[CMFCVisualManagerWindows::OnDrawEditBorder](../Topic/CMFCVisualManagerWindows::OnDrawEditBorder.md)|\(Überschreibungen `CMFCVisualManagerOfficeXP::OnDrawEditBorder`.\)|  
|[CMFCVisualManagerWindows::OnDrawExpandingBox](../Topic/CMFCVisualManagerWindows::OnDrawExpandingBox.md)|\(Überschreibungen [CMFCVisualManager::OnDrawExpandingBox](../Topic/CMFCVisualManager::OnDrawExpandingBox.md).\)|  
|[CMFCVisualManagerWindows::OnDrawFloatingToolbarBorder](../Topic/CMFCVisualManagerWindows::OnDrawFloatingToolbarBorder.md)|\(Überschreibungen `CMFCVisualManagerOfficeXP::OnDrawFloatingToolbarBorder`.\)|  
|[CMFCVisualManagerWindows::OnDrawHeaderCtrlBorder](../Topic/CMFCVisualManagerWindows::OnDrawHeaderCtrlBorder.md)|Das Framework ruft diese Methode auf, wenn der Rahmen um eine Instanz [CMFCHeaderCtrl Class](../../mfc/reference/cmfcheaderctrl-class.md) zeichnet.  \(Überschreibungen [CMFCVisualManager::OnDrawHeaderCtrlBorder](../Topic/CMFCVisualManager::OnDrawHeaderCtrlBorder.md).\)|  
|[CMFCVisualManagerWindows::OnDrawHeaderCtrlSortArrow](../Topic/CMFCVisualManagerWindows::OnDrawHeaderCtrlSortArrow.md)|Das Framework ruft diese Funktion auf, wenn der Sortierungspfeil eines Header\-Steuerelements zeichnet.  \(Überschreibungen [CMFCVisualManager::OnDrawHeaderCtrlSortArrow](../Topic/CMFCVisualManager::OnDrawHeaderCtrlSortArrow.md).\)|  
|[CMFCVisualManagerWindows::OnDrawMenuBorder](../Topic/CMFCVisualManagerWindows::OnDrawMenuBorder.md)|\(Überschreibungen `CMFCVisualManagerOfficeXP::OnDrawMenuBorder`.\)|  
|[CMFCVisualManagerWindows::OnDrawMenuSystemButton](../Topic/CMFCVisualManagerWindows::OnDrawMenuSystemButton.md)|\(Überschreibungen `CMFCVisualManagerOfficeXP::OnDrawMenuSystemButton`.\)|  
|[CMFCVisualManagerWindows::OnDrawMiniFrameBorder](../Topic/CMFCVisualManagerWindows::OnDrawMiniFrameBorder.md)|\(Überschreibungen `CMFCVisualManagerOfficeXP::OnDrawMiniFrameBorder`.\)|  
|[CMFCVisualManagerWindows::OnDrawOutlookPageButtonBorder](../Topic/CMFCVisualManagerWindows::OnDrawOutlookPageButtonBorder.md)|Aufgerufen vom Framework, wenn der Kontext einer Outlook\-Seitenschaltfläche zeichnet.  \(Überschreibungen [CMFCVisualManager::OnDrawOutlookPageButtonBorder](../Topic/CMFCVisualManager::OnDrawOutlookPageButtonBorder.md).\)|  
|[CMFCVisualManagerWindows::OnDrawPaneBorder](../Topic/CMFCVisualManagerWindows::OnDrawPaneBorder.md)|\(Überschreibungen `CMFCVisualManagerOfficeXP::OnDrawPaneBorder`.\)|  
|[CMFCVisualManagerWindows::OnDrawPaneCaption](../Topic/CMFCVisualManagerWindows::OnDrawPaneCaption.md)|\(Überschreibungen `CMFCVisualManagerOfficeXP::OnDrawPaneCaption`.\)|  
|[CMFCVisualManagerWindows::OnDrawPopupWindowButtonBorder](../Topic/CMFCVisualManagerWindows::OnDrawPopupWindowButtonBorder.md)|\(Überschreibungen `CMFCVisualManagerOfficeXP::OnDrawPopupWindowButtonBorder`.\)|  
|[CMFCVisualManagerWindows::OnDrawScrollButtons](../Topic/CMFCVisualManagerWindows::OnDrawScrollButtons.md)|\(Überschreibungen `CMFCVisualManagerOfficeXP::OnDrawScrollButtons`.\)|  
|[CMFCVisualManagerWindows::OnDrawSeparator](../Topic/CMFCVisualManagerWindows::OnDrawSeparator.md)|\(Überschreibungen `CMFCVisualManagerOfficeXP::OnDrawSeparator`.\)|  
|[CMFCVisualManagerWindows::OnDrawSpinButtons](../Topic/CMFCVisualManagerWindows::OnDrawSpinButtons.md)|\(Überschreibungen `CMFCVisualManagerOfficeXP::OnDrawSpinButtons`.\)|  
|[CMFCVisualManagerWindows::OnDrawStatusBarPaneBorder](../Topic/CMFCVisualManagerWindows::OnDrawStatusBarPaneBorder.md)|\(Überschreibungen `CMFCVisualManagerOfficeXP::OnDrawStatusBarPaneBorder`.\)|  
|[CMFCVisualManagerWindows::OnDrawStatusBarProgress](../Topic/CMFCVisualManagerWindows::OnDrawStatusBarProgress.md)|Das Framework ruft diese Methode auf, wenn die Statusanzeige auf dem [CMFCStatusBar](../../mfc/reference/cmfcstatusbar-class.md)\-Objekt zeichnet.  \(Überschreibungen [CMFCVisualManager::OnDrawStatusBarProgress](../Topic/CMFCVisualManager::OnDrawStatusBarProgress.md).\)|  
|[CMFCVisualManagerWindows::OnDrawStatusBarSizeBox](../Topic/CMFCVisualManagerWindows::OnDrawStatusBarSizeBox.md)|Das Framework ruft diese Methode auf, wenn das Größenfeld für [CMFCStatusBar](../../mfc/reference/cmfcstatusbar-class.md) zeichnet.  \(Überschreibungen [CMFCVisualManager::OnDrawStatusBarSizeBox](../Topic/CMFCVisualManager::OnDrawStatusBarSizeBox.md).\)|  
|[CMFCVisualManagerWindows::OnDrawTab](../Topic/CMFCVisualManagerWindows::OnDrawTab.md)|\(Überschreibungen `CMFCVisualManagerOfficeXP::OnDrawTab`.\)|  
|[CMFCVisualManagerWindows::OnDrawTabCloseButton](../Topic/CMFCVisualManagerWindows::OnDrawTabCloseButton.md)|\(Überschreibungen `CMFCVisualManagerOfficeXP::OnDrawTabCloseButton`.\)|  
|[CMFCVisualManagerWindows::OnDrawTabsButtonBorder](../Topic/CMFCVisualManagerWindows::OnDrawTabsButtonBorder.md)|\(Überschreibungen `CMFCVisualManagerOfficeXP::OnDrawTabsButtonBorder`.\)|  
|[CMFCVisualManagerWindows::OnDrawTask](../Topic/CMFCVisualManagerWindows::OnDrawTask.md)|\(Überschreibungen `CMFCVisualManagerOfficeXP::OnDrawTask`.\)|  
|[CMFCVisualManagerWindows::OnDrawTasksGroupAreaBorder](../Topic/CMFCVisualManagerWindows::OnDrawTasksGroupAreaBorder.md)|\(Überschreibungen `CMFCVisualManagerOfficeXP::OnDrawTasksGroupAreaBorder`.\)|  
|[CMFCVisualManagerWindows::OnDrawTasksGroupCaption](../Topic/CMFCVisualManagerWindows::OnDrawTasksGroupCaption.md)|\(Überschreibungen `CMFCVisualManagerOfficeXP::OnDrawTasksGroupCaption`.\)|  
|[CMFCVisualManagerWindows::OnDrawTearOffCaption](../Topic/CMFCVisualManagerWindows::OnDrawTearOffCaption.md)|\(Überschreibungen `CMFCVisualManagerOfficeXP::OnDrawTearOffCaption`.\)|  
|[CMFCVisualManagerWindows::OnErasePopupWindowButton](../Topic/CMFCVisualManagerWindows::OnErasePopupWindowButton.md)|\(Überschreibungen `CMFCVisualManagerOfficeXP::OnErasePopupWindowButton`.\)|  
|[CMFCVisualManagerWindows::OnEraseTabsArea](../Topic/CMFCVisualManagerWindows::OnEraseTabsArea.md)|\(Überschreibungen `CMFCVisualManagerOfficeXP::OnEraseTabsArea`.\)|  
|[CMFCVisualManagerWindows::OnEraseTabsButton](../Topic/CMFCVisualManagerWindows::OnEraseTabsButton.md)|\(Überschreibungen `CMFCVisualManagerOfficeXP::OnEraseTabsButton`.\)|  
|[CMFCVisualManagerWindows::OnEraseTabsFrame](../Topic/CMFCVisualManagerWindows::OnEraseTabsFrame.md)|Das Framework ruft diese Methode auf, wenn Frames auf [CMFCBaseTabCtrl Class](../../mfc/reference/cmfcbasetabctrl-class.md) gelöscht wird.  \(Überschreibungen [CMFCVisualManager::OnEraseTabsFrame](../Topic/CMFCVisualManager::OnEraseTabsFrame.md).\)|  
|[CMFCVisualManagerWindows::OnFillBarBackground](../Topic/CMFCVisualManagerWindows::OnFillBarBackground.md)|\(Überschreibungen `CMFCVisualManagerOfficeXP::OnFillBarBackground`.\)|  
|[CMFCVisualManagerWindows::OnFillButtonInterior](../Topic/CMFCVisualManagerWindows::OnFillButtonInterior.md)|\(Überschreibungen `CMFCVisualManagerOfficeXP::OnFillButtonInterior`.\)|  
|[CMFCVisualManagerWindows::OnFillCommandsListBackground](../Topic/CMFCVisualManagerWindows::OnFillCommandsListBackground.md)|\(Überschreibungen `CMFCVisualManagerOfficeXP::OnFillCommandsListBackground`.\)|  
|[CMFCVisualManagerWindows::OnFillMiniFrameCaption](../Topic/CMFCVisualManagerWindows::OnFillMiniFrameCaption.md)|\(Überschreibungen `CMFCVisualManagerOfficeXP::OnFillMiniFrameCaption`.\)|  
|[CMFCVisualManagerWindows::OnFillOutlookPageButton](../Topic/CMFCVisualManagerWindows::OnFillOutlookPageButton.md)|Das Framework ruft diese Methode auf, wenn das Innere einer Outlook\-Seitenschaltfläche ausfüllt.  \(Überschreibungen [CMFCVisualManager::OnFillOutlookPageButton](../Topic/CMFCVisualManager::OnFillOutlookPageButton.md).\)|  
|[CMFCVisualManagerWindows::OnFillTasksGroupInterior](../Topic/CMFCVisualManagerWindows::OnFillTasksGroupInterior.md)|\(Überschreibungen `CMFCVisualManagerOfficeXP::OnFillTasksGroupInterior`.\)|  
|[CMFCVisualManagerWindows::OnFillTasksPaneBackground](../Topic/CMFCVisualManagerWindows::OnFillTasksPaneBackground.md)|Das Framework ruft diese Methode auf, wenn der Hintergrund eines Steuerelements [CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md) ausfüllt.  \(Überschreibungen [CMFCVisualManager::OnFillTasksPaneBackground](../Topic/CMFCVisualManager::OnFillTasksPaneBackground.md).\)|  
|[CMFCVisualManagerWindows::OnHighlightMenuItem](../Topic/CMFCVisualManagerWindows::OnHighlightMenuItem.md)|\(Überschreibungen `CMFCVisualManagerOfficeXP::OnHighlightMenuItem`.\)|  
|[CMFCVisualManagerWindows::OnHighlightRarelyUsedMenuItems](../Topic/CMFCVisualManagerWindows::OnHighlightRarelyUsedMenuItems.md)|\(Überschreibungen `CMFCVisualManagerOfficeXP::OnHighlightRarelyUsedMenuItems`.\)|  
|[CMFCVisualManagerWindows::OnUpdateSystemColors](../Topic/CMFCVisualManagerWindows::OnUpdateSystemColors.md)|\(Überschreibungen `CMFCVisualManagerOfficeXP::OnUpdateSystemColors`.\)|  
|[CMFCVisualManagerWindows::SetOfficeStyleMenus](../Topic/CMFCVisualManagerWindows::SetOfficeStyleMenus.md)||  
  
### Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCVisualManagerWindows::m\_b3DTabsXPTheme](../Topic/CMFCVisualManagerWindows::m_b3DTabsXPTheme.md)|Gibt an, ob das Windows XP\-Design 3D\-Registerkarten anzeigt.|  
  
## Hinweise  
 Verwenden Sie die `CMFCVisualManagerWindows`\-Klasse, um die Darstellung der Anwendung zu ändern, aktuellen Windows XP oder das [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] Design auf dem Computer zu imitieren, auf dem die Anwendung ausgeführt wird.  
  
 jedoch möglicherweise ein Windows\-Design nicht verfügbar, wenn die Anwendung auf eine Version von Windows zuvor als Windows XP ausgeführt wird, oder wenn Designs deaktiviert werden, da der Benutzer die Ansicht **Klassisch** verwendet.  Wenn kein Design verfügbar ist, verwendet die Anwendung den standardmäßigen visuellen Manager, der in [CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md) definiert ist.  
  
## Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung von `CMFCVisualManagerWindows`.  Dieser Codeausschnitt ist Teil [Desktop\-wachsames Demobeispiel](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_DesktopAlertDemo#10](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_DesktopAlertDemo#10)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCBaseVisualManager](../../mfc/reference/cmfcbasevisualmanager-class.md)  
  
 [CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md)  
  
 [CMFCVisualManagerOfficeXP](../../mfc/reference/cmfcvisualmanagerofficexp-class.md)  
  
 [CMFCVisualManagerWindows](../../mfc/reference/cmfcvisualmanagerwindows-class.md)  
  
## Anforderungen  
 **Header:** afxvisualmanagerwindows.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCVisualManager Class](../../mfc/reference/cmfcvisualmanager-class.md)   
 [CMFCVisualManagerOfficeXP Class](../../mfc/reference/cmfcvisualmanagerofficexp-class.md)   
 [CMFCVisualManager::SetDefaultManager](../Topic/CMFCVisualManager::SetDefaultManager.md)
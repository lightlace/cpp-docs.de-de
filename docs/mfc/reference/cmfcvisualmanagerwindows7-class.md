---
title: "CMFCVisualManagerWindows7 Class"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "afxvisualmanagerwindows7/CMFCVisualManagerWindows7"
  - "CMFCVisualManagerWindows7"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCVisualManagerWindows7 class"
ms.assetid: e8d87df1-0c09-4b58-8ade-4e911f796e42
caps.latest.revision: 21
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCVisualManagerWindows7 Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCVisualManagerWindows7` gibt eine Anwendung die Darstellung einer Anwendung [!INCLUDE[win7](../../build/includes/win7_md.md)].  
  
## Syntax  
  
```  
class CMFCVisualManagerWindows7 : public CMFCVisualManagerWindows;  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCVisualManagerWindows7::CMFCVisualManagerWindows7](../Topic/CMFCVisualManagerWindows7::CMFCVisualManagerWindows7.md)|Standardkonstruktor.|  
|[CMFCVisualManagerWindows7::~CMFCVisualManagerWindows7](../Topic/CMFCVisualManagerWindows7::~CMFCVisualManagerWindows7.md)|Nehmen Sie Destruktor den Standardwert an.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|`CMFCVisualManagerWindows7::CleanStyle`|Löscht den aktuellen Stil und setzt den Standard visuellen Stil zurück.|  
|`CMFCVisualManagerWindows7::CleanUp`|Löscht alle Objekte in der Benutzeroberfläche und setzt die Menüs zurück.|  
|`CMFCVisualManagerWindows7::DrawNcBtn`|Zeichnet eine Schaltfläche im Nicht\-Clientbereich auf den Frame.  Das Framework verwendet diese Methode, um zu zeichnen minimieren, maximieren, Finalisierung und Wiederherstellen in der rechten oberen Ecke des Fensterrahmens.  Diese Methode wird nicht aufgerufen, wenn das Programm ein NichtAero\-Design verwendet.|  
|`CMFCVisualManagerWindows7::DrawNcText`|Zeichnet Text im Nicht\-Clientbereich auf den Frame.  Das Framework verwendet diese Methode, um den Anwendungsnamen in der Titelleiste am oberen Rand des Rahmenfensters zu zeichnen.|  
|`CMFCVisualManagerWindows7::DrawSeparator`|Zeichnet ein Trennzeichen auf [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md).|  
|`CMFCVisualManagerWindows7::GetRibbonBar`|Ruft [CMFCRibbonBar Class](../../mfc/reference/cmfcribbonbar-class.md) ab, das mit der Benutzeroberfläche zugeordnet ist.|  
|[CMFCVisualManagerWindows7::GetRibbonEditBackgroundColor](../Topic/CMFCVisualManagerWindows7::GetRibbonEditBackgroundColor.md)|Ruft eine Menübandeingabefeldhintergrundfarbe.|  
|`CMFCVisualManagerWindows7::GetRibbonPopupBorderSize`|Überschreibt [CMFCVisualManager::GetRibbonPopupBorderSize](../Topic/CMFCVisualManager::GetRibbonPopupBorderSize.md).|  
|`CMFCVisualManagerWindows7::GetRibbonQuickAccessToolBarChevronOffset`|Überschreibt [CMFCVisualManager::GetRibbonQuickAccessToolBarChevronOffset](../Topic/CMFCVisualManager::GetRibbonQuickAccessToolBarChevronOffset.md).|  
|`CMFCVisualManagerWindows7::GetRibbonQuickAccessToolBarRightMargin`|Überschreibt [CMFCVisualManager::GetRibbonQuickAccessToolBarRightMargin](../Topic/CMFCVisualManager::GetRibbonQuickAccessToolBarRightMargin.md).|  
|`CMFCVisualManagerWindows7::IsHighlightWholeMenuItem`|Überschreibt [CMFCVisualManagerWindows::IsHighlightWholeMenuItem](../Topic/CMFCVisualManagerWindows::IsHighlightWholeMenuItem.md).|  
|`CMFCVisualManagerWindows7::IsOwnerDrawMenuCheck`|Überschreibt [CMFCVisualManager::IsOwnerDrawMenuCheck](../Topic/CMFCVisualManager::IsOwnerDrawMenuCheck.md).|  
|`CMFCVisualManagerWindows7::IsRibbonPresent`|Bestimmt, ob `CMFCRibbonBar` vorhanden und sichtbar ist.|  
|`CMFCVisualManagerWindows7::OnDrawButtonBorder`|Überschreibt [CMFCVisualManagerWindows::OnDrawButtonBorder](../Topic/CMFCVisualManagerWindows::OnDrawButtonBorder.md).|  
|`CMFCVisualManagerWindows7::OnDrawCheckBoxEx`|Überschreibt [CMFCVisualManagerWindows::OnDrawCheckBoxEx](../Topic/CMFCVisualManagerWindows::OnDrawCheckBoxEx.md).|  
|`CMFCVisualManagerWindows7::OnDrawComboDropButton`|Überschreibt [CMFCVisualManagerWindows::OnDrawComboDropButton](../Topic/CMFCVisualManagerWindows::OnDrawComboDropButton.md).|  
|`CMFCVisualManagerWindows7::OnDrawDefaultRibbonImage`|Überschreibt [CMFCVisualManager::OnDrawDefaultRibbonImage](../Topic/CMFCVisualManager::OnDrawDefaultRibbonImage.md).|  
|`CMFCVisualManagerWindows7::OnDrawMenuBorder`|Überschreibt [CMFCVisualManagerWindows::OnDrawMenuBorder](../Topic/CMFCVisualManagerWindows::OnDrawMenuBorder.md).|  
|`CMFCVisualManagerWindows7::OnDrawMenuCheck`|Überschreibt [CMFCVisualManager::OnDrawMenuCheck](../Topic/CMFCVisualManager::OnDrawMenuCheck.md).|  
|`CMFCVisualManagerWindows7::OnDrawMenuLabel`|Überschreibt [CMFCVisualManager::OnDrawMenuLabel](../Topic/CMFCVisualManager::OnDrawMenuLabel.md).|  
|`CMFCVisualManagerWindows7::OnDrawRadioButton`|Überschreibt `CMFCVisualManager::OnDrawRadioButton`.|  
|`CMFCVisualManagerWindows7::OnDrawRibbonApplicationButton`|Überschreibt [CMFCVisualManager::OnDrawRibbonApplicationButton](../Topic/CMFCVisualManager::OnDrawRibbonApplicationButton.md).|  
|`CMFCVisualManagerWindows7::OnDrawRibbonButtonBorder`|Überschreibt [CMFCVisualManager::OnDrawRibbonButtonBorder](../Topic/CMFCVisualManager::OnDrawRibbonButtonBorder.md).|  
|`CMFCVisualManagerWindows7::OnDrawRibbonCaption`|Überschreibt [CMFCVisualManager::OnDrawRibbonCaption](../Topic/CMFCVisualManager::OnDrawRibbonCaption.md).|  
|`CMFCVisualManagerWindows7::OnDrawRibbonCaptionButton`|Überschreibt [CMFCVisualManager::OnDrawRibbonCaptionButton](../Topic/CMFCVisualManager::OnDrawRibbonCaptionButton.md).|  
|`CMFCVisualManagerWindows7::OnDrawRibbonCategory`|Überschreibt [CMFCVisualManager::OnDrawRibbonCategory](../Topic/CMFCVisualManager::OnDrawRibbonCategory.md).|  
|`CMFCVisualManagerWindows7::OnDrawRibbonCategoryTab`|Überschreibt [CMFCVisualManager::OnDrawRibbonCategoryTab](../Topic/CMFCVisualManager::OnDrawRibbonCategoryTab.md).|  
|`CMFCVisualManagerWindows7::OnDrawRibbonDefaultPaneButton`|Überschreibt [CMFCVisualManager::OnDrawRibbonDefaultPaneButton](../Topic/CMFCVisualManager::OnDrawRibbonDefaultPaneButton.md).|  
|`CMFCVisualManagerWindows7::OnDrawRibbonGalleryButton`|Überschreibt [CMFCVisualManager::OnDrawRibbonGalleryButton](../Topic/CMFCVisualManager::OnDrawRibbonGalleryButton.md).|  
|`CMFCVisualManagerWindows7::OnDrawRibbonLaunchButton`|Überschreibt `CMFCVisualManager::OnDrawRibbonLaunchButton`.|  
|`CMFCVisualManagerWindows7::OnDrawRibbonMenuCheckFrame`|Überschreibt [CMFCVisualManager::OnDrawRibbonMenuCheckFrame](../Topic/CMFCVisualManager::OnDrawRibbonMenuCheckFrame.md).|  
|`CMFCVisualManagerWindows7::OnDrawRibbonPanel`|Überschreibt [CMFCVisualManager::OnDrawRibbonPanel](../Topic/CMFCVisualManager::OnDrawRibbonPanel.md).|  
|`CMFCVisualManagerWindows7::OnDrawRibbonPanelCaption`|Überschreibt [CMFCVisualManager::OnDrawRibbonPanelCaption](../Topic/CMFCVisualManager::OnDrawRibbonPanelCaption.md).|  
|`CMFCVisualManagerWindows7::OnDrawRibbonProgressBar`|Überschreibt [CMFCVisualManager::OnDrawRibbonProgressBar](../Topic/CMFCVisualManager::OnDrawRibbonProgressBar.md).|  
|`CMFCVisualManagerWindows7::OnDrawRibbonRecentFilesFrame`|Überschreibt [CMFCVisualManager::OnDrawRibbonRecentFilesFrame](../Topic/CMFCVisualManager::OnDrawRibbonRecentFilesFrame.md).|  
|`CMFCVisualManagerWindows7::OnDrawRibbonSliderChannel`|Überschreibt [CMFCVisualManager::OnDrawRibbonSliderChannel](../Topic/CMFCVisualManager::OnDrawRibbonSliderChannel.md).|  
|`CMFCVisualManagerWindows7::OnDrawRibbonSliderThumb`|Überschreibt [CMFCVisualManager::OnDrawRibbonSliderThumb](../Topic/CMFCVisualManager::OnDrawRibbonSliderThumb.md).|  
|`CMFCVisualManagerWindows7::OnDrawRibbonSliderZoomButton`|Überschreibt [CMFCVisualManager::OnDrawRibbonSliderZoomButton](../Topic/CMFCVisualManager::OnDrawRibbonSliderZoomButton.md).|  
|`CMFCVisualManagerWindows7::OnDrawRibbonStatusBarPane`|Überschreibt [CMFCVisualManager::OnDrawRibbonStatusBarPane](../Topic/CMFCVisualManager::OnDrawRibbonStatusBarPane.md).|  
|`CMFCVisualManagerWindows7::OnDrawRibbonTabsFrame`|Überschreibt [CMFCVisualManager::OnDrawRibbonTabsFrame](../Topic/CMFCVisualManager::OnDrawRibbonTabsFrame.md).|  
|`CMFCVisualManagerWindows7::OnDrawStatusBarSizeBox`|Überschreibt [CMFCVisualManagerWindows::OnDrawStatusBarSizeBox](../Topic/CMFCVisualManagerWindows::OnDrawStatusBarSizeBox.md).|  
|`CMFCVisualManagerWindows7::OnFillBarBackground`|Überschreibt [CMFCVisualManagerWindows::OnFillBarBackground](../Topic/CMFCVisualManagerWindows::OnFillBarBackground.md).|  
|`CMFCVisualManagerWindows7::OnFillButtonInterior`|Überschreibt [CMFCVisualManagerWindows::OnFillButtonInterior](../Topic/CMFCVisualManagerWindows::OnFillButtonInterior.md).|  
|[CMFCVisualManagerWindows7::OnFillMenuImageRect](../Topic/CMFCVisualManagerWindows7::OnFillMenuImageRect.md)|Das Framework ruft diese Methode auf, wenn Bereich um Menüelementimages ausfüllt.|  
|`CMFCVisualManagerWindows7::OnFillRibbonButton`|Überschreibt [CMFCVisualManager::OnFillRibbonButton](../Topic/CMFCVisualManager::OnFillRibbonButton.md).|  
|`CMFCVisualManagerWindows7::OnFillRibbonQuickAccessToolBarPopup`|Überschreibt [CMFCVisualManager::OnFillRibbonQuickAccessToolBarPopup](../Topic/CMFCVisualManager::OnFillRibbonQuickAccessToolBarPopup.md).|  
|`CMFCVisualManagerWindows7::OnHighlightMenuItem`|Überschreibt [CMFCVisualManagerWindows::OnHighlightMenuItem](../Topic/CMFCVisualManagerWindows::OnHighlightMenuItem.md).|  
|`CMFCVisualManagerWindows7::OnNcActivate`|Überschreibt [CMFCVisualManager::OnNcActivate](../Topic/CMFCVisualManager::OnNcActivate.md).|  
|`CMFCVisualManagerWindows7::OnNcPaint`|Überschreibt [CMFCVisualManager::OnNcPaint](../Topic/CMFCVisualManager::OnNcPaint.md).|  
|`CMFCVisualManagerWindows7::OnUpdateSystemColors`|Überschreibt [CMFCVisualManagerWindows::OnUpdateSystemColors](../Topic/CMFCVisualManagerWindows::OnUpdateSystemColors.md).|  
|`CMFCVisualManagerWindows7::SetResourceHandle`|Legt das Ressourcenhandle fest, das die Attribute des visuellen Managers beschreibt.|  
|`CMFCVisualManagerWindows7::SetStyle`|Legt das Farbschema des `CMFCVisualManagerWindows7` GUI fest.|  
  
## Hinweise  
 Verwenden Sie die `CMFCVisualManagerWindows7`\-Klasse, um die Darstellung der Anwendung zu ändern, eine standardmäßige [!INCLUDE[win7](../../build/includes/win7_md.md)] Anwendung nachzuahmen.  Diese Klasse ist nicht gültig, wenn die Anwendung auf eine Version von Windows vor [!INCLUDE[win7](../../build/includes/win7_md.md)] ausgeführt wird.  In diesem Szenario verwendet die Anwendung den standardmäßigen visuellen Manager, der in [CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md) definiert ist.  
  
 Das CMFCVisualManagerWindows7 erbt mehrere Methoden von [CMFCVisualManagerWindows Class](../../mfc/reference/cmfcvisualmanagerwindows-class.md) und der `CMFCVisualManager`\-Klasse.  Die Methoden, die im vorherigen Abschnitt aufgeführt werden, sind die Methoden, die zur `CMFCVisualManagerWindows7`\-Klasse neu sind.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCBaseVisualManager](../../mfc/reference/cmfcbasevisualmanager-class.md)  
  
 [CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md)  
  
 [CMFCVisualManagerOfficeXP](../../mfc/reference/cmfcvisualmanagerofficexp-class.md)  
  
 [CMFCVisualManagerWindows](../../mfc/reference/cmfcvisualmanagerwindows-class.md)  
  
 `CMFCVisualManagerWindows7`  
  
## Anforderungen  
 **Header:**  afxvisualmanagerwindows7.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCVisualManager Class](../../mfc/reference/cmfcvisualmanager-class.md)   
 [CMFCVisualManagerWindows Class](../../mfc/reference/cmfcvisualmanagerwindows-class.md)   
 [CMFCVisualManager::SetDefaultManager](../Topic/CMFCVisualManager::SetDefaultManager.md)
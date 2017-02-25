---
title: "CMFCRibbonCategory Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCRibbonCategory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonCategory class"
ms.assetid: 99ba25b6-d060-4fdd-bfab-3c46c22981bb
caps.latest.revision: 38
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 40
---
# CMFCRibbonCategory Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `CMFCRibbonCategory`\-Klasse implementiert eine Menübandregisterkarte, die eine Gruppe von [Menübandbereiche](../../mfc/reference/cmfcribbonpanel-class.md) enthält.  
  
## Syntax  
  
```  
class CMFCRibbonCategory : public CObject  
```  
  
## Mitglieder  
  
### Geschützte Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCRibbonCategory::CMFCRibbonCategory](../Topic/CMFCRibbonCategory::CMFCRibbonCategory.md)|Der \-Konstruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCRibbonCategory::AddHidden](../Topic/CMFCRibbonCategory::AddHidden.md)|Fügt ein ausgeblendetes Element der Menübandkategorie hinzu.|  
|[CMFCRibbonCategory::AddPanel](../Topic/CMFCRibbonCategory::AddPanel.md)|Fügt einen neuen Bereich der Menübandkategorie hinzu.|  
|[CMFCRibbonCategory::CopyFrom](../Topic/CMFCRibbonCategory::CopyFrom.md)||  
|[CMFCRibbonCategory::FindByData](../Topic/CMFCRibbonCategory::FindByData.md)||  
|[CMFCRibbonCategory::FindByID](../Topic/CMFCRibbonCategory::FindByID.md)||  
|[CMFCRibbonCategory::FindPanelWithElem](../Topic/CMFCRibbonCategory::FindPanelWithElem.md)||  
|[CMFCRibbonCategory::GetContextID](../Topic/CMFCRibbonCategory::GetContextID.md)|Gibt die Kontext\-ID der Menübandkategorie zurück.|  
|[CMFCRibbonCategory::GetData](../Topic/CMFCRibbonCategory::GetData.md)|Gibt die benutzerdefinierten Daten zurück, die mit der Menübandkategorie zugeordnet ist.|  
|[CMFCRibbonCategory::GetDroppedDown](../Topic/CMFCRibbonCategory::GetDroppedDown.md)||  
|[CMFCRibbonCategory::GetElements](../Topic/CMFCRibbonCategory::GetElements.md)||  
|[CMFCRibbonCategory::GetElementsByID](../Topic/CMFCRibbonCategory::GetElementsByID.md)||  
|[CMFCRibbonCategory::GetFirstVisibleElement](../Topic/CMFCRibbonCategory::GetFirstVisibleElement.md)|Rufen Sie ein erstes sichtbares Element, das der Menübandkategorie gehören.|  
|[CMFCRibbonCategory::GetFocused](../Topic/CMFCRibbonCategory::GetFocused.md)|Gibt ein den Fokus besitzt Element zurück.|  
|[CMFCRibbonCategory::GetHighlighted](../Topic/CMFCRibbonCategory::GetHighlighted.md)|Gibt ein als Element zurück.|  
|[CMFCRibbonCategory::GetImageCount](../Topic/CMFCRibbonCategory::GetImageCount.md)||  
|[CMFCRibbonCategory::GetImageSize](../Topic/CMFCRibbonCategory::GetImageSize.md)||  
|[CMFCRibbonCategory::GetItemIDsList](../Topic/CMFCRibbonCategory::GetItemIDsList.md)||  
|[CMFCRibbonCategory::GetLastVisibleElement](../Topic/CMFCRibbonCategory::GetLastVisibleElement.md)|Rufen Sie ein letztes sichtbares Element, das der Menübandkategorie gehören|  
|[CMFCRibbonCategory::GetLargeImages](../Topic/CMFCRibbonCategory::GetLargeImages.md)|Gibt einen Verweis auf die Liste von großen Bildern zurück, die die Menübandkategorie verwendet.|  
|[CMFCRibbonCategory::GetMaxHeight](../Topic/CMFCRibbonCategory::GetMaxHeight.md)||  
|[CMFCRibbonCategory::GetName](../Topic/CMFCRibbonCategory::GetName.md)||  
|[CMFCRibbonCategory::GetPanel](../Topic/CMFCRibbonCategory::GetPanel.md)|Gibt einen Zeiger auf Favoritenmenübandbereich zurück, der am angegebenen Index befindet.|  
|[CMFCRibbonCategory::GetPanelCount](../Topic/CMFCRibbonCategory::GetPanelCount.md)|Gibt die Anzahl der Menübandbereichen in der Menübandkategorie zurück.|  
|[CMFCRibbonCategory::GetPanelFromPoint](../Topic/CMFCRibbonCategory::GetPanelFromPoint.md)||  
|[CMFCRibbonCategory::GetPanelIndex](../Topic/CMFCRibbonCategory::GetPanelIndex.md)|Gibt den Index des angegebenen Menübandbereichs zurück.|  
|[CMFCRibbonCategory::GetParentButton](../Topic/CMFCRibbonCategory::GetParentButton.md)||  
|[CMFCRibbonCategory::GetParentMenuBar](../Topic/CMFCRibbonCategory::GetParentMenuBar.md)||  
|[CMFCRibbonCategory::GetParentRibbonBar](../Topic/CMFCRibbonCategory::GetParentRibbonBar.md)||  
|[CMFCRibbonCategory::GetRect](../Topic/CMFCRibbonCategory::GetRect.md)||  
|[CMFCRibbonCategory::GetSmallImages](../Topic/CMFCRibbonCategory::GetSmallImages.md)|Gibt einen Verweis auf die Liste von kleinen Bilds zurück, die die Kategorie verwendet.|  
|[CMFCRibbonCategory::GetTabColor](../Topic/CMFCRibbonCategory::GetTabColor.md)|Gibt die aktuelle Farbe der Menübandkategorienregisterkarte zurück.|  
|[CMFCRibbonCategory::GetTabRect](../Topic/CMFCRibbonCategory::GetTabRect.md)||  
|[CMFCRibbonCategory::GetTextTopLine](../Topic/CMFCRibbonCategory::GetTextTopLine.md)||  
|[CMFCRibbonCategory::GetVisibleElements](../Topic/CMFCRibbonCategory::GetVisibleElements.md)|Abrufen aller sichtbaren Elemente, die der Menübandkategorie gehören.|  
|[CMFCRibbonCategory::HighlightPanel](../Topic/CMFCRibbonCategory::HighlightPanel.md)||  
|[CMFCRibbonCategory::HitTest](../Topic/CMFCRibbonCategory::HitTest.md)||  
|[CMFCRibbonCategory::HitTestEx](../Topic/CMFCRibbonCategory::HitTestEx.md)||  
|[CMFCRibbonCategory::HitTestScrollButtons](../Topic/CMFCRibbonCategory::HitTestScrollButtons.md)||  
|[CMFCRibbonCategory::IsActive](../Topic/CMFCRibbonCategory::IsActive.md)||  
|[CMFCRibbonCategory::IsVisible](../Topic/CMFCRibbonCategory::IsVisible.md)|Bestimmt, ob die Menübandkategorie sichtbar ist.|  
|[CMFCRibbonCategory::IsWindows7Look](../Topic/CMFCRibbonCategory::IsWindows7Look.md)|Gibt an, ob das Menüband Elemente Windows 7\-Formatblick verfügt \(kleine rechteckige Anwendungsschaltfläche\)|  
|[CMFCRibbonCategory::NotifyControlCommand](../Topic/CMFCRibbonCategory::NotifyControlCommand.md)||  
|[CMFCRibbonCategory::OnCancelMode](../Topic/CMFCRibbonCategory::OnCancelMode.md)||  
|[CMFCRibbonCategory::OnDraw](../Topic/CMFCRibbonCategory::OnDraw.md)||  
|[CMFCRibbonCategory::OnDrawImage](../Topic/CMFCRibbonCategory::OnDrawImage.md)||  
|[CMFCRibbonCategory::OnDrawMenuBorder](../Topic/CMFCRibbonCategory::OnDrawMenuBorder.md)||  
|[CMFCRibbonCategory::OnKey](../Topic/CMFCRibbonCategory::OnKey.md)|Aufgerufen vom Framework, wenn ein Benutzer eine Taste drückt.|  
|[CMFCRibbonCategory::OnLButtonDown](../Topic/CMFCRibbonCategory::OnLButtonDown.md)||  
|[CMFCRibbonCategory::OnLButtonUp](../Topic/CMFCRibbonCategory::OnLButtonUp.md)||  
|[CMFCRibbonCategory::OnMouseMove](../Topic/CMFCRibbonCategory::OnMouseMove.md)||  
|[CMFCRibbonCategory::OnRTLChanged](../Topic/CMFCRibbonCategory::OnRTLChanged.md)||  
|[CMFCRibbonCategory::OnScrollHorz](../Topic/CMFCRibbonCategory::OnScrollHorz.md)||  
|[CMFCRibbonCategory::OnUpdateCmdUI](../Topic/CMFCRibbonCategory::OnUpdateCmdUI.md)||  
|[CMFCRibbonCategory::RecalcLayout](../Topic/CMFCRibbonCategory::RecalcLayout.md)||  
|[CMFCRibbonCategory::RemovePanel](../Topic/CMFCRibbonCategory::RemovePanel.md)||  
|[CMFCRibbonCategory::ReposPanels](../Topic/CMFCRibbonCategory::ReposPanels.md)||  
|[CMFCRibbonCategory::SetCollapseOrder](../Topic/CMFCRibbonCategory::SetCollapseOrder.md)|Definiert die Einsturzreihenfolge der Menübandbereiche, die in der Menübandkategorie vorhanden sind.|  
|[CMFCRibbonCategory::SetData](../Topic/CMFCRibbonCategory::SetData.md)|Speichert die benutzerdefinierten Daten in der Menübandkategorie.|  
|[CMFCRibbonCategory::SetKeys](../Topic/CMFCRibbonCategory::SetKeys.md)|Weist der Menübandkategorie ein keytip zu.|  
|[CMFCRibbonCategory::SetName](../Topic/CMFCRibbonCategory::SetName.md)||  
|[CMFCRibbonCategory::SetTabColor](../Topic/CMFCRibbonCategory::SetTabColor.md)|Legt die Farbe der Menübandkategorie fest.|  
  
## Hinweise  
 Normalerweise erstellen Sie eine Menübandkategorie indirekt, indem Sie [CMFCRibbonBar::AddCategory](../Topic/CMFCRibbonBar::AddCategory.md) aufrufen, die einen Zeiger auf die neu erstellten Menübandkategorie zurückgibt.  Sie fügen Bereiche der Kategorie hinzu, indem Sie [CMFCRibbonCategory::AddPanel](../Topic/CMFCRibbonCategory::AddPanel.md) aufrufen.  
  
 Die Klasse zeichnet `CMFCRibbonTab` Menübandkategorien.  Wird von [CMFCRibbonBaseElement Class](../../mfc/reference/cmfcribbonbaseelement-class.md) abgeleitet.  
  
 Das folgende Beispiel zeigt, wie eine Menübandkategorie erstellt und ihr einen Bereich hinzugefügt wird.  
  
 `// Create a new ribbon category and get a pointer to it`  
  
 `CMFCRibbonCategory* pCategory = m_wndRibbonBar.AddCategory`  
  
 `(_T("&Write"),           // Category name`  
  
 `IDB_WRITE,              // Category small images (16 x 16)`  
  
 `IDB_WRITE_LARGE);   // Category large images (32 x 32)`  
  
 `// Add a panel to the new category`  
  
 `CMFCRibbonPanel* pPanel = pCategory->AddPanel (`  
  
 `_T("Clipboard"),                       // Panel name`  
  
 `m_PanelIcons.ExtractIcon (0));  // Panel icon`  
  
 Das folgende Diagramm zeigt eine Abbildung der privaten Kategorie in der RibbonApp\-Beispielanwendung an.  
  
 ![CMFCRibbonCategory&#45;Bild](../../mfc/reference/media/cmfcribboncategory.png "CMFCRibbonCategory")  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonCategory](../../mfc/reference/cmfcribboncategory-class.md)  
  
## Anforderungen  
 **Header:** afxribboncategory.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)
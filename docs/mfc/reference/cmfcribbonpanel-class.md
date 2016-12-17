---
title: "CMFCRibbonPanel Class"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "CMFCRibbonPanel"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonPanel class"
ms.assetid: 51d70749-1140-4386-b103-f14082049ba6
caps.latest.revision: 34
caps.handback.revision: "23"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCRibbonPanel Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implementiert einen Bereich, der einen Satz von Menübandelemente enthält.  Wenn der Bereich gezeichnet wird, wird er so viele Elemente an, wie möglich, die Größe des Bereichs angegeben.  
  
## Syntax  
  
```  
class CMFCRibbonPanel : public CObject  
```  
  
## Mitglieder  
  
### Geschützte Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCRibbonPanel::CMFCRibbonPanel](../Topic/CMFCRibbonPanel::CMFCRibbonPanel.md)|erstellt und initialisiert ein `CMFCRibbonPanel`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCRibbonPanel::Add](../Topic/CMFCRibbonPanel::Add.md)|Fügt ein Menübandelement dem Bereich hinzu.|  
|[CMFCRibbonPanel::AddSeparator](../Topic/CMFCRibbonPanel::AddSeparator.md)|Fügt ein Trennzeichen dem Favoritenmenübandbereich hinzu.|  
|[CMFCRibbonPanel::AddToolBar](../Topic/CMFCRibbonPanel::AddToolBar.md)|Fügt eine Symbolleiste dem Favoritenmenübandbereich hinzu.|  
|[CMFCRibbonPanel::FindByData](../Topic/CMFCRibbonPanel::FindByData.md)||  
|[CMFCRibbonPanel::FindByID](../Topic/CMFCRibbonPanel::FindByID.md)|Gibt ein Element zurück, das durch die angegebene Befehl ID identifiziert wird|  
|[CMFCRibbonPanel::GetCaptionHeight](../Topic/CMFCRibbonPanel::GetCaptionHeight.md)||  
|[CMFCRibbonPanel::GetCount](../Topic/CMFCRibbonPanel::GetCount.md)|Gibt die Anzahl der Elemente im Favoritenmenübandbereich zurück.|  
|[CMFCRibbonPanel::GetData](../Topic/CMFCRibbonPanel::GetData.md)|Gibt die benutzerdefinierten Daten zurück, die dem Bereich zugeordnet sind.|  
|[CMFCRibbonPanel::GetDefaultButton](../Topic/CMFCRibbonPanel::GetDefaultButton.md)||  
|[CMFCRibbonPanel::GetDroppedDown](../Topic/CMFCRibbonPanel::GetDroppedDown.md)||  
|[CMFCRibbonPanel::GetElement](../Topic/CMFCRibbonPanel::GetElement.md)|Gibt das Menübandelement zurück, das an einem angegebenen Index befindet.|  
|[CMFCRibbonPanel::GetElements](../Topic/CMFCRibbonPanel::GetElements.md)|Ruft alle Elemente ab, die im Favoritenmenübandbereich enthalten sind.|  
|[CMFCRibbonPanel::GetElementsByID](../Topic/CMFCRibbonPanel::GetElementsByID.md)||  
|[CMFCRibbonPanel::GetFocused](../Topic/CMFCRibbonPanel::GetFocused.md)|Gibt ein den Fokus besitzt Element zurück.|  
|[CMFCRibbonPanel::GetGalleryRect](../Topic/CMFCRibbonPanel::GetGalleryRect.md)|Gibt ein umschließendes Rechteck des Katalogelements zurück.|  
|[CMFCRibbonPanel::GetHighlighted](../Topic/CMFCRibbonPanel::GetHighlighted.md)||  
|[CMFCRibbonPanel::GetIndex](../Topic/CMFCRibbonPanel::GetIndex.md)||  
|[CMFCRibbonPanel::GetItemIDsList](../Topic/CMFCRibbonPanel::GetItemIDsList.md)||  
|[CMFCRibbonPanel::GetName](../Topic/CMFCRibbonPanel::GetName.md)||  
|[CMFCRibbonPanel::GetParentButton](../Topic/CMFCRibbonPanel::GetParentButton.md)||  
|[CMFCRibbonPanel::GetParentCategory](../Topic/CMFCRibbonPanel::GetParentCategory.md)|Gibt die übergeordnete Kategorie des Menübandbereichs zurück.|  
|[CMFCRibbonPanel::GetParentMenuBar](../Topic/CMFCRibbonPanel::GetParentMenuBar.md)||  
|[CMFCRibbonPanel::GetPreferedMenuLocation](../Topic/CMFCRibbonPanel::GetPreferedMenuLocation.md)||  
|[CMFCRibbonPanel::GetPressed](../Topic/CMFCRibbonPanel::GetPressed.md)||  
|[CMFCRibbonPanel::GetRect](../Topic/CMFCRibbonPanel::GetRect.md)||  
|[CMFCRibbonPanel::GetVisibleElements](../Topic/CMFCRibbonPanel::GetVisibleElements.md)|Ruft ein Array sichtbare Elemente.|  
|[CMFCRibbonPanel::HasElement](../Topic/CMFCRibbonPanel::HasElement.md)||  
|[CMFCRibbonPanel::HitTest](../Topic/CMFCRibbonPanel::HitTest.md)||  
|[CMFCRibbonPanel::HitTestEx](../Topic/CMFCRibbonPanel::HitTestEx.md)||  
|[CMFCRibbonPanel::Insert](../Topic/CMFCRibbonPanel::Insert.md)|Fügt ein Menübandelement an der angegebenen Position ein.|  
|[CMFCRibbonPanel::InsertSeparator](../Topic/CMFCRibbonPanel::InsertSeparator.md)|Fügt ein Trennzeichen an der angegebenen Position ein.|  
|[CMFCRibbonPanel::IsCenterColumnVert](../Topic/CMFCRibbonPanel::IsCenterColumnVert.md)|Gibt an, ob alle Panel\-Elemente vertikal zentriert ausgerichtet werden sollen \(\) werden durch Spalte.|  
|[CMFCRibbonPanel::IsCollapsed](../Topic/CMFCRibbonPanel::IsCollapsed.md)||  
|[CMFCRibbonPanel::IsHighlighted](../Topic/CMFCRibbonPanel::IsHighlighted.md)||  
|[CMFCRibbonPanel::IsJustifyColumns](../Topic/CMFCRibbonPanel::IsJustifyColumns.md)|Gibt an, ob alle Bereichsspalten die gleiche Breite haben.|  
|[CMFCRibbonPanel::IsMainPanel](../Topic/CMFCRibbonPanel::IsMainPanel.md)||  
|[CMFCRibbonPanel::IsMenuMode](../Topic/CMFCRibbonPanel::IsMenuMode.md)||  
|[CMFCRibbonPanel::MakeGalleryItemVisible](../Topic/CMFCRibbonPanel::MakeGalleryItemVisible.md)|Führt den Katalog Bildlauf, um das angegebene Menübandelement sichtbar zu machen.|  
|[CMFCRibbonPanel::OnKey](../Topic/CMFCRibbonPanel::OnKey.md)||  
|[CMFCRibbonPanel::RecalcWidths](../Topic/CMFCRibbonPanel::RecalcWidths.md)||  
|[CMFCRibbonPanel::Remove](../Topic/CMFCRibbonPanel::Remove.md)|Entfernt und löscht optional ein Element, das am angegebenen Index befindet.|  
|[CMFCRibbonPanel::RemoveAll](../Topic/CMFCRibbonPanel::RemoveAll.md)|Entfernt alle Elemente aus Favoritenmenübandbereich.|  
|[CMFCRibbonPanel::Replace](../Topic/CMFCRibbonPanel::Replace.md)|Ersetzt ein Element von anderen anhand ihrer jeweiligen Indexwerte.|  
|[CMFCRibbonPanel::ReplaceByID](../Topic/CMFCRibbonPanel::ReplaceByID.md)|Ersetzt ein Element von anderen auf Grundlage einer angegebene Befehl ID|  
|[CMFCRibbonPanel::SetCenterColumnVert](../Topic/CMFCRibbonPanel::SetCenterColumnVert.md)|Sortiert den Bereich, Elemente, durch Spalte vertikal auszurichten.|  
|[CMFCRibbonPanel::SetData](../Topic/CMFCRibbonPanel::SetData.md)|Benutzerdefinierte Daten der Mitarbeiter mit dem Favoritenmenübandbereich.|  
|[CMFCRibbonPanel::SetElementMenu](../Topic/CMFCRibbonPanel::SetElementMenu.md)|Weist ein von dem Element zu, das die angegebene Befehl ID besitzt|  
|[CMFCRibbonPanel::SetElementRTC](../Topic/CMFCRibbonPanel::SetElementRTC.md)|Fügt ein Menübandelement hinzu, das durch die bereitgestellten Ablaufklasseninformationen dem Favoritenmenübandbereich angegeben wird.|  
|[CMFCRibbonPanel::SetElementRTCByID](../Topic/CMFCRibbonPanel::SetElementRTCByID.md)|Fügt ein Menübandelement hinzu, das durch die bereitgestellten Ablaufklasseninformationen dem Favoritenmenübandbereich angegeben wird.|  
|[CMFCRibbonPanel::SetFocused](../Topic/CMFCRibbonPanel::SetFocused.md)|Festlegen des Fokus auf das Menübandelement angegebenen.|  
|[CMFCRibbonPanel::SetJustifyColumns](../Topic/CMFCRibbonPanel::SetJustifyColumns.md)|Aktiviert oder deaktiviert Spaltenrechtfertigung.|  
|[CMFCRibbonPanel::SetKeys](../Topic/CMFCRibbonPanel::SetKeys.md)|Legt die Tastenkombination fest, die den Favoritenmenübandbereich anzeigt.|  
|[CMFCRibbonPanel::ShowPopup](../Topic/CMFCRibbonPanel::ShowPopup.md)||  
  
## Hinweise  
 Menübandbereiche sind logische Gruppierungen von verwandten Aufgaben, die Sie in der Menübandkategorien erstellen.  Während die Größe des Menübands ändert, passt das Bereichslayout automatisch, so viele Elemente möglich anzuzeigen.  
  
 Sie können Bereiche eines Menübands abrufen, das in einer Menübandkategorie enthalten ist, indem Sie die [CMFCRibbonCategory::GetPanel](../Topic/CMFCRibbonCategory::GetPanel.md)\-Methode aufruft.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie ein Objekt `CMFCRibbonPanel` konfiguriert, indem verschiedene Methoden in der `CMFCRibbonPanel`\-Klasse angewendet wird.  Im Beispiel wird gezeigt, wie die Tastenkombination, die den Favoritenmenübandbereich anzeigt, ausrichten Elemente im Bereich vertikal von Spalte und aktivieren Spaltenrechtfertigung festgelegt wird.  Dieser Codeausschnitt ist Teil [MS Office\-Demobeispiel 2007](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_MSOffice2007Demo#10](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_MSOffice2007Demo#10)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonPanel](../../mfc/reference/cmfcribbonpanel-class.md)  
  
## Anforderungen  
 **Header:** afxRibbonPanel.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [CMFCRibbonCategory Class](../../mfc/reference/cmfcribboncategory-class.md)   
 [CMFCRibbonBaseElement Class](../../mfc/reference/cmfcribbonbaseelement-class.md)
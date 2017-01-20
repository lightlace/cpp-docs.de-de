---
title: "CListCtrl Class"
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
  - "CListCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CListCtrl-Klasse"
  - "list view controls"
  - "list view controls, CListCtrl-Klasse"
  - "LVS_ICON"
  - "LVS_LIST"
  - "LVS_REPORT"
  - "LVS_SMALLICON"
  - "Windows common controls [C++], CListCtrl"
ms.assetid: fe08a1ca-4b05-4ff7-a12a-ee4c765a2197
caps.latest.revision: 23
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# CListCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Kapselt die Funktionalität eines Listenansicht\-Steuerelements "," zeigt das eine Auflistung Elemente jede an, die einem Symbol besteht \(von einer Bildliste\) und einer Bezeichnung.  
  
## Syntax  
  
```  
class CListCtrl : public CWnd  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CListCtrl::CListCtrl](../Topic/CListCtrl::CListCtrl.md)|Erstellt ein `CListCtrl`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CListCtrl::ApproximateViewRect](../Topic/CListCtrl::ApproximateViewRect.md)|Bestimmt die Breite und Höhe, die erforderlich sind, um die Elemente eines Listenansicht\-Steuerelements anzuzeigen.|  
|[CListCtrl::Arrange](../Topic/CListCtrl::Arrange.md)|Richtet Elemente in einem Raster aus.|  
|[CListCtrl::CancelEditLabel](../Topic/CListCtrl::CancelEditLabel.md)|Bricht Elementtextbearbeitungsvorgang ab.|  
|[CListCtrl::Create](../Topic/CListCtrl::Create.md)|Erstellt ein Listensteuerelement und fügt es zu einem `CListCtrl`\-Objekt.|  
|[CListCtrl::CreateDragImage](../Topic/CListCtrl::CreateDragImage.md)|Erstellt eine Ziehbildliste für ein angegebenes Element.|  
|[CListCtrl::CreateEx](../Topic/CListCtrl::CreateEx.md)|Erstellt ein Listensteuerelement mit den angegebenen Windows\-erweitertenFormaten und fügt es zu einem `CListCtrl`\-Objekt.|  
|[CListCtrl::DeleteAllItems](../Topic/CListCtrl::DeleteAllItems.md)|Löscht alle Elemente aus dem Steuerelement.|  
|[CListCtrl::DeleteColumn](../Topic/CListCtrl::DeleteColumn.md)|Löscht eine Spalte aus dem ListView\-Steuerelement.|  
|[CListCtrl::DeleteItem](../Topic/CListCtrl::DeleteItem.md)|Löscht ein Element des Steuerelements.|  
|[CListCtrl::DrawItem](../Topic/CListCtrl::DrawItem.md)|Aufgerufen wenn ein visueller Aspekt von Ownerdrawnsteueränderungen.|  
|[CListCtrl::EditLabel](../Topic/CListCtrl::EditLabel.md)|Startet die direkte Bearbeitung Text eines Elements.|  
|[CListCtrl::EnableGroupView](../Topic/CListCtrl::EnableGroupView.md)|Aktiviert oder deaktiviert die ob Elemente in einer Listenansicht, die als Gruppe Anzeige ist.|  
|[CListCtrl::EnsureVisible](../Topic/CListCtrl::EnsureVisible.md)|Stellt sicher, dass ein Element sichtbar ist.|  
|[CListCtrl::FindItem](../Topic/CListCtrl::FindItem.md)|Suchen nach einem Listenansichtelement, das Eigenschaften angegeben wird.|  
|[CListCtrl::GetBkColor](../Topic/CListCtrl::GetBkColor.md)|Ruft die Hintergrundfarbe eines Listenansicht\-Steuerelements ab.|  
|[CListCtrl::GetBkImage](../Topic/CListCtrl::GetBkImage.md)|Ruft das aktuelle Hintergrundbild eines Listenansicht\-Steuerelements ab.|  
|[CListCtrl::GetCallbackMask](../Topic/CListCtrl::GetCallbackMask.md)|Ruft die Rückrufmaske für ein Listenansicht\-Steuerelement ab.|  
|[CListCtrl::GetCheck](../Topic/CListCtrl::GetCheck.md)|Ruft den aktuellen Anzeigenstatus des die Zustandsbilder ab, das einem Element zugeordnet ist.|  
|[CListCtrl::GetColumn](../Topic/CListCtrl::GetColumn.md)|Ruft die Attribute einer Spalte des ab.|  
|[CListCtrl::GetColumnOrderArray](../Topic/CListCtrl::GetColumnOrderArray.md)|Ruft die Spaltenreihenfolge \(von links nach rechts\) eines Listenansicht\-Steuerelements ab.|  
|[CListCtrl::GetColumnWidth](../Topic/CListCtrl::GetColumnWidth.md)|Ruft die Breite einer Spalte in der Berichtsansicht oder \-Listenansicht ab.|  
|[CListCtrl::GetCountPerPage](../Topic/CListCtrl::GetCountPerPage.md)|Berechnet die Anzahl von Elementen, die in ein ListView\-Steuerelement vertikal anpassen können.|  
|[CListCtrl::GetEditControl](../Topic/CListCtrl::GetEditControl.md)|Ruft das Handle des Bearbeitungssteuerelements ab, das verwendet wird, um den Text eines Elements zu bearbeiten.|  
|[CListCtrl::GetEmptyText](../Topic/CListCtrl::GetEmptyText.md)|Ruft die Zeichenfolge ab, die angezeigt werden, wenn das aktuelle Listenansicht\-Steuerelement leer ist.|  
|[CListCtrl::GetExtendedStyle](../Topic/CListCtrl::GetExtendedStyle.md)|Ruft die aktuellen erweiterten Formate eines Listenansicht\-Steuerelements ab.|  
|[CListCtrl::GetFirstSelectedItemPosition](../Topic/CListCtrl::GetFirstSelectedItemPosition.md)|Ruft die Position des ersten ausgewählten Listenansichtelements in einem ListView\-Steuerelement ab.|  
|[CListCtrl::GetFocusedGroup](../Topic/CListCtrl::GetFocusedGroup.md)|Ruft die Gruppe ab, die den Tastaturfokus im aktuellen Listenansicht\-Steuerelement verfügt.|  
|[CListCtrl::GetGroupCount](../Topic/CListCtrl::GetGroupCount.md)|Ruft die Anzahl von Gruppen im aktuellen Listenansicht\-Steuerelement ab.|  
|[CListCtrl::GetGroupInfo](../Topic/CListCtrl::GetGroupInfo.md)|Ruft die Informationen für eine angegebene Gruppe des Listenansicht\-Steuerelements ab.|  
|[CListCtrl::GetGroupInfoByIndex](../Topic/CListCtrl::GetGroupInfoByIndex.md)|Ruft Informationen über eine bestimmte Gruppe im aktuellen Listenansicht\-Steuerelement ab.|  
|[CListCtrl::GetGroupMetrics](../Topic/CListCtrl::GetGroupMetrics.md)|Ruft die Metriken einer Gruppe ab.|  
|[CListCtrl::GetGroupRect](../Topic/CListCtrl::GetGroupRect.md)|Ruft das umschließende Rechteck für eine angegebene Gruppe im aktuellen Listenansicht\-Steuerelement ab.|  
|[CListCtrl::GetGroupState](../Topic/CListCtrl::GetGroupState.md)|Ruft den Zustand für eine angegebene Gruppe im aktuellen Listenansicht\-Steuerelement ab.|  
|[CListCtrl::GetHeaderCtrl](../Topic/CListCtrl::GetHeaderCtrl.md)|Ruft das Header\-Steuerelement eines Listenansicht\-Steuerelements ab.|  
|[CListCtrl::GetHotCursor](../Topic/CListCtrl::GetHotCursor.md)|Ruft den verwendeten Cursor ab, wenn das Hottracking für ein Listenansicht\-Steuerelement aktiviert ist.|  
|[CListCtrl::GetHotItem](../Topic/CListCtrl::GetHotItem.md)|Ruft das Listenansichtelement direkt unter dem Cursor ab.|  
|[CListCtrl::GetHoverTime](../Topic/CListCtrl::GetHoverTime.md)|Ruft die aktuelle Hoverzeit eines Listenansicht\-Steuerelements ab.|  
|[CListCtrl::GetImageList](../Topic/CListCtrl::GetImageList.md)|Ruft das Handle einer Bildliste ab, die zum Zeichnen von Listenansichtelementen verwendet wird.|  
|[CListCtrl::GetInsertMark](../Topic/CListCtrl::GetInsertMark.md)|Ruft die aktuelle Position der Einfügemarke ab.|  
|[CListCtrl::GetInsertMarkColor](../Topic/CListCtrl::GetInsertMarkColor.md)|Ruft die aktuelle Farbe der Einfügemarke ab.|  
|[CListCtrl::GetInsertMarkRect](../Topic/CListCtrl::GetInsertMarkRect.md)|Ruft das Rechteck ab, die die Einfügemarke begrenzt.|  
|[CListCtrl::GetItem](../Topic/CListCtrl::GetItem.md)|Ruft die Attribute eines Listenansichtelements ab.|  
|[CListCtrl::GetItemCount](../Topic/CListCtrl::GetItemCount.md)|Ruft die Anzahl der Elemente in einem ListView\-Steuerelement ab.|  
|[CListCtrl::GetItemData](../Topic/CListCtrl::GetItemData.md)|Ruft den anwendungsspezifischen Wert ab, der einem Element zugeordnet ist.|  
|[CListCtrl::GetItemIndexRect](../Topic/CListCtrl::GetItemIndexRect.md)|Ruft das umschließende Rechteck für alle oder nur einen Teil eines Unterelements im aktuellen Listenansicht\-Steuerelement ab.|  
|[CListCtrl::GetItemPosition](../Topic/CListCtrl::GetItemPosition.md)|Ruft die Position eines Listenansichtelements ab.|  
|[CListCtrl::GetItemRect](../Topic/CListCtrl::GetItemRect.md)|Ruft das umschließende Rechteck für ein Element ab.|  
|[CListCtrl::GetItemSpacing](../Topic/CListCtrl::GetItemSpacing.md)|Berechnet den Abstand zwischen Elementen im aktuellen Listenansicht\-Steuerelement.|  
|[CListCtrl::GetItemState](../Topic/CListCtrl::GetItemState.md)|Ruft den Zustand eines Listenansichtelements ab.|  
|[CListCtrl::GetItemText](../Topic/CListCtrl::GetItemText.md)|Ruft den Text eines Listenansichtelements oder des Unterelements ab.|  
|[CListCtrl::GetNextItem](../Topic/CListCtrl::GetNextItem.md)|Suchen nach einem Listenansichtelement mit angegebenen Eigenschaften und mit angegebener Beziehung zu einem angegebenen Element.|  
|[CListCtrl::GetNextItemIndex](../Topic/CListCtrl::GetNextItemIndex.md)|Ruft den Index des Elements im aktuellen Listenansicht\-Steuerelement ab, das einen angegebenen Satz von Eigenschaften verfügt.|  
|[CListCtrl::GetNextSelectedItem](../Topic/CListCtrl::GetNextSelectedItem.md)|Ruft den Index einer Listenansichtelementposition und die Position des folgenden ausgewählten Listenansichtelements zum Durchlaufen ab.|  
|[CListCtrl::GetNumberOfWorkAreas](../Topic/CListCtrl::GetNumberOfWorkAreas.md)|Ruft die aktuelle Anzahl von Arbeitsbereichen für ein Listenansicht\-Steuerelement ab.|  
|[CListCtrl::GetOrigin](../Topic/CListCtrl::GetOrigin.md)|Ruft den Ursprung der aktuellen Ansicht ein Listenansicht\-Steuerelement ab.|  
|[CListCtrl::GetOutlineColor](../Topic/CListCtrl::GetOutlineColor.md)|Ruft die Farbe des Rahmens eines Listenansicht\-Steuerelements ab.|  
|[CListCtrl::GetSelectedColumn](../Topic/CListCtrl::GetSelectedColumn.md)|Ruft den Index der ausgewählten Spalte im Listensteuerelement ab.|  
|[CListCtrl::GetSelectedCount](../Topic/CListCtrl::GetSelectedCount.md)|Ruft die Anzahl der ausgewählten Elemente im ListView\-Steuerelement ab.|  
|[CListCtrl::GetSelectionMark](../Topic/CListCtrl::GetSelectionMark.md)|Ruft die Auswahlmarke eines Listenansicht\-Steuerelements ab.|  
|[CListCtrl::GetStringWidth](../Topic/CListCtrl::GetStringWidth.md)|Bestimmt die minimale Spaltenbreite, die erforderlich ist, die ganze angegebene Zeichenfolge anzuzeigen.|  
|[CListCtrl::GetSubItemRect](../Topic/CListCtrl::GetSubItemRect.md)|Ruft das umgebende Rechteck eines Elements in einem ListView\-Steuerelement ab.|  
|[CListCtrl::GetTextBkColor](../Topic/CListCtrl::GetTextBkColor.md)|Ruft die Texthintergrundfarbe eines Listenansicht\-Steuerelements ab.|  
|[CListCtrl::GetTextColor](../Topic/CListCtrl::GetTextColor.md)|Ruft die Textfarbe eines Listenansicht\-Steuerelements ab.|  
|[CListCtrl::GetTileInfo](../Topic/CListCtrl::GetTileInfo.md)|Ruft Informationen zu einer Kachel in einem ListView\-Steuerelement ab.|  
|[CListCtrl::GetTileViewInfo](../Topic/CListCtrl::GetTileViewInfo.md)|Ruft Informationen über ein Listenansicht\-Steuerelement in der Tile\-Ansicht ab.|  
|[CListCtrl::GetToolTips](../Topic/CListCtrl::GetToolTips.md)|Ruft das QuickInfosteuerelement ab, dem das ListView\-Steuerelement verwendet, um QuickInfo anzuzeigen.|  
|[CListCtrl::GetTopIndex](../Topic/CListCtrl::GetTopIndex.md)|Ruft den Index des obersten sichtbaren Elements ab.|  
|[CListCtrl::GetView](../Topic/CListCtrl::GetView.md)|Ruft die Ansicht des Listenansicht\-Steuerelements ab.|  
|[CListCtrl::GetViewRect](../Topic/CListCtrl::GetViewRect.md)|Ruft das umschließende Rechteck aller Elemente im ListView\-Steuerelement ab.|  
|[CListCtrl::GetWorkAreas](../Topic/CListCtrl::GetWorkAreas.md)|Ruft die aktuellen Arbeitsbereiche eines Listenansicht\-Steuerelements ab.|  
|[CListCtrl::HasGroup](../Topic/CListCtrl::HasGroup.md)|Bestimmt, ob das ListView\-Steuerelement die angegebene Gruppe verfügt.|  
|[CListCtrl::HitTest](../Topic/CListCtrl::HitTest.md)|Bestimmt, das Listenansichtelement in einer angegebenen Position befindet.|  
|[CListCtrl::InsertColumn](../Topic/CListCtrl::InsertColumn.md)|Fügt eine neue Spalte in einem ListView\-Steuerelement ein.|  
|[CListCtrl::InsertGroup](../Topic/CListCtrl::InsertGroup.md)|Fügt eine Gruppe in das ListView\-Steuerelement ein.|  
|[CListCtrl::InsertGroupSorted](../Topic/CListCtrl::InsertGroupSorted.md)|Fügt die angegebene Gruppe in eine sortierte Liste von Gruppen ein.|  
|[CListCtrl::InsertItem](../Topic/CListCtrl::InsertItem.md)|Fügt ein neues Element in einem ListView\-Steuerelement ein.|  
|[CListCtrl::InsertMarkHitTest](../Topic/CListCtrl::InsertMarkHitTest.md)|Ruft die Einfügemarke ab, die einem angegebenen Punkt am nächsten ist.|  
|[CListCtrl::IsGroupViewEnabled](../Topic/CListCtrl::IsGroupViewEnabled.md)|Bestimmt, ob Gruppenansicht für ein Listenansicht\-Steuerelement aktiviert ist.|  
|[CListCtrl::IsItemVisible](../Topic/CListCtrl::IsItemVisible.md)|Gibt an, ob ein angegebenes Element im aktuellen Listenansicht\-Steuerelement sichtbar ist.|  
|[CListCtrl::MapIDToIndex](../Topic/CListCtrl::MapIDToIndex.md)|Ordnet die eindeutige ID eines Elements im aktuellen Listenansicht\-Steuerelement zu einem Index zu.|  
|[CListCtrl::MapIndexToID](../Topic/CListCtrl::MapIndexToID.md)|Ordnet den Index eines Elements im aktuellen Listenansicht\-Steuerelement auf eine eindeutige ID zu|  
|[CListCtrl::MoveGroup](../Topic/CListCtrl::MoveGroup.md)|Befördert die angegebene Gruppe.|  
|[CListCtrl::MoveItemToGroup](../Topic/CListCtrl::MoveItemToGroup.md)|Verschiebt die angegebene Gruppe auf den angegebenen nullbasierten Index des Listenansicht\-Steuerelements.|  
|[CListCtrl::RedrawItems](../Topic/CListCtrl::RedrawItems.md)|Erzwingt ein ListView\-Steuerelement, um einen Bereich von Elementen neu zu zeichnen.|  
|[CListCtrl::RemoveAllGroups](../Topic/CListCtrl::RemoveAllGroups.md)|Entfernt alle Gruppen aus einem Listenansicht\-Steuerelement.|  
|[CListCtrl::RemoveGroup](../Topic/CListCtrl::RemoveGroup.md)|Entfernt die angegebene Gruppe im ListView\-Steuerelement.|  
|[CListCtrl::Scroll](../Topic/CListCtrl::Scroll.md)|Führt den Inhalt eines Listenansicht\-Steuerelements aus.|  
|[CListCtrl::SetBkColor](../Topic/CListCtrl::SetBkColor.md)|Legt die Hintergrundfarbe des Listenansicht\-Steuerelements fest.|  
|[CListCtrl::SetBkImage](../Topic/CListCtrl::SetBkImage.md)|Legt das aktuelle Hintergrundbild eines Listenansicht\-Steuerelements fest.|  
|[CListCtrl::SetCallbackMask](../Topic/CListCtrl::SetCallbackMask.md)|Legt die Rückrufmaske für ein Listenansicht\-Steuerelement fest.|  
|[CListCtrl::SetCheck](../Topic/CListCtrl::SetCheck.md)|Legt den aktuellen Anzeigenstatus des die Zustandsbilder fest, das einem Element zugeordnet ist.|  
|[CListCtrl::SetColumn](../Topic/CListCtrl::SetColumn.md)|Legt die Attribute einer Listenansichtsspalte fest.|  
|[CListCtrl::SetColumnOrderArray](../Topic/CListCtrl::SetColumnOrderArray.md)|Legt die Spaltenreihenfolge \(von links nach rechts\) eines Listenansicht\-Steuerelements fest.|  
|[CListCtrl::SetColumnWidth](../Topic/CListCtrl::SetColumnWidth.md)|Ändert die Breite einer Spalte in der Berichtsansicht oder \-Listenansicht.|  
|[CListCtrl::SetExtendedStyle](../Topic/CListCtrl::SetExtendedStyle.md)|Legt die aktuellen erweiterten Formate eines Listenansicht\-Steuerelements fest.|  
|[CListCtrl::SetGroupInfo](../Topic/CListCtrl::SetGroupInfo.md)|Legt die Informationen für die angegebene Gruppe eines Listenansicht\-Steuerelements fest.|  
|[CListCtrl::SetGroupMetrics](../Topic/CListCtrl::SetGroupMetrics.md)|Legt die Gruppenmetrik eines Listenansicht\-Steuerelements fest.|  
|[CListCtrl::SetHotCursor](../Topic/CListCtrl::SetHotCursor.md)|Legt den verwendeten Cursor fest, wenn das Hottracking für ein Listenansicht\-Steuerelement aktiviert ist.|  
|[CListCtrl::SetHotItem](../Topic/CListCtrl::SetHotItem.md)|Legt das aktuelle hervorgehobene Element eines Listenansicht\-Steuerelements fest.|  
|[CListCtrl::SetHoverTime](../Topic/CListCtrl::SetHoverTime.md)|Legt die aktuelle Hoverzeit eines Listenansicht\-Steuerelements fest.|  
|[CListCtrl::SetIconSpacing](../Topic/CListCtrl::SetIconSpacing.md)|Legt den Abstand zwischen Symbolen in einem ListView\-Steuerelement fest.|  
|[CListCtrl::SetImageList](../Topic/CListCtrl::SetImageList.md)|Weist eine Bildliste zu einem Listenansicht\-Steuerelement zu.|  
|[CListCtrl::SetInfoTip](../Topic/CListCtrl::SetInfoTip.md)|Legt den QuickInfo\-Text fest.|  
|[CListCtrl::SetInsertMark](../Topic/CListCtrl::SetInsertMark.md)|Legt die Einfügemarke zur definierten Position fest.|  
|[CListCtrl::SetInsertMarkColor](../Topic/CListCtrl::SetInsertMarkColor.md)|Legt die Farbe der Einfügemarke fest.|  
|[CListCtrl::SetItem](../Topic/CListCtrl::SetItem.md)|Legt mehrere oder alle Attribute eines Listenansichtelements fest.|  
|[CListCtrl::SetItemCount](../Topic/CListCtrl::SetItemCount.md)|Bereitet ein ListView\-Steuerelement zum Hinzufügen vieler Elemente vor.|  
|[CListCtrl::SetItemCountEx](../Topic/CListCtrl::SetItemCountEx.md)|Legt die Elementanzahl für ein virtuelles Listenansicht\-Steuerelement fest.|  
|[CListCtrl::SetItemData](../Topic/CListCtrl::SetItemData.md)|Legt den anwendungsspezifischen Wert des Elements fest.|  
|[CListCtrl::SetItemIndexState](../Topic/CListCtrl::SetItemIndexState.md)|Legt den Zustand eines Elements im aktuellen Listenansicht\-Steuerelement fest.|  
|[CListCtrl::SetItemPosition](../Topic/CListCtrl::SetItemPosition.md)|Verschiebt ein Element an eine angegebene Position in einem ListView\-Steuerelement.|  
|[CListCtrl::SetItemState](../Topic/CListCtrl::SetItemState.md)|Ändert den Zustand eines Elements in einem ListView\-Steuerelement.|  
|[CListCtrl::SetItemText](../Topic/CListCtrl::SetItemText.md)|Ändert den Text eines Listenansichtelements oder des Unterelements.|  
|[CListCtrl::SetOutlineColor](../Topic/CListCtrl::SetOutlineColor.md)|Legt die Farbe des Rahmens eines Listenansicht\-Steuerelements fest.|  
|[CListCtrl::SetSelectedColumn](../Topic/CListCtrl::SetSelectedColumn.md)|Legt die ausgewählte Spalte des Listenansicht\-Steuerelements fest.|  
|[CListCtrl::SetSelectionMark](../Topic/CListCtrl::SetSelectionMark.md)|Legt die Auswahlmarke eines Listenansicht\-Steuerelements fest.|  
|[CListCtrl::SetTextBkColor](../Topic/CListCtrl::SetTextBkColor.md)|Legt die Hintergrundfarbe des Texts in einem ListView\-Steuerelement fest.|  
|[CListCtrl::SetTextColor](../Topic/CListCtrl::SetTextColor.md)|Legt die Textfarbe eines Listenansicht\-Steuerelements fest.|  
|[CListCtrl::SetTileInfo](../Topic/CListCtrl::SetTileInfo.md)|Legt die Informationen für eine Kachel des Listenansicht\-Steuerelements fest.|  
|[CListCtrl::SetTileViewInfo](../Topic/CListCtrl::SetTileViewInfo.md)|Enthält Informationen fest, die ein Listenansicht\-Steuerelement in der Tile\-Ansicht verwendet.|  
|[CListCtrl::SetToolTips](../Topic/CListCtrl::SetToolTips.md)|Legt das QuickInfosteuerelement fest, dem das ListView\-Steuerelement verwendet, um QuickInfo anzuzeigen.|  
|[CListCtrl::SetView](../Topic/CListCtrl::SetView.md)|Legt die Ansicht des Listenansicht\-Steuerelements fest.|  
|[CListCtrl::SetWorkAreas](../Topic/CListCtrl::SetWorkAreas.md)|Legt den Bereich fest, in dem Symbole in einem ListView\-Steuerelement angezeigt werden können.|  
|[CListCtrl::SortGroups](../Topic/CListCtrl::SortGroups.md)|Sortiert die Gruppen eines Listenansicht\-Steuerelements mit einer benutzerdefinierten Funktion.|  
|[CListCtrl::SortItems](../Topic/CListCtrl::SortItems.md)|Sortiert Listenansichtelemente mithilfe einer anwendungsdefinierten Vergleichsfunktion.|  
|[CListCtrl::SortItemsEx](../Topic/CListCtrl::SortItemsEx.md)|Sortiert Listenansichtelemente mithilfe einer anwendungsdefinierten Vergleichsfunktion.|  
|[CListCtrl::SubItemHitTest](../Topic/CListCtrl::SubItemHitTest.md)|Bestimmt, die Listenansichtelement ggf. an einer angegebenen Position befindet.|  
|[CListCtrl::Update](../Topic/CListCtrl::Update.md)|Erzwingt das Steuerelement, um ein bestimmtes Element neu zu zeichnen.|  
  
## Hinweise  
 Zusätzlich zu einem Symbol und eine Bezeichnung kann jedes Element die Informationen verfügen, die in den Spalten auf der rechten Seite des Symbols und der Bezeichnung angezeigt werden.  Dieses Steuerelement \(und daher die `CListCtrl`\-Klasse\) ist nur für \- Programmen verfügbar, die unter Windows 95\/98\- und Windows NT 3,51 und höher ausgeführt werden.  
  
 Es folgt eine kurze Übersicht über die `CListCtrl`\-Klasse.  Eine ausführliche Erläuterung, konzeptionelle finden Sie unter [Verwenden CListCtrl](../../mfc/using-clistctrl.md) und [Steuerelemente](../../mfc/controls-mfc.md).  
  
## Ansichten  
 Listenansicht\-Steuerelemente können ihren Inhalt auf vier verschiedene Arten anzeigen, aufgerufen "Ansichten."  
  
-   Symbolen  
  
     Jedes Element wird als Pixel des Symbols \(32 x 32 an\) mit einer Bezeichnung unter es.  Der Benutzer kann Elemente zu einem Speicherort im Listenansichtsfenster ziehen.  
  
-   Kleine Symbolen  
  
     Jedes Element wird als kleinen Pixel des Symbols \(16 x 16\) mit der Bezeichnung auf der rechten Seite dieses.  Der Benutzer kann Elemente zu einem Speicherort im Listenansichtsfenster ziehen.  
  
-   Listenansicht  
  
     Jedes Element wird als kleines Symbol mit einer Bezeichnung auf der rechten Seite dieses.  Elemente werden in Spalten angeordnet und können nicht zu einem Speicherort im Listenansichtsfenster gezogen werden.  
  
-   Berichtsansicht  
  
     Jedes Element wird in einer eigenen Zeile, wenn die zusätzliche Informationen in Spalten angeordnet ist, rechts.  Die Spalte ganz links enthält das kleine Symbol und die Bezeichnung, und folgende Spalten enthalten Unterelemente, wie durch die Anwendung angegeben.  Ein eingebettetes Header\-Steuerelement \(\- Klasse\) [Steuerelement\-MFC\-Klassen](../../mfc/reference/cheaderctrl-class.md) implementiert diese Spalten.  Weitere Informationen über das Header\-Steuerelement und Spalten in einer Berichtsansicht, finden Sie unter [Verwenden CListCtrl: Spalten auf das Steuerelement \(Berichtsansicht\) hinzufügen](../../mfc/adding-columns-to-the-control-report-view.md).  
  
 Siehe auch:  
  
-   Knowledge Base\-Artikel Q250614: HOWTO: Sortierungs\-Elemente in einem CListCtrl in der Berichtsansicht  
  
-   Knowledge Base\-Artikel Q200054: PRB: OnTimer\(\) wird wiederholt nicht für ein Listensteuerelement aufgerufen  
  
 Das Format der aktuellen Listenansicht des Steuerelements bestimmt die aktuelle Ansicht.  Weitere Informationen zu diesen sieht Formate und ihre Verwendung, [Verwenden CListCtrl: Ändern von Listensteuerelement\-Formaten](../../mfc/changing-list-control-styles.md).  
  
## Erweiterte Stile  
 Zusätzlich zu den Standardlistenformaten unterstützt Klasse `CListCtrl` einen umfangreichen Satz erweiterte Formate und stellt angereicherte Funktionalität bereit.  Einige Beispiele für diese Funktionalität:  
  
-   Verschiebung des Mauszeigerss\-Auswahl  
  
     Wenn Sie aktiviert sind, lässt die automatische Auswahl eines Elements, wenn der Cursor über dem Element während eines bestimmten Zeitraums bleibt.  
  
-   Virtuelle Listenansichten  
  
     Wenn Sie aktiviert werden, ermöglicht es dem Steuerelement, um bis zu `DWORD`\-Elemente zu unterstützen.  Dies ist möglich, indem Sie den Aufwand für die Verwaltung von Elementdaten auf der Anwendung platziert.  Neben der die Auswahl von Elementen und den Fokuseninformationen müssen alle Elementinformationen von der Anwendung verwaltet werden.  Weitere Informationen finden Sie unter [Verwenden CListCtrl: Virtuelle Listensteuerelemente](../../mfc/virtual-list-controls.md).  
  
-   Aktivierung mit ein und zwei Klicken  
  
     Wenn Sie aktiviert sind, lässt das Hottracking \(automatische Hervorhebung des Elementtexts\) und die Aktivierung mit ein oder zwei Klicken des markierten Elements.  
  
-   Drag & Drop\-Spaltenreihenfolge  
  
     Wenn Sie aktiviert sind, lässt das Drag & Drop\-Neuanordnen von Spalten in einem ListView\-Steuerelement.  Nur verfügbar in der Berichtsansicht.  
  
 Informationen zur Verwendung dieser neuen erweiterten Stile, finden Sie unter [Verwenden CListCtrl: Ändern von Listensteuerelement\-Formaten](../../mfc/changing-list-control-styles.md).  
  
## Elemente und Unterelemente  
 Jedes Element in einem ListView\-Steuerelement besteht aus einem Symbol \(von einer Bildliste\), eine Bezeichnung, einem aktuellen Zustand und einem anwendungsdefinierten Wert \(bezeichnet als "Elementdaten"\).  Eine oder mehrere Unterelemente können mit jedem Element auch zugeordnet werden.  Ein "Unterelement" ist eine Zeichenfolge, die, in der Berichtsansicht, in einer Spalte auf der rechten Seite des Symbols und der Bezeichnung eines Elements angezeigt werden kann.  Alle Elemente in einem ListView\-Steuerelement müssen die gleiche Anzahl von Unterelementen haben.  
  
 \- Klasse **CListCtrl**  stellt mehrere Funktionen zum Einfügen, Löschen, Durchsuchen und Ändern dieser Elemente bereit.  Weitere Informationen finden Sie unter [CListCtrl::GetItem](../Topic/CListCtrl::GetItem.md), [CListCtrl::InsertItem](../Topic/CListCtrl::InsertItem.md) und [CListCtrl::FindItem](../Topic/CListCtrl::FindItem.md), [Verwenden CListCtrl: Hinzufügen von Elementen zum Steuerelement](../../mfc/adding-items-to-the-control.md) und [Verwenden CListCtrl: wechseln, Anordnen, Sortieren und Suchen in Listen\-Steuerelemente](../../mfc/scrolling-arranging-sorting-and-finding-in-list-controls.md).  
  
 Standardmäßig ist das ListView\-Steuerelement zum Speichern von Symbol\- und Textattributen eines Elements zuständig.  jedoch zusätzlich zu diesen Elementtypen, unterstützt die Klasse `CListCtrl` "Rückrufelemente." Ein "Rückrufelement" ist ein Listenansichtelement, für das die Anwendung \- anstelle des Steuerelement Speicher für Text, das Symbol oder beide.  Eine Rückrufmaske wird verwendet, um anzugeben, die Elementattribute \(Text und\/oder Symbol\) durch die Anwendung angegeben werden.  Wenn eine Anwendung Rückrufelemente verwendet, muss es in der Lage sein, die Text\- und\/oder Symbolattribute bei Bedarf an.  Rückrufelemente sind hilfreich, wenn die Anwendung bereits einige dieser Informationen aufrechterhält.  Weitere Informationen finden Sie unter [Verwenden CListCtrl: Rückruf\-Elemente und die Rückruf\-Maske](../../mfc/callback-items-and-the-callback-mask.md).  
  
## Bildlisten  
 Die Symbole, die Headerelementimages und anwendungsdefinierte Zustände für Listenansichtelemente werden in mehreren Grafiklisten \(implementiert durch Klasse [CImageList](../../mfc/reference/cimagelist-class.md)\) enthalten, die Sie dem ListView\-Steuerelement erstellen und zuweisen.  Jedes Listenansicht\-Steuerelement kann bis zu vier verschiedene Typen Bildlisten haben:  
  
-   Großes Symbol  
  
     Wird in der Symbolen für Symbole an.  
  
-   Kleines Symbol  
  
     Wird im kleinen Symbol, in der Liste und in den Berichtsansichten für kleinere Versionen der Symbole verwendet in der Symbolen angezeigt.  
  
-   Anwendungsdefinierter Zustand  
  
     Enthält die Zustandsbilder, die neben dem Symbol eines Elements werden angezeigt, um einen anwendungsdefinierten Zustand anzugeben.  
  
-   Headerelement  
  
     Wird in der Berichtsansicht für kleine Bilder, die in jedem Header\-Steuerelement\-Element angezeigt werden.  
  
 Standardmäßig zerstört ein ListView\-Steuerelement die Bildlisten, die zugewiesen werden, wenn es zerstört wird, kann jedoch der Entwickler dieses Verhalten, indem jede Bildliste, wenn er nicht mehr verwendet wird, wie durch die Anwendung bestimmt anpassen zerstört.  Weitere Informationen finden Sie unter [Verwenden CListCtrl: Listenelemente und Bildlisten](../../mfc/list-items-and-image-lists.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CListCtrl`  
  
## Anforderungen  
 **Header:**  afxcmn.h  
  
## Siehe auch  
 [MFC Sampling ROWLIST](../../top/visual-cpp-samples.md)   
 [CWnd\-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CImageList Class](../../mfc/reference/cimagelist-class.md)
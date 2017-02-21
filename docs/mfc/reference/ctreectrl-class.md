---
title: "CTreeCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CTreeCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTreeCtrl class"
  - "directory lists"
  - "file lists [C++]"
  - "tree view controls"
ms.assetid: 96e20031-6161-4143-8c12-8d1816c66d90
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CTreeCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt die Funktionalität des allgemeinen Strukturansicht\-Steuerelements Windows bereit.  
  
## Syntax  
  
```  
class CTreeCtrl : public CWnd  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CTreeCtrl::CTreeCtrl](../Topic/CTreeCtrl::CTreeCtrl.md)|Erstellt ein `CTreeCtrl`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CTreeCtrl::Create](../Topic/CTreeCtrl::Create.md)|Erstellt eine Strukturansicht und fügt es zu einem `CTreeCtrl`\-Objekt.|  
|[CTreeCtrl::CreateDragImage](../Topic/CTreeCtrl::CreateDragImage.md)|Erstellt eine ziehende Bitmap für das angegebene Strukturansichtelement.|  
|[CTreeCtrl::CreateEx](../Topic/CTreeCtrl::CreateEx.md)|Erstellt eine Strukturansicht mit den angegebenen Windows\-erweitertenFormaten und fügt es zu einem `CTreeCtrl`\-Objekt.|  
|[CTreeCtrl::DeleteAllItems](../Topic/CTreeCtrl::DeleteAllItems.md)|Löscht alle Elemente in einem Strukturansicht\-Steuerelement.|  
|[CTreeCtrl::DeleteItem](../Topic/CTreeCtrl::DeleteItem.md)|Löscht ein neues Element in einem Strukturansicht\-Steuerelement.|  
|[CTreeCtrl::EditLabel](../Topic/CTreeCtrl::EditLabel.md)|Bearbeitet ein angegebenes direkt Strukturansichtelement.|  
|[CTreeCtrl::EndEditLabelNow](../Topic/CTreeCtrl::EndEditLabelNow.md)|Bricht den Bearbeitungsvorgang für die Bezeichnung eines Strukturansichtelements im aktuellen Strukturansicht ab.|  
|[CTreeCtrl::EnsureVisible](../Topic/CTreeCtrl::EnsureVisible.md)|Stellt sicher, dass ein Strukturansichtelement in seinem Strukturansicht sichtbar ist.|  
|[CTreeCtrl::Expand](../Topic/CTreeCtrl::Expand.md)|Erweitert oder reduziert, die untergeordneten Elemente des angegebenen Strukturansichtelements.|  
|[CTreeCtrl::GetBkColor](../Topic/CTreeCtrl::GetBkColor.md)|Ruft die aktuelle Hintergrundfarbe des Steuerelements ab.|  
|[CTreeCtrl::GetCheck](../Topic/CTreeCtrl::GetCheck.md)|Ruft den Aktivierungszustand eines Strukturansicht\-Steuerelement\-Elements ab.|  
|[CTreeCtrl::GetChildItem](../Topic/CTreeCtrl::GetChildItem.md)|Ruft das untergeordnete Element eines angegebenen Strukturansichtelements ab.|  
|[CTreeCtrl::GetCount](../Topic/CTreeCtrl::GetCount.md)|Ruft die Anzahl der Strukturelementen ab, die einem Strukturansicht\-Steuerelement zugeordnet werden.|  
|[CTreeCtrl::GetDropHilightItem](../Topic/CTreeCtrl::GetDropHilightItem.md)|Ruft das Ziel eines Drag & Drop\-Vorgangs ab.|  
|[CTreeCtrl::GetEditControl](../Topic/CTreeCtrl::GetEditControl.md)|Ruft das Handle des Bearbeitungssteuerelements ab, das verwendet wird, um das angegebene Strukturansichtelement zu bearbeiten.|  
|[CTreeCtrl::GetExtendedStyle](../Topic/CTreeCtrl::GetExtendedStyle.md)|Ruft die erweiterten Stile ab, dass das aktuelle Strukturansicht verwendet.|  
|[CTreeCtrl::GetFirstVisibleItem](../Topic/CTreeCtrl::GetFirstVisibleItem.md)|Ruft das erste sichtbare Element des angegebenen Strukturansichtelements ab.|  
|[CTreeCtrl::GetImageList](../Topic/CTreeCtrl::GetImageList.md)|Ruft das Handle der Bildliste ab, die einem Strukturansicht\-Steuerelement zugeordnet ist.|  
|[CTreeCtrl::GetIndent](../Topic/CTreeCtrl::GetIndent.md)|Ruft den Offset \(in Pixel\) eines Strukturansichtelements von seinem übergeordneten Element ab.|  
|[CTreeCtrl::GetInsertMarkColor](../Topic/CTreeCtrl::GetInsertMarkColor.md)|Ruft die Farbe ab, die verwendet wird, um die Einfügemarke für die Strukturansicht zu zeichnen.|  
|[CTreeCtrl::GetItem](../Topic/CTreeCtrl::GetItem.md)|Ruft die Attribute eines angegebenen Strukturansichtelements ab.|  
|[CTreeCtrl::GetItemData](../Topic/CTreeCtrl::GetItemData.md)|Gibt den Anwendungsbereich 32\-Bit\-Wert zurück, der einem Element zugeordnet ist.|  
|[CTreeCtrl::GetItemExpandedImageIndex](../Topic/CTreeCtrl::GetItemExpandedImageIndex.md)|Ruft den Index des Bilds ab, die angezeigt wird, wenn das angegebene Element des aktuellen Strukturansicht\-Steuerelements im erweiterten Zustand befindet.|  
|[CTreeCtrl::GetItemHeight](../Topic/CTreeCtrl::GetItemHeight.md)|Ruft die aktuelle Höhe der Strukturansichtelemente ab.|  
|[CTreeCtrl::GetItemImage](../Topic/CTreeCtrl::GetItemImage.md)|Ruft die Bilder ab, die einem Element zugeordnet werden.|  
|[CTreeCtrl::GetItemPartRect](../Topic/CTreeCtrl::GetItemPartRect.md)|Ruft das umschließende Rechteck für einen angegebenen Teil eines angegebenen Elements im aktuellen Strukturansicht ab.|  
|[CTreeCtrl::GetItemRect](../Topic/CTreeCtrl::GetItemRect.md)|Ruft das umgebende Rechteck eines Strukturansichtelements ab.|  
|[CTreeCtrl::GetItemState](../Topic/CTreeCtrl::GetItemState.md)|Gibt den Zustand eines Elements zurück.|  
|[CTreeCtrl::GetItemStateEx](../Topic/CTreeCtrl::GetItemStateEx.md)|Ruft den erweiterten Zustand des angegebenen Elements im aktuellen Strukturansicht ab.|  
|[CTreeCtrl::GetItemText](../Topic/CTreeCtrl::GetItemText.md)|Gibt den Text des Elements zurück.|  
|[CTreeCtrl::GetLastVisibleItem](../Topic/CTreeCtrl::GetLastVisibleItem.md)|Ruft das letzte erweiterte Element im aktuellen Strukturansicht ab.|  
|[CTreeCtrl::GetLineColor](../Topic/CTreeCtrl::GetLineColor.md)|Ruft die Farbe der aktuellen Zeile für das Strukturansicht\-Steuerelement ab.|  
|[CTreeCtrl::GetNextItem](../Topic/CTreeCtrl::GetNextItem.md)|Ruft das folgende Strukturansichtelement ab, das eine angegebene Beziehung entspricht.|  
|[CTreeCtrl::GetNextSiblingItem](../Topic/CTreeCtrl::GetNextSiblingItem.md)|Ruft das nächste gleichgeordnete Element des angegebenen Strukturansichtelements ab.|  
|[CTreeCtrl::GetNextVisibleItem](../Topic/CTreeCtrl::GetNextVisibleItem.md)|Ruft die nächste sichtbare Element des angegebenen Strukturansichtelements ab.|  
|[CTreeCtrl::GetParentItem](../Topic/CTreeCtrl::GetParentItem.md)|Ruft das übergeordnete Element des angegebenen Strukturansichtelements ab.|  
|[CTreeCtrl::GetPrevSiblingItem](../Topic/CTreeCtrl::GetPrevSiblingItem.md)|Ruft das vorhergehende gleichgeordnete Element des angegebenen Strukturansichtelements ab.|  
|[CTreeCtrl::GetPrevVisibleItem](../Topic/CTreeCtrl::GetPrevVisibleItem.md)|Ruft das vorherige sichtbare Element des angegebenen Strukturansichtelements ab.|  
|[CTreeCtrl::GetRootItem](../Topic/CTreeCtrl::GetRootItem.md)|Ruft den Stamm des angegebenen Strukturansichtelements ab.|  
|[CTreeCtrl::GetScrollTime](../Topic/CTreeCtrl::GetScrollTime.md)|Ruft die maximale Bildlaufzeit für die Strukturansicht ab.|  
|[CTreeCtrl::GetSelectedCount](../Topic/CTreeCtrl::GetSelectedCount.md)|Ruft die Anzahl der ausgewählten Elemente im aktuellen Strukturansicht ab.|  
|[CTreeCtrl::GetSelectedItem](../Topic/CTreeCtrl::GetSelectedItem.md)|Ruft das derzeit ausgewählte Strukturansichtelement ab.|  
|[CTreeCtrl::GetTextColor](../Topic/CTreeCtrl::GetTextColor.md)|Ruft die aktuelle Textfarbe des Steuerelements ab.|  
|[CTreeCtrl::GetToolTips](../Topic/CTreeCtrl::GetToolTips.md)|Ruft das Handle für den untergeordneten QuickInfosteuerelement ab, das durch eine Strukturansicht verwendet wird.|  
|[CTreeCtrl::GetVisibleCount](../Topic/CTreeCtrl::GetVisibleCount.md)|Ruft die Anzahl der sichtbaren Strukturelementen ab, die einem Strukturansicht\-Steuerelement zugeordnet werden.|  
|[CTreeCtrl::HitTest](../Topic/CTreeCtrl::HitTest.md)|Gibt die aktuelle Position des Cursors zurück, der dem `CTreeCtrl`\-Objekt verknüpft ist.|  
|[CTreeCtrl::InsertItem](../Topic/CTreeCtrl::InsertItem.md)|Fügt ein neues Element in einem Strukturansicht\-Steuerelement ein.|  
|[CTreeCtrl::ItemHasChildren](../Topic/CTreeCtrl::ItemHasChildren.md)|Gibt Wert ungleich 0 zurück, wenn das angegebene Element untergeordnete Elemente verfügt.|  
|[CTreeCtrl::MapAccIdToItem](../Topic/CTreeCtrl::MapAccIdToItem.md)|Ordnet den angegebenen Barrierefreiheitsbezeichner dem Handle für ein Strukturansichtelement im aktuellen Strukturansicht zu.|  
|[CTreeCtrl::MapItemToAccID](../Topic/CTreeCtrl::MapItemToAccID.md)|Ordnet das angegebene Handle für ein Strukturansichtelement im aktuellen Strukturansicht zu einem Barrierefreiheitsbezeichner zu.|  
|[CTreeCtrl::Select](../Topic/CTreeCtrl::Select.md)|Wählt aus, führt in Bildlauf durch oder zeichnet ein angegebenes Strukturansichtelement neu.|  
|[CTreeCtrl::SelectDropTarget](../Topic/CTreeCtrl::SelectDropTarget.md)|Aktualisiert das Strukturelement als Ziel eines Drag & Drop\-Vorgangs neu.|  
|[CTreeCtrl::SelectItem](../Topic/CTreeCtrl::SelectItem.md)|Wählt ein angegebenes Strukturansichtelement aus.|  
|[CTreeCtrl::SelectSetFirstVisible](../Topic/CTreeCtrl::SelectSetFirstVisible.md)|Wählt ein angegebenes Strukturansichtelement als Erstes sichtbares Element aus.|  
|[CTreeCtrl::SetAutoscrollInfo](../Topic/CTreeCtrl::SetAutoscrollInfo.md)|Legt die Rate des automatischen Bildlaufs des aktuellen Strukturansicht\-Steuerelements fest.|  
|[CTreeCtrl::SetBkColor](../Topic/CTreeCtrl::SetBkColor.md)|Legt die Hintergrundfarbe des Steuerelements fest.|  
|[CTreeCtrl::SetCheck](../Topic/CTreeCtrl::SetCheck.md)|Legt den Aktivierungszustand eines Strukturansicht\-Steuerelement\-Elements fest.|  
|[CTreeCtrl::SetExtendedStyle](../Topic/CTreeCtrl::SetExtendedStyle.md)|Legt die erweiterten Stile für das aktuelle Strukturansicht\-Steuerelement fest.|  
|[CTreeCtrl::SetImageList](../Topic/CTreeCtrl::SetImageList.md)|Legt das Handle der Bildliste fest, die einem Strukturansicht\-Steuerelement zugeordnet ist.|  
|[CTreeCtrl::SetIndent](../Topic/CTreeCtrl::SetIndent.md)|Legt den Offset \(in Pixel\) eines Strukturansichtelements von seinem übergeordneten Element fest.|  
|[CTreeCtrl::SetInsertMark](../Topic/CTreeCtrl::SetInsertMark.md)|Legt die Einfügemarke in einem Strukturansicht\-Steuerelement fest.|  
|[CTreeCtrl::SetInsertMarkColor](../Topic/CTreeCtrl::SetInsertMarkColor.md)|Legt die Farbe fest, die verwendet wird, um die Einfügemarke für die Strukturansicht zu zeichnen.|  
|[CTreeCtrl::SetItem](../Topic/CTreeCtrl::SetItem.md)|Legt die Attribute eines angegebenen Strukturansichtelements fest.|  
|[CTreeCtrl::SetItemData](../Topic/CTreeCtrl::SetItemData.md)|Legt den Anwendungsbereich 32\-Bit\-Wert fest, der einem Element zugeordnet ist.|  
|[CTreeCtrl::SetItemExpandedImageIndex](../Topic/CTreeCtrl::SetItemExpandedImageIndex.md)|Legt den Index des Bilds fest, die angezeigt wird, wenn das angegebene Element des aktuellen Strukturansicht\-Steuerelements im erweiterten Zustand befindet.|  
|[CTreeCtrl::SetItemHeight](../Topic/CTreeCtrl::SetItemHeight.md)|Gibt die Höhe der Strukturansichtelemente fest.|  
|[CTreeCtrl::SetItemImage](../Topic/CTreeCtrl::SetItemImage.md)|Ordnet Bilder mit einem Element zu.|  
|[CTreeCtrl::SetItemState](../Topic/CTreeCtrl::SetItemState.md)|Legt den Zustand eines Elements fest.|  
|[CTreeCtrl::SetItemStateEx](../Topic/CTreeCtrl::SetItemStateEx.md)|Legt den erweiterten Zustand des angegebenen Elements im aktuellen Strukturansicht\-Steuerelement fest.|  
|[CTreeCtrl::SetItemText](../Topic/CTreeCtrl::SetItemText.md)|Legt den Text eines Elements festgelegt.|  
|[CTreeCtrl::SetLineColor](../Topic/CTreeCtrl::SetLineColor.md)|Legt die Farbe der aktuellen Zeile für das Strukturansicht\-Steuerelement fest.|  
|[CTreeCtrl::SetScrollTime](../Topic/CTreeCtrl::SetScrollTime.md)|Legt die maximale Bildlaufzeit für das Strukturansicht\-Steuerelement fest.|  
|[CTreeCtrl::SetTextColor](../Topic/CTreeCtrl::SetTextColor.md)|Legt die Textfarbe des Steuerelements fest.|  
|[CTreeCtrl::SetToolTips](../Topic/CTreeCtrl::SetToolTips.md)|Legt untergeordnetes QuickInfosteuerelement eines Strukturansicht\-Steuerelements fest.|  
|[CTreeCtrl::ShowInfoTip](../Topic/CTreeCtrl::ShowInfoTip.md)|Zeigt den Infotipp für das angegebene Element im aktuellen Strukturansicht an.|  
|[CTreeCtrl::SortChildren](../Topic/CTreeCtrl::SortChildren.md)|Sortiert die untergeordneten Elemente eines angegebenen übergeordneten Elements.|  
|[CTreeCtrl::SortChildrenCB](../Topic/CTreeCtrl::SortChildrenCB.md)|Sortiert die untergeordneten Elemente eines angegebenen übergeordneten Elements mit einer anwendungsdefinierten fügen.|  
  
## Hinweise  
 Ein "Strukturansicht" ist ein Fenster, das eine hierarchische Liste von Elementen, wie den Überschriften in einem Dokument, die Einträge in einem Index oder die Dateien und Verzeichnisse auf einem Datenträger anzeigt.  Jedes Element besteht aus einer Bezeichnung und einem optionalen Bitmapbild, und jedes Element kann eine Liste der Unterelemente verfügen, die zugeordnet.  Wenn er auf ein Element klickt, kann der Benutzer die zugeordnete Liste von Unterelementen erweitern und reduzieren.  
  
 Dieses Steuerelement \(und daher die `CTreeCtrl`\-Klasse\) ist nur für \- Programmen verfügbar, die unter Windows 98 und Windows NT 4 und höher ausgeführt werden.  
  
 Weitere Informationen zur Verwendung von `CTreeCtrl`, finden Sie unter:  
  
-   [Steuerelemente](../../mfc/controls-mfc.md)  
  
-   [Verwenden CTreeCtrl](../../mfc/using-ctreectrl.md)  
  
-   [Strukturansicht\-Steuerelement\-Verweis](http://msdn.microsoft.com/library/windows/desktop/bb759988) in [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
-   Knowledge Base\-Artikel Q222905: HOWTO: Zeigen Sie ein Kontextmenü für CTreeCtrl an  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CTreeCtrl`  
  
## Anforderungen  
 **Header:**  afxcmn.h  
  
## Siehe auch  
 [MFC Sampling CMNCTRL1](../../top/visual-cpp-samples.md)   
 [CWnd\-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CImageList Class](../../mfc/reference/cimagelist-class.md)
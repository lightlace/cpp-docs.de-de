---
title: "CMFCRibbonGallery Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCRibbonGallery"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonGallery class"
ms.assetid: 9734c9c9-981c-4b3f-8c59-264fd41811b4
caps.latest.revision: 28
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 30
---
# CMFCRibbonGallery Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Werkzeug\-Office 2007\-Format\-Menübandkataloge.  
  
## Syntax  
  
```  
class CMFCRibbonGallery : public CMFCRibbonButton  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCRibbonGallery::CMFCRibbonGallery](../Topic/CMFCRibbonGallery::CMFCRibbonGallery.md)|erstellt und initialisiert ein `CMFCRibbonGallery`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCRibbonGallery::AddGroup](../Topic/CMFCRibbonGallery::AddGroup.md)|Fügt eine neue Gruppe dem Katalog hinzu.|  
|[CMFCRibbonGallery::AddSubItem](../Topic/CMFCRibbonGallery::AddSubItem.md)|Fügt ein neues Menüelement im Dropdownmenü hinzu.|  
|[CMFCRibbonGallery::Clear](../Topic/CMFCRibbonGallery::Clear.md)|Löscht den Inhalt aus dem Katalog.|  
|[CMFCRibbonGallery::EnableMenuResize](../Topic/CMFCRibbonGallery::EnableMenuResize.md)|Aktiviert oder deaktiviert die Größenanpassung des Menübereichs.|  
|[CMFCRibbonGallery::EnableMenuSideBar](../Topic/CMFCRibbonGallery::EnableMenuSideBar.md)|Aktiviert oder deaktiviert die Randleiste auf der linken Seite des Popupmenüs.|  
|[CMFCRibbonGallery::GetCompactSize](../Topic/CMFCRibbonGallery::GetCompactSize.md)|\(Überschreibungen [CMFCRibbonButton::GetCompactSize](../Topic/CMFCRibbonButton::GetCompactSize.md).\)|  
|[CMFCRibbonGallery::GetDroppedDown](../Topic/CMFCRibbonGallery::GetDroppedDown.md)|\(Überschreibungen [CMFCRibbonBaseElement::GetDroppedDown](../Topic/CMFCRibbonBaseElement::GetDroppedDown.md).\)|  
|[CMFCRibbonGallery::GetGroupName](../Topic/CMFCRibbonGallery::GetGroupName.md)|Gibt den Namen der Gruppe zurück, die am angegebenen Index befinden.|  
|[CMFCRibbonGallery::GetGroupOffset](../Topic/CMFCRibbonGallery::GetGroupOffset.md)||  
|[CMFCRibbonGallery::GetIconsInRow](../Topic/CMFCRibbonGallery::GetIconsInRow.md)|Gibt die Anzahl der Elemente in einer Zeile des Menübandkatalogs zurück.|  
|[CMFCRibbonGallery::GetItemToolTip](../Topic/CMFCRibbonGallery::GetItemToolTip.md)|Gibt den QuickInfo\-Text zurück, der einem Element im Katalog zugeordnet ist.|  
|[CMFCRibbonGallery::GetLastSelectedItem](../Topic/CMFCRibbonGallery::GetLastSelectedItem.md)|Gibt den Index des letzten Elements im Katalog zurück, den der Benutzer ausgewählt hat.|  
|[CMFCRibbonGallery::GetPaletteID](../Topic/CMFCRibbonGallery::GetPaletteID.md)|Gibt die Befehls\-ID des aktuellen Katalogs zurück.|  
|[CMFCRibbonGallery::GetRegularSize](../Topic/CMFCRibbonGallery::GetRegularSize.md)|\(Überschreibungen [CMFCRibbonButton::GetRegularSize](../Topic/CMFCRibbonButton::GetRegularSize.md).\)|  
|[CMFCRibbonGallery::GetSelectedItem](../Topic/CMFCRibbonGallery::GetSelectedItem.md)||  
|[CMFCRibbonGallery::HasMenu](../Topic/CMFCRibbonGallery::HasMenu.md)|\(Überschreibungen [CMFCRibbonButton::HasMenu](../Topic/CMFCRibbonButton::HasMenu.md).\)|  
|[CMFCRibbonGallery::IsButtonMode](../Topic/CMFCRibbonGallery::IsButtonMode.md)|Gibt an, ob der Katalog in einer Katalogschaltfläche enthalten ist.|  
|[CMFCRibbonGallery::IsMenuResizeEnabled](../Topic/CMFCRibbonGallery::IsMenuResizeEnabled.md)|Gibt an, ob Menügrößenanpassung aktiviert oder deaktiviert wird.|  
|[CMFCRibbonGallery::IsMenuResizeVertical](../Topic/CMFCRibbonGallery::IsMenuResizeVertical.md)||  
|[CMFCRibbonGallery::IsMenuSideBar](../Topic/CMFCRibbonGallery::IsMenuSideBar.md)|Gibt an, ob die Randleiste aktiviert oder deaktiviert wird.|  
|[CMFCRibbonGallery::OnAfterChangeRect](../Topic/CMFCRibbonGallery::OnAfterChangeRect.md)|\(Überschreibungen `CMFCRibbonButton::OnAfterChangeRect`.\)|  
|[CMFCRibbonGallery::OnDraw](../Topic/CMFCRibbonGallery::OnDraw.md)|\(Überschreibungen [CMFCRibbonButton::OnDraw](../Topic/CMFCRibbonButton::OnDraw.md).\)|  
|[CMFCRibbonGallery::OnEnable](../Topic/CMFCRibbonGallery::OnEnable.md)|\(Überschreibungen `CMFCRibbonBaseElement::OnEnable`.\)|  
|[CMFCRibbonGallery::OnRTLChanged](../Topic/CMFCRibbonGallery::OnRTLChanged.md)|\(Überschreibungen [CMFCRibbonBaseElement::OnRTLChanged](../Topic/CMFCRibbonBaseElement::OnRTLChanged.md).\)|  
|[CMFCRibbonGallery::RedrawIcons](../Topic/CMFCRibbonGallery::RedrawIcons.md)|Aktualisiert den Katalog neu.|  
|[CMFCRibbonGallery::RemoveItemToolTips](../Topic/CMFCRibbonGallery::RemoveItemToolTips.md)|Entfernt die QuickInfo von allen Elementen im Katalog.|  
|[CMFCRibbonGallery::SelectItem](../Topic/CMFCRibbonGallery::SelectItem.md)||  
|[CMFCRibbonGallery::SetACCData](../Topic/CMFCRibbonGallery::SetACCData.md)|\(Überschreibungen [CMFCRibbonButton::SetACCData](../Topic/CMFCRibbonButton::SetACCData.md).\)|  
|[CMFCRibbonGallery::SetButtonMode](../Topic/CMFCRibbonGallery::SetButtonMode.md)|Gibt an, ob der Menübandkatalog als Dropdownschaltfläche oder als Palette direkt auf dem Menüband angezeigt wird.|  
|[CMFCRibbonGallery::SetGroupName](../Topic/CMFCRibbonGallery::SetGroupName.md)|Legt den Namen einer Gruppe fest.|  
|[CMFCRibbonGallery::SetIconsInRow](../Topic/CMFCRibbonGallery::SetIconsInRow.md)|Definiert die Anzahl von Elementen pro Zeile im Katalog.|  
|[CMFCRibbonGallery::SetItemToolTip](../Topic/CMFCRibbonGallery::SetItemToolTip.md)|Legt den QuickInfo\-Text für ein Element im Katalog fest.|  
|[CMFCRibbonGallery::SetPalette](../Topic/CMFCRibbonGallery::SetPalette.md)|Fügt eine Palette einem Menübandkatalog bei.|  
|[CMFCRibbonGallery::SetPaletteID](../Topic/CMFCRibbonGallery::SetPaletteID.md)|Definiert die Befehls\-ID, die in der `WM_COMMAND` Meldung gesendet wird, wenn ein Katalogelement ausgewählt wurde.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCRibbonGallery::OnDrawPaletteIcon](../Topic/CMFCRibbonGallery::OnDrawPaletteIcon.md)|Aufgerufen vom Framework ausgelöst, wenn ein Katalogsymbol gezeichnet wird.|  
  
## Hinweise  
 Eine Katalogschaltfläche verhält sich wie eine reguläre Menüschaltfläche, außer dass sie zeigt einen Katalog an, wenn sie von einem Benutzer geöffnet wird.  Wenn Sie ein Element in einem Katalog auswählen, sendet das Framework die `WM_COMMAND` Meldung zusammen mit Befehls\-ID der Schaltfläche.  Wenn die Meldung bearbeiten, sollten Sie [CMFCRibbonGallery::GetLastSelectedItem](../Topic/CMFCRibbonGallery::GetLastSelectedItem.md) aufrufen, um zu bestimmen, welches Element aus dem Katalog ausgewählt wurde.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie verschiedene Methoden in der `CMFCRibbonGallery`\-Klasse verwendet, um ein `CMFCRibbonGallery`\-Objekt zu konfigurieren.  Das Beispiel veranschaulicht, wie die Anzahl von Elementen pro Zeile im Katalog angibt, Größenanpassung des Menübereichs aktiviert, die Randleiste auf der linken Seite des Popupmenüs aktiviert und den Menübandkatalog als Palette direkt auf der Menübandleiste anzeigt.  Dieser Codeausschnitt ist Teil [Clientbeispiel Videofunktionen](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_DrawClient#6](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_DrawClient#6)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md) [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md) [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md)  
  
## Anforderungen  
 **Header:** afxRibbonPaletteGallery.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonButton Class](../../mfc/reference/cmfcribbonbutton-class.md)   
 [CMFCRibbonGalleryMenuButton Class](../../mfc/reference/cmfcribbongallerymenubutton-class.md)
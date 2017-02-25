---
title: "CReBarCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CReBarCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CReBarCtrl class"
  - "rebar controls, control bar"
  - "rebar controls, CReBarCtrl class"
ms.assetid: 154570d7-e48c-425d-8c7e-c64542bcb4cc
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CReBarCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Kapselt die Funktionalität eines Infoleiste\-Steuerelements, das ein Container für ein untergeordnetes Fenster ist.  
  
## Syntax  
  
```  
class CReBarCtrl : public CWnd  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CReBarCtrl::CReBarCtrl](../Topic/CReBarCtrl::CReBarCtrl.md)|Erstellt ein `CReBarCtrl`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CReBarCtrl::BeginDrag](../Topic/CReBarCtrl::BeginDrag.md)|Setzt das Grundleistensteuerelement in Drag & Drop\-Modus.|  
|[CReBarCtrl::Create](../Topic/CReBarCtrl::Create.md)|Erstellt das Grundleistensteuerelement und fügt es dem `CReBarCtrl`\-Objekt.|  
|[CReBarCtrl::CreateEx](../Topic/CReBarCtrl::CreateEx.md)|Erstellt ein Grundleisten\-Steuerelement mit den angegebenen Windows\-erweitertenFormaten und fügt es zu einem `CReBarCtrl`\-Objekt.|  
|[CReBarCtrl::DeleteBand](../Topic/CReBarCtrl::DeleteBand.md)|Löscht ein Band von einem Infoleistensteuerelement.|  
|[CReBarCtrl::DragMove](../Topic/CReBarCtrl::DragMove.md)|Aktualisiert die Ziehposition im Grundleistensteuerelement nach einem Aufruf von `BeginDrag`.|  
|[CReBarCtrl::EndDrag](../Topic/CReBarCtrl::EndDrag.md)|Beendet den Drag & Drop\-Vorgang des Infoleiste\-Steuerelements.|  
|[CReBarCtrl::GetBandBorders](../Topic/CReBarCtrl::GetBandBorders.md)|Ruft die Kontext eines Bands ab.|  
|[CReBarCtrl::GetBandCount](../Topic/CReBarCtrl::GetBandCount.md)|Ruft die Anzahl von Bändern derzeit im Grundleistensteuerelement ab.|  
|[CReBarCtrl::GetBandInfo](../Topic/CReBarCtrl::GetBandInfo.md)|Ruft Informationen über ein bestimmtes Band in einem Grundleistensteuerelement ab.|  
|[CReBarCtrl::GetBandMargins](../Topic/CReBarCtrl::GetBandMargins.md)|Ruft die Ränder eines Bands ab.|  
|[CReBarCtrl::GetBarHeight](../Topic/CReBarCtrl::GetBarHeight.md)|Ruft die Höhe des Infoleiste\-Steuerelements ab.|  
|[CReBarCtrl::GetBarInfo](../Topic/CReBarCtrl::GetBarInfo.md)|Ruft Informationen zum Grundleistensteuerelement und die Bildliste ab, die sie verwendet.|  
|[CReBarCtrl::GetBkColor](../Topic/CReBarCtrl::GetBkColor.md)|Ruft die Standardhintergrundfarbe eines Infoleiste\-Steuerelements ab.|  
|[CReBarCtrl::GetColorScheme](../Topic/CReBarCtrl::GetColorScheme.md)|Ruft die [COLORSCHEME](http://msdn.microsoft.com/library/windows/desktop/bb775502)\-Struktur ab, die dem Grundleistensteuerelement zugeordnet ist.|  
|[CReBarCtrl::GetDropTarget](../Topic/CReBarCtrl::GetDropTarget.md)|Ruft `IDropTarget`\-Schnittstellenzeiger eines Infoleiste\-Steuerelements ab.|  
|[CReBarCtrl::GetExtendedStyle](../Topic/CReBarCtrl::GetExtendedStyle.md)|Ruft das erweiterte Format des aktuellen Infoleiste\-Steuerelements ab.|  
|[CReBarCtrl::GetImageList](../Topic/CReBarCtrl::GetImageList.md)|Ruft die Bildliste ab, die einem Grundleistensteuerelement zugeordnet ist.|  
|[CReBarCtrl::GetPalette](../Topic/CReBarCtrl::GetPalette.md)|Ruft die aktuelle Palette des Infoleiste\-Steuerelements ab.|  
|[CReBarCtrl::GetRect](../Topic/CReBarCtrl::GetRect.md)|Ruft das umschließende Rechteck für ein angegebenes Band in einem Grundleistensteuerelement ab.|  
|[CReBarCtrl::GetRowCount](../Topic/CReBarCtrl::GetRowCount.md)|Ruft die Anzahl der Bandzeilen in einem Grundleistensteuerelement ab.|  
|[CReBarCtrl::GetRowHeight](../Topic/CReBarCtrl::GetRowHeight.md)|Ruft die Höhe einer bestimmten Zeile in einem Grundleistensteuerelement ab.|  
|[CReBarCtrl::GetTextColor](../Topic/CReBarCtrl::GetTextColor.md)|Ruft Standardtextfarbe eines Infoleiste\-Steuerelements ab.|  
|[CReBarCtrl::GetToolTips](../Topic/CReBarCtrl::GetToolTips.md)|Ruft das Handle zu jedem ToolTip\-Steuerelement ab, das dem Grundleistensteuerelement zugeordnet ist.|  
|[CReBarCtrl::HitTest](../Topic/CReBarCtrl::HitTest.md)|Bestimmt, die Teil eines Infoleistenbandes an einem angegebenen Punkt auf dem Bildschirm angezeigt wird, wenn ein Infoleistenband an diesem Punkt vorhanden ist.|  
|[CReBarCtrl::IDToIndex](../Topic/CReBarCtrl::IDToIndex.md)|Konvertiert einen Bandbezeichner \(ID\) zu einem Bandindex in einem Infoleistensteuerelement.|  
|[CReBarCtrl::InsertBand](../Topic/CReBarCtrl::InsertBand.md)|Fügt ein neues Band in einem Grundleistensteuerelement ein.|  
|[CReBarCtrl::MaximizeBand](../Topic/CReBarCtrl::MaximizeBand.md)|Ändert ein Band in einem Grundleistensteuerelement in der größten Variante Größe.|  
|[CReBarCtrl::MinimizeBand](../Topic/CReBarCtrl::MinimizeBand.md)|Ändert ein Band in einem Grundleistensteuerelement auf den kleinsten Größe.|  
|[CReBarCtrl::MoveBand](../Topic/CReBarCtrl::MoveBand.md)|Verschiebt ein Band von einem Index auf andere.|  
|[CReBarCtrl::PushChevron](../Topic/CReBarCtrl::PushChevron.md)|Drückt programmgesteuert ein Chevron.|  
|[CReBarCtrl::RestoreBand](../Topic/CReBarCtrl::RestoreBand.md)|Ändert ein Band in einem Grundleistensteuerelement zu seiner Größe idealen Größe.|  
|[CReBarCtrl::SetBandInfo](../Topic/CReBarCtrl::SetBandInfo.md)|Legt Eigenschaften eines vorhandenen Bands in einem Grundleistensteuerelement fest.|  
|[CReBarCtrl::SetBandWidth](../Topic/CReBarCtrl::SetBandWidth.md)|Gibt die Breite des angegebenen angedockten Bands im aktuellen Grundleistensteuerelement fest.|  
|[CReBarCtrl::SetBarInfo](../Topic/CReBarCtrl::SetBarInfo.md)|Legt die Eigenschaften eines Infoleiste\-Steuerelements fest.|  
|[CReBarCtrl::SetBkColor](../Topic/CReBarCtrl::SetBkColor.md)|Legt die Standardhintergrundfarbe eines Infoleiste\-Steuerelements fest.|  
|[CReBarCtrl::SetColorScheme](../Topic/CReBarCtrl::SetColorScheme.md)|Legt das Farbschema für die Schaltflächen in einem Grundleistensteuerelement fest.|  
|[CReBarCtrl::SetExtendedStyle](../Topic/CReBarCtrl::SetExtendedStyle.md)|Legt die erweiterten Stile für das aktuelle Grundleistensteuerelement fest.|  
|[CReBarCtrl::SetImageList](../Topic/CReBarCtrl::SetImageList.md)|Legt die Bildliste eines Infoleiste\-Steuerelements fest.|  
|[CReBarCtrl::SetOwner](../Topic/CReBarCtrl::SetOwner.md)|Legt das Besitzerfenster eines Infoleiste\-Steuerelements fest.|  
|[CReBarCtrl::SetPalette](../Topic/CReBarCtrl::SetPalette.md)|Legt die aktuelle Palette des Infoleiste\-Steuerelements fest.|  
|[CReBarCtrl::SetTextColor](../Topic/CReBarCtrl::SetTextColor.md)|Legt Standardtextfarbe eines Infoleiste\-Steuerelements fest.|  
|[CReBarCtrl::SetToolTips](../Topic/CReBarCtrl::SetToolTips.md)|Ordnet ein QuickInfo\-Steuerelement mit dem Grundleistensteuerelement zu.|  
|[CReBarCtrl::SetWindowTheme](../Topic/CReBarCtrl::SetWindowTheme.md)|Legt den Stil des Infoleiste\-Steuerelements fest.|  
|[CReBarCtrl::ShowBand](../Topic/CReBarCtrl::ShowBand.md)|In oder aus einem angegebenen Band in einem Infoleistensteuerelement.|  
|[CReBarCtrl::SizeToRect](../Topic/CReBarCtrl::SizeToRect.md)|Passt ein Grundleisten\-Steuerelement zu einem angegebenen Rechteck.|  
  
## Hinweise  
 Die Anwendung, in der das Grundleistensteuerelement gespeichert wird, weist der zu Infoleistenband das untergeordnete Fenster, das durch das Grundleistensteuerelement enthalten ist.  Das untergeordnete Fenster ist normalerweise eine andere allgemeine Steuerelemente.  
  
 Infoleistensteuerelemente enthalten eine oder mehrere Bänder.  Jedes Band kann eine Ziehpunktleiste, der Bitmaps, der Beschriftung und untergeordneten Fensters enthalten.  Das Band kann nur ein für jedes dieser Elemente enthalten.  
  
 Das Grundleistensteuerelement kann das untergeordnete Fenster über einer angegebenen Hintergrundbitmap anzeigen.  Alle Infoleiste\-Steuerelement\-Bänder können, außer die Größe geändert werden, die das **RBBS\_FIXEDSIZE** Format verwenden.  Wenn Sie ein Infoleiste\-Steuerelement\-Band neu anordnen oder Größe ändern, verwaltet das Infoleiste die Größe und die Position des untergeordneten Fensters, das diesem Band zugewiesen wird.  Um die Reihenfolge von Bändern innerhalb des Steuerelements auf, Größe oder ändern und Ziehpunktleiste eines Bands ziehen.  
  
 Die folgende Abbildung zeigt ein Grundleisten\-Steuerelement an, das drei Bänder verfügt:  
  
-   Band 0 enthält ein gedrehtes, transparentes ToolBar\-Steuerelement.  
  
-   Band 1 enthält transparenten Standard und transparente Dropdown\-Schaltflächen.  
  
-   Band 2 enthält ein Kombinationsfeld und vier Standardschaltflächen.  
  
     ![Beispiel eines Grundleistenmenüs](../../mfc/reference/media/vc4scc1.png "vc4SCC1")  
  
## Grundleistensteuerelement  
 Infoleiste\-Steuerelement\-Unterstützung:  
  
-   Bildlisten.  
  
-   Meldungsbehandlung.  
  
-   Benutzerdefinierte Funktionen Videofunktionen.  
  
-   Eine Vielzahl von Steuerelementstile zusätzlich zu den Standardfensterstilen.  Eine Liste dieser Formate, finden Sie unter [Infoleiste\-Steuerelement\-Formate](http://msdn.microsoft.com/library/windows/desktop/bb774377) in [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Weitere Informationen finden Sie unter [Verwenden CReBarCtrl](../../mfc/using-crebarctrl.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CReBarCtrl`  
  
## Anforderungen  
 **Header:**  afxcmn.h  
  
## Siehe auch  
 [CWnd\-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)
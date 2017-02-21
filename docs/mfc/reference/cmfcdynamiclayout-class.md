---
title: "CMFCDynamicLayout-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: c2df2976-f049-47fc-9cf0-abe3e01948bc
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# CMFCDynamicLayout-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt an, wie Steuerelemente in einem Fenster verschoben und verkleinert oder vergrößert werden, wenn Benutzer die Größe des Fensters ändern.  
  
## Syntax  
  
```  
class CMFCDynamicLayout : public CObject  
```  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|`CMFCDynamicLayout::CMFCDynamicLayout`|Erstellt ein `CMFCDynamicLayout`\-Objekt.|  
|`CMFCDynamicLayout::~CMFCDynamicLayout`|Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CMFCDynamicLayout::AddItem](../Topic/CMFCDynamicLayout::AddItem.md)|Fügt der Liste von Fenstern, die vom dynamischen Layout\-Manager gesteuert werden, ein untergeordnetes Fenster hinzu, in der Regel ein Steuerelement.|  
|[CMFCDynamicLayout::Adjust](../Topic/CMFCDynamicLayout::Adjust.md)|Fügt der Liste von Fenstern, die vom dynamischen Layout\-Manager gesteuert werden, ein untergeordnetes Fenster hinzu, in der Regel ein Steuerelement.|  
|[CMFCDynamicLayout::Create](../Topic/CMFCDynamicLayout::Create.md)|Speichert und überprüft das Hostfenster.|  
|[CMFCDynamicLayout::GetHostWnd](../Topic/CMFCDynamicLayout::GetHostWnd.md)|Gibt einen Zeiger auf ein Hostfenster zurück.|  
|[CMFCDynamicLayout::GetMinSize](../Topic/CMFCDynamicLayout::GetMinSize.md)|Gibt die Größe des Fensters zurück, unterhalb derer das Layout nicht angepasst wird.|  
|[CMFCDynamicLayout::GetWindowRect](../Topic/CMFCDynamicLayout::GetWindowRect.md)|Ruft das Rechteck für den aktuellen Client\-Bereich des Fensters ab.|  
|[CMFCDynamicLayout::HasItem](../Topic/CMFCDynamicLayout::HasItem.md)|Überprüft, ob dem dynamischen Layout ein untergeordnetes Steuerelement hinzugefügt wurde.|  
|[CMFCDynamicLayout::IsEmpty](../Topic/CMFCDynamicLayout::IsEmpty.md)|Überprüft, ob einem dynamischen Layout keine untergeordneten Fenster hinzugefügt wurden.|  
|[CMFCDynamicLayout::LoadResource](../Topic/CMFCDynamicLayout::LoadResource.md)|Liest das dynamische Layout aus der AFX\_DIALOG\_LAYOUT\-Ressource und wendet das Layout dann auf das Hostfenster an.|  
|[CMFCDynamicLayout::MoveHorizontal](../Topic/CMFCDynamicLayout::MoveHorizontal.md), statisch|Ruft einen [MoveSettings](../Topic/CMFCDynamicLayout::MoveSettings%20Structure.md)\-Wert ab, der definiert, um wie viel ein untergeordnetes Steuerelement horizontal verschoben wird, wenn der Benutzer die Größe des Hostingfensters ändert.|  
|[CMFCDynamicLayout::MoveHorizontalAndVertical](../Topic/CMFCDynamicLayout::MoveHorizontalAndVertical.md), statisch|Ruft einen [MoveSettings](../Topic/CMFCDynamicLayout::MoveSettings%20Structure.md)\-Wert ab, der definiert, um wie viel ein untergeordnetes Steuerelement horizontal verschoben wird, wenn der Benutzer die Größe des Hostingfensters ändert.|  
|[CMFCDynamicLayout::MoveNone](../Topic/CMFCDynamicLayout::MoveNone.md), statisch|Ruft einen [MoveSettings](../Topic/CMFCDynamicLayout::MoveSettings%20Structure.md)\-Wert ab, der keine Bewegung \(vertikal oder horizontal\) für ein untergeordnetes Steuerelement darstellt.|  
|[CMFCDynamicLayout::MoveVertical](../Topic/CMFCDynamicLayout::MoveVertical.md), statisch|Ruft einen [MoveSettings](../Topic/CMFCDynamicLayout::MoveSettings%20Structure.md)\-Wert ab, der definiert, um wie viel ein untergeordnetes Steuerelement vertikal verschoben wird, wenn der Benutzer die Größe des Hostingfensters ändert.|  
|[CMFCDynamicLayout::SetMinSize](../Topic/CMFCDynamicLayout::SetMinSize.md)|Legt die Größe des Fensters fest, unterhalb derer das Layout nicht angepasst wird.|  
|[CMFCDynamicLayout::SizeHorizontal](../Topic/CMFCDynamicLayout::SizeHorizontal.md), statisch|Ruft einen [SizeSettings](../Topic/CMFCDynamicLayout::SizeSettings%20Structure.md)\-Wert ab, der definiert, um wie viel die Größe eines untergeordneten Steuerelements horizontal geändert wird, wenn der Benutzer die Größe des Hostingfensters ändert.|  
|[CMFCDynamicLayout::SizeHorizontalAndVertical](../Topic/CMFCDynamicLayout::SizeHorizontalAndVertical.md), statisch|Ruft einen [SizeSettings](../Topic/CMFCDynamicLayout::SizeSettings%20Structure.md)\-Wert ab, der definiert, um wie viel die Größe eines untergeordneten Steuerelements horizontal geändert wird, wenn der Benutzer die Größe des Hostingfensters ändert.|  
|[CMFCDynamicLayout::SizeNone](../Topic/CMFCDynamicLayout::SizeNone.md), statisch|Ruft einen [SizeSettings](../Topic/CMFCDynamicLayout::SizeSettings%20Structure.md) \-Wert ab, der keine Änderung der Größe für ein untergeordnetes Steuerelement darstellt.|  
|[CMFCDynamicLayout::SizeVertical](../Topic/CMFCDynamicLayout::SizeVertical.md), statisch|Ruft einen [SizeSettings](../Topic/CMFCDynamicLayout::SizeSettings%20Structure.md)\-Wert ab, der definiert, um wie viel die Größe eines untergeordneten Steuerelements vertikal geändert wird, wenn der Benutzer die Größe des Hostingfensters ändert.|  
  
## Geschachtelte Typen  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CMFCDynamicLayout::MoveSettings\-Struktur](../Topic/CMFCDynamicLayout::MoveSettings%20Structure.md)|Kapselt Daten für die Verschiebung für Steuerelemente in einem dynamischen Layout.|  
|[CMFCDynamicLayout::SizeSettings\-Struktur](../Topic/CMFCDynamicLayout::SizeSettings%20Structure.md)|Kapselt Daten für die Größenänderung für Steuerelemente in einem dynamischen Layout.|  
  
## Hinweise  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCDynamicLayout](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
## Anforderungen  
 **Header:** afxlayout.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)
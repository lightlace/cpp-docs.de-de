---
title: "CMFCRibbonColorButton-Klasse"
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
  - "CMFCRibbonColorButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonColorButton-Klasse"
ms.assetid: 6b4b4ee3-8cc0-41b4-a4eb-93e8847008e1
caps.latest.revision: 36
caps.handback.revision: "24"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCRibbonColorButton-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `CMFCRibbonColorButton`\-Klasse implementiert eine Farbenschaltfläche, die einer Menübandleiste hinzugefügt werden kann. Die Menüband\-Farbenschaltfläche zeigt ein Dropdownmenü an, das eine oder mehrere Farbpaletten enthält.  
  
## Syntax  
  
```  
class CMFCRibbonColorButton : public CMFCRibbonGallery  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CMFCRibbonColorButton::CMFCRibbonColorButton](../Topic/CMFCRibbonColorButton::CMFCRibbonColorButton.md)||  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CMFCRibbonColorButton::AddColorsGroup](../Topic/CMFCRibbonColorButton::AddColorsGroup.md)|Fügt dem normalen Farbbereich eine Gruppe Farben hinzu.|  
|[CMFCRibbonColorButton::EnableAutomaticButton](../Topic/CMFCRibbonColorButton::EnableAutomaticButton.md)|Gibt an, ob die Schaltfläche **Automatisch** aktiviert ist.|  
|[CMFCRibbonColorButton::EnableOtherButton](../Topic/CMFCRibbonColorButton::EnableOtherButton.md)|Aktiviert die Schaltfläche **Weitere**.|  
|[CMFCRibbonColorButton::GetAutomaticColor](../Topic/CMFCRibbonColorButton::GetAutomaticColor.md)||  
|[CMFCRibbonColorButton::GetColor](../Topic/CMFCRibbonColorButton::GetColor.md)|Gibt die aktuell ausgewählte Farbe zurück.|  
|[CMFCRibbonColorButton::GetColorBoxSize](../Topic/CMFCRibbonColorButton::GetColorBoxSize.md)|Gibt die Größe der Farbelemente zurück, die in der Farbleiste angezeigt werden.|  
|[CMFCRibbonColorButton::GetColumns](../Topic/CMFCRibbonColorButton::GetColumns.md)||  
|[CMFCRibbonColorButton::GetHighlightedColor](../Topic/CMFCRibbonColorButton::GetHighlightedColor.md)|Gibt die Farbe des aktuell in der Popup\-Farbpalette ausgewählten Elements zurück.|  
|[CMFCRibbonColorButton::RemoveAllColorGroups](../Topic/CMFCRibbonColorButton::RemoveAllColorGroups.md)|Entfernt alle Farbgruppen aus dem normalen Farbbereich.|  
|[CMFCRibbonColorButton::SetColor](../Topic/CMFCRibbonColorButton::SetColor.md)|Wählt eine Farbe aus dem normalen Farbbereich aus.|  
|[CMFCRibbonColorButton::SetColorBoxSize](../Topic/CMFCRibbonColorButton::SetColorBoxSize.md)|Legt die Größe aller Farbelemente fest, die in der Farbleiste angezeigt werden.|  
|[CMFCRibbonColorButton::SetColorName](../Topic/CMFCRibbonColorButton::SetColorName.md)||  
|[CMFCRibbonColorButton::SetColumns](../Topic/CMFCRibbonColorButton::SetColumns.md)||  
|[CMFCRibbonColorButton::SetDocumentColors](../Topic/CMFCRibbonColorButton::SetDocumentColors.md)|Gibt eine Liste mit RGB\-Werten für die Anzeige im Farbbereich des Dokuments an.|  
|[CMFCRibbonColorButton::SetPalette](../Topic/CMFCRibbonColorButton::SetPalette.md)||  
|[CMFCRibbonColorButton::UpdateColor](../Topic/CMFCRibbonColorButton::UpdateColor.md)||  
  
## Hinweise  
 Die Farbenschaltfläche im Menüband zeigt eine Farbleiste an, wenn ein Benutzer drauf drückt. Standardmäßig enthält diese Farbleiste eine Farbauswahlpalette, die als normaler Farbbereich bezeichnet wird. Optional kann die Farbleiste eine Schaltfläche **Automatisch**, die dem Benutzer die Auswahl einer Standardfarbe ermöglicht, und eine Schaltfläche **Weitere** anzeigen, die eine Popupfarbpalette anzeigt, die weitere Farben enthält.  
  
## Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung verschiedener Methoden in der `CMFCRibbonColorButton`\-Klasse. Im Beispiel wird gezeigt, wie ein `CMFCRibbonColorButton`\-Objekt konstruiert wird, das große Bild festgelegt wird, die Schaltfläche **Automatisch** aktiviert wird, die Schaltfläche **Weitere** aktiviert wird, die Spaltenanzahl festgelegt wird, die Größe aller Farbelemente festgelegt wird, die auf der Farbleiste angezeigt werden, dem normalen Farbbereich eine Gruppe Farben hinzugefügt wird, und eine Liste mit RGB\-Werten für die Anzeige im Farbbereich des Dokuments angegeben wird. Dieser Codeausschnitt ist Teil des [Draw Client\-Beispiels](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_DrawClient#3](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_DrawClient#3)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md)  
  
 [CMFCRibbonColorButton](../../mfc/reference/cmfcribboncolorbutton-class.md)  
  
## Anforderungen  
 **Header:** afxribboncolorbutton.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonGallery Class](../../mfc/reference/cmfcribbongallery-class.md)
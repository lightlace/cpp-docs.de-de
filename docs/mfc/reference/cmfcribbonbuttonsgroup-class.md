---
title: "CMFCRibbonButtonsGroup-Klasse"
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
  - "CMFCRibbonButtonsGroup"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonButtonsGroup-Klasse"
ms.assetid: b993d93e-fc1a-472f-a87f-1d7b7b499845
caps.latest.revision: 34
caps.handback.revision: "22"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCRibbonButtonsGroup-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `CMFCRibbonButtonsGroup`\-Klasse ermöglicht es Ihnen, einen Satz Menübandschaltflächen in eine Gruppe zu organisieren.  Alle Schaltflächen in der Gruppe sind direkt horizontal nebeneinander wieder und enthalten in einem Rahmen.  
  
## Syntax  
  
```  
class CMFCRibbonButtonsGroup : public CMFCRibbonBaseElement  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CMFCRibbonButtonsGroup::CMFCRibbonButtonsGroup](../Topic/CMFCRibbonButtonsGroup::CMFCRibbonButtonsGroup.md)|Erstellt ein `CMFCRibbonButtonsGroup`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CMFCRibbonButtonsGroup::AddButton](../Topic/CMFCRibbonButtonsGroup::AddButton.md)|Fügt eine Schaltfläche einer Gruppe hinzu.|  
|[CMFCRibbonButtonsGroup::AddButtons](../Topic/CMFCRibbonButtonsGroup::AddButtons.md)|Fügt eine Liste von Schaltflächen einer Gruppe hinzu.|  
|[CMFCRibbonButtonsGroup::GetButton](../Topic/CMFCRibbonButtonsGroup::GetButton.md)|Gibt einen Zeiger auf die Schaltfläche zurück, die an einem angegebenen Index befinden.|  
|[CMFCRibbonButtonsGroup::GetCount](../Topic/CMFCRibbonButtonsGroup::GetCount.md)|Gibt die Anzahl von Schaltflächen in der Gruppe zurück.|  
|[CMFCRibbonButtonsGroup::GetImageSize](../Topic/CMFCRibbonButtonsGroup::GetImageSize.md)|Gibt die Größe der normalen Bilder in der Menübandgruppe zurück \(Überschreibungen [CMFCRibbonBaseElement::GetImageSize](../Topic/CMFCRibbonBaseElement::GetImageSize.md).\)|  
|[CMFCRibbonButtonsGroup::GetRegularSize](../Topic/CMFCRibbonButtonsGroup::GetRegularSize.md)|Gibt die reguläre Größe des Menübandelements zurück \(Überschreibungen [CMFCRibbonBaseElement::GetRegularSize](../Topic/CMFCRibbonBaseElement::GetRegularSize.md).\)|  
|[CMFCRibbonButtonsGroup::HasImages](../Topic/CMFCRibbonButtonsGroup::HasImages.md)|Berichte, ob das Objekt `CMFCRibbonButtonsGroup` Symbolleistenimages enthält.|  
|[CMFCRibbonButtonsGroup::OnDrawImage](../Topic/CMFCRibbonButtonsGroup::OnDrawImage.md)|Zeichnet das entsprechende Bild für eine angegebene Schaltfläche, je nachdem, ob die Schaltfläche ist hervorgehoben, Normal oder deaktiviert.|  
|[CMFCRibbonButtonsGroup::RemoveAll](../Topic/CMFCRibbonButtonsGroup::RemoveAll.md)|Entfernt alle Schaltflächen vom `CMFCRibbonButtonsGroup`\-Objekt.|  
|[CMFCRibbonButtonsGroup::SetImages](../Topic/CMFCRibbonButtonsGroup::SetImages.md)|Weist der Gruppe Bilder zu.|  
|[CMFCRibbonButtonsGroup::SetParentCategory](../Topic/CMFCRibbonButtonsGroup::SetParentCategory.md)|Legt Elemente `CMFCRibbonCategory` des Objekts `CMFCRibbonButtonsGroup` und aller Schaltflächen in es fest \(Überschreibungen [CMFCRibbonBaseElement::SetParentCategory](../Topic/CMFCRibbonBaseElement::SetParentCategory.md).\)|  
  
## Hinweise  
 Die Gruppe wird von [CMFCBaseRibbonElement](../../mfc/reference/cmfcribbonbaseelement-class.md) berechnet und kann als einzelne Entität behandelt werden.  Sie können die Gruppe auf jeden Bereich oder Popupmenü positionieren.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie verschiedene Methoden in der Klasse `CMFCRibbonButtonsGroup` verwendet.  Im Beispiel wird gezeigt, wie ein `CMFCRibbonButtonsGroup`\-Objekt erstellt, der Gruppe von Menübandschaltflächen Bilder zuweist und eine Schaltfläche der Gruppe von Menübandschaltflächen hinzugefügt wird.  Dieser Codeausschnitt ist Teil [Clientbeispiel Videofunktionen](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_DrawClient#2](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_DrawClient#2)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButtonsGroup](../../mfc/reference/cmfcribbonbuttonsgroup-class.md)  
  
## Anforderungen  
 **Header:** afxribbonbuttonsgroup.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)
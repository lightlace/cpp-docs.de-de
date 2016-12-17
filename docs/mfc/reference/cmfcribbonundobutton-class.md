---
title: "CMFCRibbonUndoButton Class"
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
  - "CMFCRibbonUndoButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonUndoButton class"
ms.assetid: 5c42adf7-871d-4239-901e-47ae7fb816fc
caps.latest.revision: 35
caps.handback.revision: "23"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCRibbonUndoButton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `CMFCRibbonUndoButton`\-Klasse implementiert eine Dropdownlistenschaltfläche, die die neuesten Benutzerbefehle enthält.  Benutzer können eine oder mehrere der letzten Befehle aus der Dropdownliste auswählen entweder zu überprüfen oder sie rückgängig machen.  
  
## Syntax  
  
```  
class CMFCRibbonUndoButton : public CMFCRibbonGallery  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCRibbonUndoButton::CMFCRibbonUndoButton](../Topic/CMFCRibbonUndoButton::CMFCRibbonUndoButton.md)|Erstellt ein neues `CMFCRibbonUndoButton`\-Objekt unter Verwendung der Befehls\-ID, dass Sie angeben, der Beschriftung und Bildern aus der Bildliste des übergeordneten Objekts.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCRibbonUndoButton::AddUndoAction](../Topic/CMFCRibbonUndoButton::AddUndoAction.md)|Fügt eine neue Aktion der Liste der Aktionen hinzu.|  
|[CMFCRibbonUndoButton::CleanUpUndoList](../Topic/CMFCRibbonUndoButton::CleanUpUndoList.md)|Löscht die Aktionsliste, die die Dropdownliste ist.|  
|[CMFCRibbonUndoButton::GetActionNumber](../Topic/CMFCRibbonUndoButton::GetActionNumber.md)|Bestimmt die Anzahl der Elemente, die ein Benutzer in der Dropdownliste ausgewählt hat.|  
|[CMFCRibbonUndoButton::HasMenu](../Topic/CMFCRibbonUndoButton::HasMenu.md)|Gibt an, ob das Objekt ein Menü enthält.|  
  
## Hinweise  
 Die `CMFCRibbonUndoButton`\-Klasse verwendet einen Stapel, um die Dropdownliste anzuzeigen.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie ein Objekt der Klasse `CMFCRibbonUndoButton` erstellt und eine neue Aktion der Liste der Aktionen hinzu.  Dieser Codeausschnitt ist Teil [Menüband\-Gadgetbeispiel](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_RibbonGadgets#2](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_RibbonGadgets#2)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md)  
  
 [CMFCRibbonUndoButton](../../mfc/reference/cmfcribbonundobutton-class.md)  
  
## Anforderungen  
 **Header:** afxribbonundobutton.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonGallery Class](../../mfc/reference/cmfcribbongallery-class.md)   
 [CMFCRibbonButton Class](../../mfc/reference/cmfcribbonbutton-class.md)
---
title: "CMFCRibbonStatusBarPane Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCRibbonStatusBarPane"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonStatusBarPane class"
ms.assetid: 5d034c3c-ecca-4267-b88c-0f55a2884dd0
caps.latest.revision: 31
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 33
---
# CMFCRibbonStatusBarPane Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `CMFCRibbonStatusBarPane`\-Klasse implementiert ein Menübandelement, das Sie einer Menübandstatusleiste hinzufügen können.  
  
## Syntax  
  
```  
class CMFCRibbonStatusBarPane : public CMFCRibbonButton  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCRibbonStatusBarPane::CMFCRibbonStatusBarPane](../Topic/CMFCRibbonStatusBarPane::CMFCRibbonStatusBarPane.md)|erstellt und initialisiert ein `CMFCRibbonStatusBarPane`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCRibbonStatusBarPane::GetAlmostLargeText](../Topic/CMFCRibbonStatusBarPane::GetAlmostLargeText.md)|Gibt die Zeichenfolge zurück, die die längste Textzeichenfolge definiert, die im Bereich ohne Verkürzung angezeigt werden kann.|  
|[CMFCRibbonStatusBarPane::GetTextAlign](../Topic/CMFCRibbonStatusBarPane::GetTextAlign.md)|Gibt die aktuelle Einstellung der Textausrichtung zurück.|  
|[CMFCRibbonStatusBarPane::IsAnimation](../Topic/CMFCRibbonStatusBarPane::IsAnimation.md)|Bestimmt, ob die Animation ausgeführt wird.|  
|[CMFCRibbonStatusBarPane::IsExtended](../Topic/CMFCRibbonStatusBarPane::IsExtended.md)|Bestimmt, ob der Bereich im erweiterten Bereich der Menübandstatusleiste ist.|  
|[CMFCRibbonStatusBarPane::OnDrawBorder](../Topic/CMFCRibbonStatusBarPane::OnDrawBorder.md)|\(Überschreibungen [CMFCRibbonButton::OnDrawBorder](../Topic/CMFCRibbonButton::OnDrawBorder.md).\)|  
|[CMFCRibbonStatusBarPane::OnFillBackground](../Topic/CMFCRibbonStatusBarPane::OnFillBackground.md)|\(Überschreibungen [CMFCRibbonButton::OnFillBackground](../Topic/CMFCRibbonButton::OnFillBackground.md).\)|  
|[CMFCRibbonStatusBarPane::SetAlmostLargeText](../Topic/CMFCRibbonStatusBarPane::SetAlmostLargeText.md)|Definiert die längste Textzeichenfolge, die im Bereich ohne Verkürzung angezeigt werden kann.|  
|[CMFCRibbonStatusBarPane::SetAnimationList](../Topic/CMFCRibbonStatusBarPane::SetAnimationList.md)|Weist dem Bereich einer Bildliste zu, die für Animationen verwendet werden kann.|  
|[CMFCRibbonStatusBarPane::SetTextAlign](../Topic/CMFCRibbonStatusBarPane::SetTextAlign.md)|Legt die Textausrichtung fest.|  
|[CMFCRibbonStatusBarPane::StartAnimation](../Topic/CMFCRibbonStatusBarPane::StartAnimation.md)|Startet die Animation, die dem Bereich zugewiesen wird.|  
|[CMFCRibbonStatusBarPane::StopAnimation](../Topic/CMFCRibbonStatusBarPane::StopAnimation.md)|Beendet die Animation, die dem Bereich zugewiesen wird.  .|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCRibbonStatusBarPane::OnFinishAnimation](../Topic/CMFCRibbonStatusBarPane::OnFinishAnimation.md)|Aufgerufen vom Framework, wenn die Animation, die dem Bereich zugewiesen wird, beendet wird.|  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie die verschiedenen Methoden in der Klasse `CMFCRibbonStatusBarPane` verwendet.  Im Beispiel wird gezeigt, wie ein `CMFCRibbonStatusBarPane`\-Objekt, legen Sie die Textausrichtung der Bezeichnung des Statusleistenbereichs, definieren den längsten Text erstellt, der im Statusleistenbereich ohne Verkürzung angezeigt werden kann, um den Statusleistenbereich Bildliste, die für eine Animation verwendet und die Animation startet.  
  
 [!CODE [NVC_MFC_RibbonApp#2](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_RibbonApp#2)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonStatusBarPane](../../mfc/reference/cmfcribbonstatusbarpane-class.md)  
  
## Anforderungen  
 **Header:** afxribbonstatusbarpane.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonButton Class](../../mfc/reference/cmfcribbonbutton-class.md)   
 [CMFCRibbonStatusBar Class](../../mfc/reference/cmfcribbonstatusbar-class.md)
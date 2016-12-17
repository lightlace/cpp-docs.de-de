---
title: "CMFCRibbonProgressBar Class"
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
  - "CMFCRibbonProgressBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonProgressBar class"
ms.assetid: de3d9f2e-ed59-480e-aa7d-08a33ab36c67
caps.latest.revision: 26
caps.handback.revision: "14"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCRibbonProgressBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implementiert ein Steuerelement, das visuell den Status eines längeren Vorgangs angibt.  
  
## Syntax  
  
```  
class CMFCRibbonProgressBar : public CMFCRibbonBaseElement  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCRibbonProgressBar::CMFCRibbonProgressBar](../Topic/CMFCRibbonProgressBar::CMFCRibbonProgressBar.md)|erstellt und initialisiert ein `CMFCRibbonProgressBar`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCRibbonProgressBar::GetPos](../Topic/CMFCRibbonProgressBar::GetPos.md)|Gibt den aktuellen Status zurück.|  
|[CMFCRibbonProgressBar::GetRangeMax](../Topic/CMFCRibbonProgressBar::GetRangeMax.md)|Gibt den maximalen Wert des Strombereichs zurück.|  
|[CMFCRibbonProgressBar::GetRangeMin](../Topic/CMFCRibbonProgressBar::GetRangeMin.md)|Gibt den minimalen Wert des Strombereichs zurück.|  
|[CMFCRibbonProgressBar::GetRegularSize](../Topic/CMFCRibbonProgressBar::GetRegularSize.md)|Gibt die reguläre Größe des Menübandelements zurück.  \(Überschreibungen [CMFCRibbonBaseElement::GetRegularSize](../Topic/CMFCRibbonBaseElement::GetRegularSize.md).\)|  
|[CMFCRibbonProgressBar::IsInfiniteMode](../Topic/CMFCRibbonProgressBar::IsInfiniteMode.md)|Gibt an, ob die Statusanzeige im unendlichen Modus funktioniert.|  
|[CMFCRibbonProgressBar::OnDraw](../Topic/CMFCRibbonProgressBar::OnDraw.md)|Aufgerufen durch das Framework, um das Menübandelement zu zeichnen.  \(Überschreibungen [CMFCRibbonBaseElement::OnDraw](../Topic/CMFCRibbonBaseElement::OnDraw.md).\)|  
|[CMFCRibbonProgressBar::SetInfiniteMode](../Topic/CMFCRibbonProgressBar::SetInfiniteMode.md)|Legt die Statusanzeige fest, um im unendlichen Modus zu arbeiten.|  
|[CMFCRibbonProgressBar::SetPos](../Topic/CMFCRibbonProgressBar::SetPos.md)|Legt den aktuellen Status fest.|  
|[CMFCRibbonProgressBar::SetRange](../Topic/CMFCRibbonProgressBar::SetRange.md)|Legt die minimalen und maximalen Werte fest.|  
  
## Hinweise  
 `CMFCRibbonProgressBar` kann in zwei Modi ausgeführt werden: Normal und unbegrenzt.  Im regulären Modus wird die Statusanzeige von links nach rechts gefüllt und angehalten wird, wenn sie den Höchstwert erreicht.  Im unendlichen Modus wird die Statusanzeige wiederholt vom niedrigsten Wert auf den maximalen Wert.  Sie haben eine Modus, um anzugeben, dass ein Vorgang ausgeführt wird, aber die Abschlusszeit unbekannt ist.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie verschiedene Methoden in der Klasse `CMFCRibbonProgressBar` verwendet.  Im Beispiel wird gezeigt, wie die Statusanzeige festgelegt werden, um im unendlichen Modus arbeiten \(wobei die Abschlusszeit eines Vorgangs unbekannt ist\), legen Sie die minimalen und maximalen Werte für die Statusanzeige und legen Sie die aktuelle Position der Statusanzeige.  Dieser Codeausschnitt ist Teil [MS Office\-Demobeispiel 2007](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_MSOffice2007Demo#11](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_MSOffice2007Demo#11)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonProgressBar](../../mfc/reference/cmfcribbonprogressbar-class.md)  
  
## Anforderungen  
 **Header:** afxRibbonProgressBar.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonBaseElement Class](../../mfc/reference/cmfcribbonbaseelement-class.md)   
 [CMFCRibbonBar Class](../../mfc/reference/cmfcribbonbar-class.md)
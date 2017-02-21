---
title: "CMFCRibbonStatusBar Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCRibbonStatusBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonStatusBar class"
ms.assetid: 921eb57f-3b40-49fa-a38c-3f2fb6dc2893
caps.latest.revision: 37
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 39
---
# CMFCRibbonStatusBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `CMFCRibbonStatusBar`\-Klasse implementiert ein StatusBar\-Steuerelement, das Menübandelemente anzeigen kann.  
  
## Syntax  
  
```  
class CMFCRibbonStatusBar : public CMFCRibbonBar  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCRibbonStatusBar::AddDynamicElement](../Topic/CMFCRibbonStatusBar::AddDynamicElement.md)|Fügt ein dynamisches Element der Menübandstatusleiste hinzu.|  
|[CMFCRibbonStatusBar::AddElement](../Topic/CMFCRibbonStatusBar::AddElement.md)|Fügt ein neues Excel\-Add\-In\-Projekt der Menübandstatusleiste hinzu.|  
|[CMFCRibbonStatusBar::AddExtendedElement](../Topic/CMFCRibbonStatusBar::AddExtendedElement.md)|Fügt ein Menübandelement dem erweiterten Bereich der Menübandstatusleiste hinzu.|  
|[CMFCRibbonStatusBar::AddSeparator](../Topic/CMFCRibbonStatusBar::AddSeparator.md)|Fügt ein Trennzeichen der Menübandstatusleiste hinzu.|  
|[CMFCRibbonStatusBar::Create](../Topic/CMFCRibbonStatusBar::Create.md)|Erstellt eine Menübandstatusleiste.|  
|[CMFCRibbonStatusBar::CreateEx](../Topic/CMFCRibbonStatusBar::CreateEx.md)|Erstellt eine Menübandstatusleiste mit einem erweiterten Format.|  
|[CMFCRibbonStatusBar::FindByID](../Topic/CMFCRibbonStatusBar::FindByID.md)||  
|[CMFCRibbonStatusBar::FindElement](../Topic/CMFCRibbonStatusBar::FindElement.md)|Gibt einen Zeiger auf das Element zurück, das die angegebene ID besitzt Befehl|  
|[CMFCRibbonStatusBar::GetCount](../Topic/CMFCRibbonStatusBar::GetCount.md)|Gibt die Anzahl von Elementen zurück, die im Hauptbereich der Menübandstatusleiste sind.|  
|[CMFCRibbonStatusBar::GetElement](../Topic/CMFCRibbonStatusBar::GetElement.md)|Gibt einen Zeiger auf das Element zurück, das an einem angegebenen Index befindet.|  
|[CMFCRibbonStatusBar::GetExCount](../Topic/CMFCRibbonStatusBar::GetExCount.md)|Gibt die Anzahl von Elementen zurück, die im erweiterten Bereich der Menübandstatusleiste sind.|  
|[CMFCRibbonStatusBar::GetExElement](../Topic/CMFCRibbonStatusBar::GetExElement.md)|Gibt einen Zeiger auf das Element zurück, das an einem angegebenen Index im erweiterten Bereich der Menübandstatusleiste befindet.|  
|[CMFCRibbonStatusBar::GetExtendedArea](../Topic/CMFCRibbonStatusBar::GetExtendedArea.md)||  
|[CMFCRibbonStatusBar::GetSpace](../Topic/CMFCRibbonStatusBar::GetSpace.md)||  
|[CMFCRibbonStatusBar::IsBottomFrame](../Topic/CMFCRibbonStatusBar::IsBottomFrame.md)||  
|[CMFCRibbonStatusBar::IsExtendedElement](../Topic/CMFCRibbonStatusBar::IsExtendedElement.md)||  
|[CMFCRibbonStatusBar::IsInformationMode](../Topic/CMFCRibbonStatusBar::IsInformationMode.md)|Bestimmt, ob Informationsmodus für die Menübandstatusleiste aktiviert ist.|  
|[CMFCRibbonStatusBar::RecalcLayout](../Topic/CMFCRibbonStatusBar::RecalcLayout.md)|\(Überschreibungen [CMFCRibbonBar::RecalcLayout](../Topic/CMFCRibbonBar::RecalcLayout.md).\)|  
|[CMFCRibbonStatusBar::RemoveAll](../Topic/CMFCRibbonStatusBar::RemoveAll.md)|Entfernt alle Elemente aus der Menübandstatusleiste.|  
|[CMFCRibbonStatusBar::RemoveElement](../Topic/CMFCRibbonStatusBar::RemoveElement.md)|Entfernt das Element, das eine angegebene Befehls\-ID aus der Menübandstatusleiste verfügt.|  
|[CMFCRibbonStatusBar::SetInformation](../Topic/CMFCRibbonStatusBar::SetInformation.md)|Aktiviert oder deaktiviert den Informationsmodus für die Menübandstatusleiste.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCRibbonStatusBar::OnDrawInformation](../Topic/CMFCRibbonStatusBar::OnDrawInformation.md)|Zeigt die Informationszeichenfolge an, die auf der Menübandstatusleiste angezeigt wird, wenn der Informationsmodus aktiviert ist.|  
  
## Hinweise  
 Benutzer können die Sichtbarkeit von Menübandelementen auf einer Menübandstatusleiste ändern, indem sie das integrierte Kontextmenü für die Menübandstatusleiste verwenden.  Sie können Elemente dynamisch hinzufügen oder entfernen.  
  
 Eine Menübandstatusleiste umfasst zwei Bereiche: bei im Bereich und ein erweiterter Bereich.  Der erweiterte Bereich wird auf der rechten Seite der Menübandstatusleiste angezeigt und wird in einer anderen Farbe, als sich der Bereich ausführt.  
  
 In der Regel wird der zentrale Bereich der Statusleiste Statusbenachrichtigungen angezeigt, und der erweiterte Bereich werden Ansichtssteuerelemente an.  Der erweiterte Bereich bleibt so lange wie möglich sichtbar, wenn der Benutzer die Menübandstatusleiste Größe ändert.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie verschiedene Methoden in der Klasse `CMFCRibbonStatusBar` verwendet.  Im Beispiel wird gezeigt, wie ein neues Menübandelement hinzufügen, der Menübandstatusleiste ein Menübandelement dem erweiterten Bereich der Menübandstatusleiste hinzufügen, ein Trennzeichen und ermöglichen den normalen Modus für die Menübandstatusleiste hinzugefügt wird.  
  
 [!CODE [NVC_MFC_RibbonApp#15](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_RibbonApp#15)]  
[!CODE [NVC_MFC_RibbonApp#16](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_RibbonApp#16)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCRibbonBar](../../mfc/reference/cmfcribbonbar-class.md)  
  
 [CMFCRibbonStatusBar](../../mfc/reference/cmfcribbonstatusbar-class.md)  
  
## Anforderungen  
 **Header:** afxribbonstatusbar.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonBar Class](../../mfc/reference/cmfcribbonbar-class.md)   
 [CMFCRibbonBaseElement Class](../../mfc/reference/cmfcribbonbaseelement-class.md)   
 [CMFCRibbonBar Class](../../mfc/reference/cmfcribbonbar-class.md)
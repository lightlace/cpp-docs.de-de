---
title: "CTabView Class"
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
  - "CTabView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTabView class"
ms.assetid: 8e6ecd9d-d28d-432b-8ec8-0446f0204d52
caps.latest.revision: 32
caps.handback.revision: "20"
ms.author: "mblome"
manager: "ghogen"
---
# CTabView Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `CTabView`\-Klasse vereinfacht die Verwendung der Tab\-Steuerelement\-Klasse \([CMFCTabCtrl](../../mfc/reference/ctabview-class.md)\) in Anwendungen, die Dokument\-\/Ansichtarchitektur MFC verwenden.  
  
## Syntax  
  
```  
class CTabbedView : public CView  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CTabView::AddView](../Topic/CTabView::AddView.md)|Fügt eine neue Ansicht dem Tab\-Steuerelement hinzu.|  
|[CTabView::FindTab](../Topic/CTabView::FindTab.md)|Gibt den Index der angegebenen Ansicht in das Tab\-Steuerelement zurück.|  
|[CTabView::GetActiveView](../Topic/CTabView::GetActiveView.md)|Gibt einen Zeiger auf die derzeit aktive Ansicht zurück|  
|[CTabView::GetTabControl](../Topic/CTabView::GetTabControl.md)|Gibt einen Verweis auf das Tab\-Steuerelement zurück, das mit der Ansicht zugeordnet ist.|  
|[CTabView::RemoveView](../Topic/CTabView::RemoveView.md)|Entfernt die Ansicht im Tab\-Steuerelement.|  
|[CTabView::SetActiveView](../Topic/CTabView::SetActiveView.md)|Führt eine Ansicht aktiv.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CTabView::IsScrollBar](../Topic/CTabView::IsScrollBar.md)|Aufgerufen vom Framework, wenn eine Registerkartenansicht erstellt wird, um zu bestimmen, ob die Registerkartenansicht eine freigegebene horizontale Bildlaufleiste vorhanden.|  
|[CTabView::OnActivateView](../Topic/CTabView::OnActivateView.md)|Aufgerufen vom Framework, wenn die Registerkartenansicht aktiv oder inaktiv gemacht wird.|  
  
## Hinweise  
 Diese Klasse ist es einfach, eine Ansicht im Registerkartenformat in eine Dokument\/für zu setzen.  `CTabView` ist `CView` von abgeleitete Klasse, die ein eingebettetes `CMFCTabCtrl`\-Objekt enthält.  `CTabView` behandelt alle Meldungen, die erforderlich sind, um das `CMFCTabCtrl`\-Objekt zu unterstützen.  Leiten Sie eine Klasse von `CTabView` und werden Sie diese in die Anwendung ein, fügen Sie `CView` von abgeleitete Klassen hinzu, indem Sie die Methode verwenden. `AddView` Das Tab\-Steuerelement zeigt diese Ansichten als Registerkarten an.  
  
 Beispielsweise können Sie ein Dokument, das auf verschiedene Weise dargestellt werden kann: als Arbeitsblatt ein Diagramm, ein bearbeitbares Formular, u. a.  Sie können die einzelnen Ansichten erstellen, welche die Daten nach Bedarf zeichnen, in Ihr `CTabView` ein von abgeleitetes Objekt und sie ohne zusätzliche Codierung mit der TAB\-TASTE lassen.  
  
 [TabbedView\-Beispiel: MFC\-Anwendung für Ansicht im](../../top/visual-cpp-samples.md) veranschaulicht Verwendung von `CTabView`.  
  
## Beispiel  
 Im folgenden Beispiel wird gezeigt, wie `CTabView` im TabbedView\-Beispiel verwendet wird.  
  
 [!CODE [NVC_MFC_TabbedView#1](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_TabbedView#1)]  
  
## Anforderungen  
 **Header:** afxTabView.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CTabView Class](../../mfc/reference/ctabview-class.md)   
 [CView Class](../../mfc/reference/cview-class.md)
---
title: "CMFCRibbonQuickAccessToolBarDefaultState Class"
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
  - "CMFCRibbonQuickAccessToolBarDefaultState"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonQuickAccessToolBarDefaultState class"
ms.assetid: eca99200-b87b-47ba-b2e8-2f3f2444b176
caps.latest.revision: 28
caps.handback.revision: "16"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCRibbonQuickAccessToolBarDefaultState Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine Hilfsklasse, die Standardzustand für die Symbolleiste für den Schnellzugriff verwaltet, die auf der Menübandleiste \([CMFCRibbonBar Class](../../mfc/reference/cmfcribbonbar-class.md)\) positioniert wird.  
  
## Syntax  
  
```  
class CMFCRibbonQuickAccessToolBarDefaultState  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCRibbonQuickAccessToolBarDefaultState::CMFCRibbonQuickAccessToolBarDefaultState](../Topic/CMFCRibbonQuickAccessToolBarDefaultState::CMFCRibbonQuickAccessToolBarDefaultState.md)|Erstellt ein `CMFCRibbonQuickAccessToolbarDefaultState`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCRibbonQuickAccessToolBarDefaultState::AddCommand](../Topic/CMFCRibbonQuickAccessToolBarDefaultState::AddCommand.md)|Fügt einen Befehl dem Standardzustand für die Symbolleiste für den Schnellzugriff hinzu.  Dadurch wird die Symbolleiste nicht selbst.|  
|[CMFCRibbonQuickAccessToolBarDefaultState::CopyFrom](../Topic/CMFCRibbonQuickAccessToolBarDefaultState::CopyFrom.md)|Kopiert die Eigenschaften einer Symbolleiste für den Schnellzugriff auf andere.|  
|[CMFCRibbonQuickAccessToolBarDefaultState::RemoveAll](../Topic/CMFCRibbonQuickAccessToolBarDefaultState::RemoveAll.md)|Entfernt alle Befehle aus der Symbolleiste für den Schnellzugriff.  Dadurch wird die Symbolleiste nicht selbst.|  
  
## Hinweise  
 Nachdem Sie die Symbolleiste für den Schnellzugriff in der Anwendung erstellen, wird empfohlen Standardzustand festgelegt, indem der [CMFCRibbonBar::SetQuickAccessDefaultState](../Topic/CMFCRibbonBar::SetQuickAccessDefaultState.md) aufrufen.  Dieser Standardzustand wird wiederhergestellt, wenn ein Benutzer auf die Schaltfläche **Zurücksetzen** auf der Seite **Anpassen** von Dialogfeld **Optionen** der Anwendung klickt.  
  
## Vererbungshierarchie  
 [CMFCRibbonQuickAccessToolBarDefaultState](../../mfc/reference/cmfcribbonquickaccesstoolbardefaultstate-class.md)  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie ein Objekt der Klasse `CMFCRibbonQuickAccessToolbarDefaultState` erstellt und wie ein Befehl dem Standardzustand für die Symbolleiste für den Schnellzugriff hinzugefügt wird.  
  
 [!CODE [NVC_MFC_RibbonApp#21](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_RibbonApp#21)]  
  
## Anforderungen  
 **Header:** afxribbonquickaccesstoolbar.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonBar Class](../../mfc/reference/cmfcribbonbar-class.md)   
 [CMFCRibbonBar::SetQuickAccessDefaultState](../Topic/CMFCRibbonBar::SetQuickAccessDefaultState.md)
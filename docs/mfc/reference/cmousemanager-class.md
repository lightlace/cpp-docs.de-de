---
title: "CMouseManager Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMouseManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMouseManager class"
ms.assetid: a4d05017-4e44-4a40-8b57-4ece0de20481
caps.latest.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 28
---
# CMouseManager Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ermöglicht es einem Benutzer zu verschiedenen Befehlen des Mitarbeiters mit einem bestimmten Objekt [CView](../../mfc/reference/cview-class.md), wenn der Benutzer in doppelklicken, die anzeigen.  
  
## Syntax  
  
```  
class CMouseManager : public CObject  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMouseManager::AddView](../Topic/CMouseManager::AddView.md)|Fügt ein Objekt `CView` zum Dialogfeld **Anpassung** hinzu.  Das Dialogfeld **Anpassung** ermöglicht es dem Benutzer, um einen Doppelklick mit einem Befehl für jede der aufgeführten Ansichten zuzuordnen.|  
|[CMouseManager::GetViewDblClickCommand](../Topic/CMouseManager::GetViewDblClickCommand.md)|Gibt den Befehl zurück, der ausgeführt wird, wenn der Benutzer in die bereitgestellte Ansicht doppelklickt.|  
|[CMouseManager::GetViewIconId](../Topic/CMouseManager::GetViewIconId.md)|Gibt das Symbol zurück, das mit der bereitgestellten Ansicht ID zugeordnet ist|  
|[CMouseManager::GetViewIdByName](../Topic/CMouseManager::GetViewIdByName.md)|Gibt die Ansicht ID zurück, die mit dem angegebenen Namen zugeordnet ist.|  
|[CMouseManager::GetViewNames](../Topic/CMouseManager::GetViewNames.md)|Ruft eine Liste aller hinzugefügten Ansichtsnamen ab.|  
|[CMouseManager::LoadState](../Topic/CMouseManager::LoadState.md)|Lädt den `CMouseManager` Zustand aus der Windows\-Registrierung.|  
|[CMouseManager::SaveState](../Topic/CMouseManager::SaveState.md)|Schreibt den `CMouseManager` Zustand zur Windows\-Registrierung.|  
|[CMouseManager::SetCommandForDblClk](../Topic/CMouseManager::SetCommandForDblClk.md)|Ordnet den bereitgestellten Befehl und die bereitgestellte Ansicht zu.|  
  
## Hinweise  
 Die `CMouseManager`\-Klasse verwaltet eine Auflistung `CView`\-Objekte bei.  Jede Ansicht wird durch einen Namen und durch eine ID identifiziert  Diese Ansichten **Anpassung** werden im Dialogfeld angezeigt.  Der Benutzer kann den Befehl ändern, der mit jeder Ansicht durch das Dialogfeld **Anpassung** zugeordnet ist.  Der zugeordnete Befehl wird ausgeführt, wenn der Benutzer in dieser Ansicht doppelklickt.  Um dieses aus einer Codierungsperspektive zu unterstützen, müssen Sie die `WM_LBUTTONDBLCLK` Meldung verarbeiten und die [CWinAppEx::OnViewDoubleClick](../Topic/CWinAppEx::OnViewDoubleClick.md)\-Funktion im Code für dieses Objekt. `CView` aufrufen.  
  
 Sie sollten ein `CMouseManager`\-Objekt nicht manuell erstellen.  Es wird durch das Framework der Anwendung erstellt.  Es wird automatisch beim Beenden von die Anwendung zerstört.  Um einen Zeiger auf den Mausmanager für die Anwendung abzurufen, rufen Sie [CWinAppEx::GetMouseManager](../Topic/CWinAppEx::GetMouseManager.md) auf.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMouseManager](../../mfc/reference/cmousemanager-class.md)  
  
## Anforderungen  
 **Header:** afxmousemanager.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx Class](../../mfc/reference/cwinappex-class.md)   
 [Anpassen von Tastatur und Maus](../../mfc/keyboard-and-mouse-customization.md)
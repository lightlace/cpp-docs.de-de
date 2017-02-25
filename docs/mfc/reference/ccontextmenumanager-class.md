---
title: "CContextMenuManager Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CContextMenuManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CContextMenuManager class"
ms.assetid: 1de20640-243c-47e1-85de-1baa4153bc83
caps.latest.revision: 32
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 33
---
# CContextMenuManager Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Das `CContextMenuManager`\-Objekt verwaltet Kontextmenüs, auch als Kontextmenüs.  
  
## Syntax  
  
```  
class CContextMenuManager : public CObject  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CContextMenuManager::CContextMenuManager](../Topic/CContextMenuManager::CContextMenuManager.md)|Erstellt ein `CContextMenuManager`\-Objekt.|  
|`CContextMenuManager::~CContextMenuManager`|Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CContextMenuManager::AddMenu](../Topic/CContextMenuManager::AddMenu.md)|Fügt ein neues Kontextmenü hinzu.|  
|[CContextMenuManager::GetMenuById](../Topic/CContextMenuManager::GetMenuById.md)|Gibt ein Handle für das Menü zurück, das mit der bereitgestellten Ressourcen\-ID zugeordnet ist|  
|[CContextMenuManager::GetMenuByName](../Topic/CContextMenuManager::GetMenuByName.md)|Gibt ein Handle für das Menü zurück, das den angegebenen Menünamen übereinstimmt.|  
|[CContextMenuManager::GetMenuNames](../Topic/CContextMenuManager::GetMenuNames.md)|Gibt eine Liste von Menünamen zurück.|  
|[CContextMenuManager::LoadState](../Topic/CContextMenuManager::LoadState.md)|Lädt die Kontextmenüs, die in der Windows\-Registrierung gespeichert werden.|  
|[CContextMenuManager::ResetState](../Topic/CContextMenuManager::ResetState.md)|Löscht die Kontextmenüs vom Kontextmenümanager.|  
|[CContextMenuManager::SaveState](../Topic/CContextMenuManager::SaveState.md)|Speichert Kontextmenüs zur Windows\-Registrierung.|  
|[CContextMenuManager::SetDontCloseActiveMenu](../Topic/CContextMenuManager::SetDontCloseActiveMenu.md)|Steuert, ob `CContextMenuManager` das aktive Kontextmenü geschlossen wird, wenn ein neues Kontextmenü angezeigt wird.|  
|[CContextMenuManager::ShowPopupMenu](../Topic/CContextMenuManager::ShowPopupMenu.md)|Zeigt das angegebene Kontextmenü an.|  
|[CContextMenuManager::TrackPopupMenu](../Topic/CContextMenuManager::TrackPopupMenu.md)|Zeigt das angegebene Kontextmenü an.  Gibt den Index des ausgewählten Menübefehls zurück.|  
  
## Hinweise  
 `CContextMenuManager` verwaltet Kontextmenüs und stellt sicher, dass sie eine konsistente Darstellung haben.  
  
 Sie sollten ein `CContextMenuManager`\-Objekt nicht manuell erstellen.  Das Framework der Anwendung erstellt das `CContextMenuManager`\-Objekt.  Sie sollten [CWinAppEx::InitContextMenuManager](../Topic/CWinAppEx::InitContextMenuManager.md) aufrufen, wenn die Anwendung initialisiert wird.  Nachdem Sie den Kontextmanager initialisiert haben, verwenden Sie die \- Methode [CWinAppEx::GetContextMenuManager](../Topic/CWinAppEx::GetContextMenuManager.md), um ein Zeiger auf Kontextmanager für die Anwendung abzurufen.  
  
 Sie können Kontextmenüs zur Laufzeit erstellen, indem Sie `AddMenu` aufrufen.  Wenn Sie das erste Menü ohne empfangende Benutzereingaben anzeigen möchten, rufen Sie `ShowPopupMenu` auf.  `TrackPopupMenu` wird verwendet, wenn Sie ein Menü und ein Wartung Benutzereingaben erstellen möchten.  `TrackPopupMenu` gibt den Index des ausgewählten Befehls oder des 0 zurück, wenn der Benutzer der ohne alles auszuwählen gebeendet wird.  
  
 `CContextMenuManager` kann ihren Zustand zur Windows\-Registrierung auch speichern und laden.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie ein Menü einem `CContextMenuManager`\-Objekt hinzufügen und wie Sie nicht das aktive Popupmenü enthält, wenn das Objekt `CContextMenuManager` ein neues Popupmenü anzeigt.  Dieser Codeausschnitt ist Teil [Gewohnheits\-Seitenbeispiel](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_CustomPages#4](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_CustomPages#4)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md)  
  
## Anforderungen  
 **Header:** afxcontextmenumanager.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx Class](../../mfc/reference/cwinappex-class.md)   
 [CWinAppEx::InitContextMenuManager](../Topic/CWinAppEx::InitContextMenuManager.md)
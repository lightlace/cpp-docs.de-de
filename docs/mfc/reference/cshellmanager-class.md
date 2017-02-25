---
title: "CShellManager Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CShellManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CShellManager class"
ms.assetid: f15c4c1a-6fae-487d-9913-9b7369b33da0
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CShellManager Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implementiert mehrere Möglichkeiten, die es Ihnen ermöglichen, mit Zeigern zu den Namenlisten \(PIDLs\).  
  
## Syntax  
  
```  
class CShellManager : public CObject  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CShellManager::CShellManager](../Topic/CShellManager::CShellManager.md)|Erstellt ein `CShellManager`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CShellManager::BrowseForFolder](../Topic/CShellManager::BrowseForFolder.md)|Zeigt ein Dialogfeld an, in dem Benutzer ermöglicht, einen Shellordner auszuwählen.|  
|[CShellManager::ConcatenateItem](../Topic/CShellManager::ConcatenateItem.md)|Verkettet zwei PIDLs.|  
|[CShellManager::CopyItem](../Topic/CShellManager::CopyItem.md)|Erstellt ein neues PIDL und kopiert das angegebene PIDL hinzufügen.|  
|[CShellManager::CreateItem](../Topic/CShellManager::CreateItem.md)|Erstellt ein neues PIDL des angegebenen Größe.|  
|[CShellManager::FreeItem](../Topic/CShellManager::FreeItem.md)|Löscht das angegebene PIDL.|  
|[CShellManager::GetItemCount](../Topic/CShellManager::GetItemCount.md)|Gibt die Anzahl der Elemente im angegebenen PIDL zurück.|  
|[CShellManager::GetItemSize](../Topic/CShellManager::GetItemSize.md)|Gibt die Größe des angegebenen PIDL zurück.|  
|[CShellManager::GetNextItem](../Topic/CShellManager::GetNextItem.md)|Gibt den nächsten Element vom PIDL zurück.|  
|[CShellManager::GetParentItem](../Topic/CShellManager::GetParentItem.md)|Ruft das übergeordnete Element des angegebenen Elements ab.|  
|[CShellManager::ItemFromPath](../Topic/CShellManager::ItemFromPath.md)|Ruft das PIDL für das Element ab, das durch den angegebenen Pfad identifiziert wird.|  
  
## Hinweise  
 Die Methoden `CShellManager`\-Klasse alle Daten mit PIDLs.  Ein PIDL ist ein eindeutiger Bezeichner für ein Shellobjekt.  
  
 Sie sollten ein `CShellManager`\-Objekt nicht manuell erstellen.  Es wird automatisch vom Framework der Anwendung erstellt.  Sie sollten [CWinAppEx::InitShellManager](../Topic/CWinAppEx::InitShellManager.md) während des Initialisierungsprozesses der Anwendung aufrufen.  Um einen Zeiger auf den Shellmanager für die Anwendung abzurufen, rufen Sie [CWinAppEx::GetShellManager](../Topic/CWinAppEx::GetShellManager.md) auf.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CShellManager](../../mfc/reference/cshellmanager-class.md)  
  
## Anforderungen  
 **Header:** afxshellmanager.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)
---
title: "CMFCDisableMenuAnimation Class"
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
  - "CMFCDisableMenuAnimation"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCDisableMenuAnimation class"
ms.assetid: c6eb07da-c382-43d6-8028-007f2320e50e
caps.latest.revision: 22
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCDisableMenuAnimation Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Deaktiviert Popupmenüanimation.  
  
## Syntax  
  
```  
class CMFCDisableMenuAnimation  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|||  
|-|-|  
|Name|Description|  
|`CMFCDisableMenuAnimation::CMFCDisableMenuAnimation`|Erstellt ein `CMFCDisableMenuAnimation`\-Objekt.|  
|`CMFCDisableMenuAnimation::~CMFCDisableMenuAnimation`|Destruktor.|  
  
### Öffentliche Methoden  
  
|||  
|-|-|  
|Name|Description|  
|[CMFCDisableMenuAnimation::Restore](../Topic/CMFCDisableMenuAnimation::Restore.md)|Stellt die vorherigen Animation wieder her, die das Framework diese ist, das verwendet wird, um ein Popupmenü anzuzeigen.|  
  
### Datenmember  
  
|||  
|-|-|  
|Name|Description|  
|`CMFCDisableMenuAnimation::m_animType`|Speichert den vorherigen Popupmenüanimationstyp.|  
  
### Hinweise  
 Verwenden Sie diese Hilfsklasse, um Popupmenüanimation vorübergehend zu deaktivieren \(beispielsweise, wenn Sie Maus oder Tastaturbefehle verarbeiten\).  
  
 Ein Objekt `CMFCDisableMenuAnimation` deaktiviert Popupmenüanimation während seiner Lebensdauer.  Der Konstruktor speichert die aktuelle Popupmenüanimation im `m_animType` Feld und Sätze, die die aktuelle Animation auf `CMFCPopupMenu::NO_ANIMATION` eingeben.  Der Destruktor stellt den vorherigen Animationstyp wieder her.  
  
 Sie können ein `CMFCDisableMenuAnimation`\-Objekt auf dem Stapel zur Sperrungspopupmenüanimation während einer einzelnen Funktion erstellen.  Wenn Sie Popupmenüanimation zwischen Funktionen deaktivieren möchten, erstellen Sie ein `CMFCDisableMenuAnimation`\-Objekt auf dem Heap und löschen Sie sie dann, wenn Sie Popupmenüanimation wiederherstellen möchten.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie der Stapel verwendet, um Menüanimation vorübergehend zu deaktivieren.  
  
 [!CODE [NVC_MFC_Misc#1](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_Misc#1)]  
  
## Vererbungshierarchie  
 [CMFCDisableMenuAnimation](../../mfc/reference/cmfcdisablemenuanimation-class.md)  
  
## Anforderungen  
 **Header:** afxpopupmenu.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCPopupMenu Class](../../mfc/reference/cmfcpopupmenu-class.md)
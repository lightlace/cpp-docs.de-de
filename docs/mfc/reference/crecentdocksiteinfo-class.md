---
title: "CRecentDockSiteInfo Class"
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
  - "CRecentDockSiteInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRecentDockSiteInfo class"
ms.assetid: 2dd14f95-d5a2-4461-a7a5-2c6c36a3a165
caps.latest.revision: 26
caps.handback.revision: "14"
ms.author: "mblome"
manager: "ghogen"
---
# CRecentDockSiteInfo Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bei der `CRecentDockSiteInfo`\-Klasse handelt es sich um eine Hilfsklasse, die die neuesten Statusinformationen für die [CPane Class](../../mfc/reference/cpane-class.md) speichert.  
  
## Syntax  
  
```  
class CRecentDockSiteInfo : public CObject  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|`CRecentDockSiteInfo::CRecentDockSiteInfo`|Standardkonstruktor|  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CRecentDockSiteInfo::CleanUp](../Topic/CRecentDockSiteInfo::CleanUp.md)||  
|[CRecentDockSiteInfo::GetRecentDefaultPaneDivider](../Topic/CRecentDockSiteInfo::GetRecentDefaultPaneDivider.md)||  
|[CRecentDockSiteInfo::GetRecentDockedPercent](../Topic/CRecentDockSiteInfo::GetRecentDockedPercent.md)||  
|[CRecentDockSiteInfo::GetRecentDockedRect](../Topic/CRecentDockSiteInfo::GetRecentDockedRect.md)||  
|[CRecentDockSiteInfo::GetRecentListOfPanes](../Topic/CRecentDockSiteInfo::GetRecentListOfPanes.md)||  
|[CRecentDockSiteInfo::GetRecentPaneContainer](../Topic/CRecentDockSiteInfo::GetRecentPaneContainer.md)||  
|[CRecentDockSiteInfo::GetRecentTabContainer](../Topic/CRecentDockSiteInfo::GetRecentTabContainer.md)||  
|[CRecentDockSiteInfo::Init](../Topic/CRecentDockSiteInfo::Init.md)||  
|[CRecentDockSiteInfo::IsRecentLeftPane](../Topic/CRecentDockSiteInfo::IsRecentLeftPane.md)||  
|[CRecentDockSiteInfo::operator \=](../Topic/CRecentDockSiteInfo::operator%20=.md)||  
|[CRecentDockSiteInfo::SaveListOfRecentPanes](../Topic/CRecentDockSiteInfo::SaveListOfRecentPanes.md)||  
|[CRecentDockSiteInfo::SetInfo](../Topic/CRecentDockSiteInfo::SetInfo.md)||  
|[CRecentDockSiteInfo::StoreDockInfo](../Topic/CRecentDockSiteInfo::StoreDockInfo.md)||  
  
## Hinweise  
 Die `CRecentDockSiteInfo`\-Klasse ist eine Datenverwaltungsklasse.  Sie verfolgt den letzten Status eines `CPane` während des Übergangs zwischen angedockt und unverankert nach.  Wenn ein Benutzer auf einen unverankerten andockbaren Bereich klickt, wird der Bereich angedockt.  Durch das Doppelklicken auf den angedockten Bereich wird dieser zu seiner vorherigen Position, Größe und zum vorherigen Status zurückversetzt.  Gleiches gilt, wenn der Bereich erneut angedockt wird, wird er an seine vorherige Andockposition zurückversetzt.  Dies wird durch diese Datenklasse ermöglicht.  Da die Member dieser Klasse Statusinformationen für den angedockten Bereich speichern können, sollten sie nicht direkt durch Ihre Anwendung geändert werden.  
  
 Ein `CRecentDockSiteInfo`\-Objekt wird erstellt, sobald ein Bereich erstellt wird.  Jedes `CPane`\-Objekt verfügt über eine Membervariable [CPane::m\_recentDockInfo](../Topic/CPane::m_recentDockInfo.md) zum Speichern dieser Informationen.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CRecentDockSiteInfo](../../mfc/reference/crecentdocksiteinfo-class.md)  
  
## Anforderungen  
 **Header:** afxrecentDockSiteInfo.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CDockSite Class](../../mfc/reference/cdocksite-class.md)
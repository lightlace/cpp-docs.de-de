---
title: "CMDITabInfo Class"
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
  - "CMDITabInfo"
  - "CMDITabInfo.CMDITabInfo"
  - "CMDITabInfo::CMDITabInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMDITabInfo class"
  - "CMDITabInfo class, Konstruktor"
ms.assetid: 988ae1b7-4f7f-4239-b88f-7e28b3291c5e
caps.latest.revision: 37
caps.handback.revision: "25"
ms.author: "mblome"
manager: "ghogen"
---
# CMDITabInfo Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `CMDITabInfo`\-Klasse wird verwendet, um Parameter zu [CMDIFrameWndEx::EnableMDITabbedGroups](../Topic/CMDIFrameWndEx::EnableMDITabbedGroups.md)\-Methode zu übergeben.  Festgelegte Member dieser Klasse, um das Verhalten der MDI mit den versehenen Gruppen zu steuern.  
  
## Syntax  
  
```  
class CMDITabInfo   
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|`CMDITabInfo::CMDITabInfo`|Standardkonstruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMDITabInfo::Serialize](../Topic/CMDITabInfo::Serialize.md)|Liest oder Schreiben dieses Objekt von oder einem Archiv.|  
  
### Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CMDITabInfo::m\_bActiveTabCloseButton;](../Topic/CMDITabInfo::m_bActiveTabCloseButton;.md)|Gibt an, ob eine Schaltfläche **Schließen** auf der Bezeichnung der aktiven Registerkarte angezeigt wird.|  
|[CMDITabInfo::m\_bAutoColor](../Topic/CMDITabInfo::m_bAutoColor.md)|Gibt an, ob die MDI\-Registerkarten Farbe.|  
|[CMDITabInfo::m\_bDocumentMenu](../Topic/CMDITabInfo::m_bDocumentMenu.md)|Gibt die Registerkartengemeinschaftsausstellungen ob ein Popupmenü an, das eine Liste der geöffneten Dokumenten oder Bildlaufschaltflächen anzeigt.|  
|[CMDITabInfo::m\_bEnableTabSwap](../Topic/CMDITabInfo::m_bEnableTabSwap.md)|Gibt an, ob der Benutzer die Positionen von Registerkarten auslagern kann, indem er zieht.|  
|[CMDITabInfo::m\_bFlatFrame](../Topic/CMDITabInfo::m_bFlatFrame.md)|Gibt an, ob Registerkarten flachen Frames haben.|  
|[CMDITabInfo::m\_bTabCloseButton](../Topic/CMDITabInfo::m_bTabCloseButton.md)|Gibt an, ob jede Registerkartenbezeichnung **Schließen** eine Schaltfläche angezeigt wird.|  
|[CMDITabInfo::m\_bTabCustomTooltips](../Topic/CMDITabInfo::m_bTabCustomTooltips.md)|Gibt an, ob benutzerdefinierte QuickInfos aktiviert werden.|  
|[CMDITabInfo::m\_bTabIcons](../Topic/CMDITabInfo::m_bTabIcons.md)|Gibt an, ob Symbole auf MDI\-Registerkarten anzeigt.|  
|[CMDITabInfo::m\_nTabBorderSize](../Topic/CMDITabInfo::m_nTabBorderSize.md)|Gibt die Rahmengröße jedes Registerkartenfensters an.|  
|[CMDITabInfo::m\_style](../Topic/CMDITabInfo::m_style.md)|Gibt das Format der Registerkartenbezeichnungen an.|  
|[CMDITabInfo::m\_tabLocation](../Topic/CMDITabInfo::m_tabLocation.md)|Gibt an, ob die Registerkartenbezeichnungen oben oder den unteren Rand der Seite gefunden werden.|  
  
## Hinweise  
 Diese Klasse gibt die Parameter der MDI\-Registerkartengruppen an, die das Framework erstellt.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie die Werte verschiedener Membervariablen in `CMDITabInfo`\-Klasse festgelegt wird.  
  
 [!CODE [NVC_MFC_MDITab#1](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_MDITab#1)]  
  
## Vererbungshierarchie  
 [CMDITabInfo](../../mfc/reference/cmditabinfo-class.md)  
  
## Anforderungen  
 **Header:** afxmdiclientareawnd.h  
  
## Siehe auch  
 [CMDIFrameWndEx\-Klasse](../../mfc/reference/cmdiframewndex-class.md)   
 [MDI\-Gruppen im Registerkartenformat](../../mfc/mdi-tabbed-groups.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)
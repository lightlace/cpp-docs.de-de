---
title: "CSmartDockingInfo Class"
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
  - "CSmartDockingInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSmartDockingInfo class"
ms.assetid: cab04f38-4bc1-4378-9337-c56fc87fbd68
caps.latest.revision: 27
caps.handback.revision: "15"
ms.author: "mblome"
manager: "ghogen"
---
# CSmartDockingInfo Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Definiert die Darstellung von Markern intelligenten Andocken.  
  
## Syntax  
  
```  
class CSmartDockingInfo : public CObject  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|`CSmartDockingInfo::CSmartDockingInfo`|Standardkonstruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CSmartDockingInfo::CopyTo](../Topic/CSmartDockingInfo::CopyTo.md)|Kopiert die aktuellen intelligenten Andocken Informationsparameter in das bereitgestellte [CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md)\-Objekt.|  
  
### Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CSmartDockingInfo::m\_bUseThemeColorInShading](../Topic/CSmartDockingInfo::m_bUseThemeColorInShading.md)|Gibt an, ob das aktuelle Design Farbe verwendet, wenn das Framework intelligente andockbare Marker anzeigt.|  
|[CSmartDockingInfo::m\_clrBaseBackground](../Topic/CSmartDockingInfo::m_clrBaseBackground.md)|Gibt die Hintergrundfarbe von intelligenten Andocken Markierungen an.|  
|[CSmartDockingInfo::m\_clrToneDest](../Topic/CSmartDockingInfo::m_clrToneDest.md)|Gibt die Farbe an, die `m_clrToneSrc` in den intelligenten Andocken Markerbitmaps ersetzt.|  
|[CSmartDockingInfo::m\_clrToneSrc](../Topic/CSmartDockingInfo::m_clrToneSrc.md)|Gibt die Farbe von intelligenten Andocken Markerbitmaps an.|  
|[CSmartDockingInfo::m\_clrTransparent](../Topic/CSmartDockingInfo::m_clrTransparent.md)|Gibt die Farbe von intelligenten Andocken Markerbitmaps an, wenn sie transparent sind.|  
|[CSmartDockingInfo::m\_nCentralGroupOffset](../Topic/CSmartDockingInfo::m_nCentralGroupOffset.md)|Gibt den Offset der zentralen Gruppe der intelligenten Andocken Markierung aus den Grenzen des zentralen Gruppenrechtecks an.|  
|[CSmartDockingInfo::m\_sizeTotal](../Topic/CSmartDockingInfo::m_sizeTotal.md)|Gibt die Gesamtgröße aller intelligenten Andocken Markierung in einer Gruppe an.|  
|[CSmartDockingInfo::m\_uiMarkerBmpResID](../Topic/CSmartDockingInfo::m_uiMarkerBmpResID.md)|Definiert die Ressourcen\-IDs der Bitmap, die das Framework für intelligente andockbare Markierung verwendet, die nicht hervorgehoben werden.|  
|[CSmartDockingInfo::m\_uiMarkerLightBmpResID](../Topic/CSmartDockingInfo::m_uiMarkerLightBmpResID.md)|Definiert die Ressourcen\-IDs der Bitmap, die das Framework für intelligente andockbare Markierung verwendet, die hervorgehoben werden.|  
  
## Hinweise  
 Das Framework behandelt intelligente andockbare Markierung intern.  Die folgende Abbildung zeigt die intelligenten Andocken StandardMarker an:  
  
 ![Standardmarker für intelligentes Andocken](../../mfc/reference/media/nextsdmarkers.png "nextSDmarkers")  
  
 In dieser Abbildung zeigt das Bild auf der linken Seite einen intelligenten Andocken Markierung der zentralen Gruppe an, der Andocken nicht zu einer aktivierten Registerkarte verfügt.  Das Bild in der Mitte wird einem rechten Rand intelligenten Andocken Markierung an.  Das Bild rechts zeigt einen intelligenten Andocken Markierung der zentralen Gruppe an, der das Andocken zu einer aktivierten Registerkarte verfügt.  Der intelligente andockbare Markierung der zentralen Gruppe verfügt über eine zentrale Bitmap und fünf intelligente andockbare Markerbitmaps.  
  
 Sie können die folgenden Parameter von intelligenten Andocken Markierungen anpassen:  
  
-   Farbe  Beispielsweise können Sie die Farbe Blau der Markierung in der Abbildung durch eine benutzerdefinierte Farbe ersetzen.  
  
-   Transparenzfarbe.  
  
-   Offset eines intelligenten Andocken Markierung in der zentralen Gruppe im Rahmen des umschließenden Rechtecks.  
  
-   Die Bitmap, die die zentrale Gruppe darstellt.  
  
-   Die Bitmaps, das die regulären und markierten intelligenten Andocken Markierung darstellt.  
  
 Die folgende Abbildung zeigt ein Beispiel für intelligenten Andocken Markierungen an, die angepasst werden:  
  
 ![Benutzerdefinierte Marker für intelligentes Andocken](../../mfc/reference/media/nextsdmarkerscustom.png "nextSDmarkersCustom")  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md)  
  
## Anforderungen  
 **Header:** afxDockingManager.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)
---
title: "CMFCToolTipInfo Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCToolTipInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCToolTipInfo class"
ms.assetid: f9d3d7f8-1f08-4342-a7b2-683860e5d2a5
caps.latest.revision: 27
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 29
---
# CMFCToolTipInfo Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Speichert Informationen über die visuelle Darstellung von QuickInfos.  
  
## Syntax  
  
```  
class CMFCToolTipInfo  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CMFCToolTipInfo::operator\=](../Topic/CMFCToolTipInfo::operator=.md)||  
  
### Datenmember  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CMFCToolTipInfo::m\_bBalloonTooltip](../Topic/CMFCToolTipInfo::m_bBalloonTooltip.md)|Eine boolesche Variable, die angibt, ob die QuickInfo über eine Sprechblasendarstellung verfügt.|  
|[CMFCToolTipInfo::m\_bBoldLabel](../Topic/CMFCToolTipInfo::m_bBoldLabel.md)|Eine boolesche Variable, die angibt, ob die QuickInfo\-Bezeichnungen in fett formatierter Schrift angezeigt werden.|  
|[CMFCToolTipInfo::m\_bDrawDescription](../Topic/CMFCToolTipInfo::m_bDrawDescription.md)|Eine boolesche Variable, die angibt, ob die QuickInfo eine Beschreibung enthält.|  
|[CMFCToolTipInfo::m\_bDrawIcon](../Topic/CMFCToolTipInfo::m_bDrawIcon.md)|Eine boolesche Variable, die angibt, ob die QuickInfo ein Symbol enthält.|  
|[CMFCToolTipInfo::m\_bDrawSeparator](../Topic/CMFCToolTipInfo::m_bDrawSeparator.md)|Eine boolesche Variable, die angibt, ob eine Trennzeichen zwischen der QuickInfo\-Bezeichnung und der QuickInfo\-Beschreibung angezeigt wird.|  
|[CMFCToolTipInfo::m\_bRoundedCorners](../Topic/CMFCToolTipInfo::m_bRoundedCorners.md)|Eine boolesche Variable, die angibt, ob die QuickInfo abgerundete Ecken besitzt.|  
|[CMFCToolTipInfo::m\_bVislManagerTheme](../Topic/CMFCToolTipInfo::m_bVislManagerTheme.md)|Eine boolesche Variable, der angibt, ob die Darstellung der QuickInfo durch einen visuellen Manager gesteuert werden soll \(siehe [CMFCVisualManager Class](../../mfc/reference/cmfcvisualmanager-class.md)\).|  
|[CMFCToolTipInfo::m\_clrBorder](../Topic/CMFCToolTipInfo::m_clrBorder.md)|Die Farbe des QuickInfo\-Rahmens.|  
|[CMFCToolTipInfo::m\_clrFill](../Topic/CMFCToolTipInfo::m_clrFill.md)|Die Farbe des QuickInfo\-Hintergrunds.|  
|[CMFCToolTipInfo::m\_clrFillGradient](../Topic/CMFCToolTipInfo::m_clrFillGradient.md)|Die Farbe der Verlaufsfläche in der QuickInfo.|  
|[CMFCToolTipInfo::m\_clrText](../Topic/CMFCToolTipInfo::m_clrText.md)|Die Textfarbe in der QuickInfo.|  
|[CMFCToolTipInfo::m\_nGradientAngle](../Topic/CMFCToolTipInfo::m_nGradientAngle.md)|Der Winkel der Verlaufsfläche in der QuickInfo.|  
|[CMFCToolTipInfo::m\_nMaxDescrWidth](../Topic/CMFCToolTipInfo::m_nMaxDescrWidth.md)|Die maximal mögliche Breite der Beschreibung in der QuickInfo in Pixel.|  
  
## Hinweise  
 Verwenden Sie [CMFCToolTipCtrl Class](../../mfc/reference/cmfctooltipctrl-class.md), `CMFCToolTipInfo` und [CTooltipManager Class](../../mfc/reference/ctooltipmanager-class.md) zusammen, um benutzerdefinierte QuickInfos in Ihre Anwendung zu implementieren.  Ein Beispiel dafür, wie Sie diese QuickInfo\-Klassen verwenden, finden Sie im Thema [CMFCToolTipCtrl Class](../../mfc/reference/cmfctooltipctrl-class.md).  
  
## Beispiel  
 Im folgenden Beispiel wird die Festlegung der Werte für die verschiedenen Membervariablen in der `CMFCToolTipInfo`\-Klasse veranschaulicht.  
  
 [!CODE [NVC_MFC_RibbonApp#42](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_RibbonApp#42)]  
  
## Vererbungshierarchie  
 [CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md)  
  
## Anforderungen  
 **Header:** afxtooltipctrl.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CTooltipManager Class](../../mfc/reference/ctooltipmanager-class.md)   
 [CMFCToolTipCtrl Class](../../mfc/reference/cmfctooltipctrl-class.md)
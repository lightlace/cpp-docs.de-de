---
title: "CMFCToolTipCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCToolTipCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCToolTipCtrl class"
ms.assetid: 9fbfcfb1-a8ab-417f-ae29-9a9ca85ee58f
caps.latest.revision: 33
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 35
---
# CMFCToolTipCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine erweiterte QuickInfo\-Implementierung auf Grundlage der [CToolTipCtrl Class](../../mfc/reference/ctooltipctrl-class.md).  Eine QuickInfo auf Grundlage der `CMFCToolTipCtrl`\-Klasse kann ein Symbol, eine Bezeichnung und eine Beschreibung anzeigen.  Sie können das Aussehen anpassen, indem Sie einen Farbverlauf, einen benutzerdefinierter Text, Rahmenfarben, fetten Text, abgerundete Ecken oder ein Sprechblasenformat verwenden.  
  
## Syntax  
  
```  
class CMFCToolTipCtrl : public CToolTipCtrl  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|`CMFCToolTipCtrl::CMFCToolTipCtrl`|Standardkonstruktor|  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CMFCToolTipCtrl::GetIconSize](../Topic/CMFCToolTipCtrl::GetIconSize.md)|Gibt die Größe eines QuickInfo\-Symbols zurück.|  
|[CMFCToolTipCtrl::GetParams](../Topic/CMFCToolTipCtrl::GetParams.md)|Gibt die Anzeigeeinstellungen für QuickInfo zurück.|  
|[CMFCToolTipCtrl::OnDrawBorder](../Topic/CMFCToolTipCtrl::OnDrawBorder.md)|Zeichnet den QuickInfo\-Rahmen.|  
|[CMFCToolTipCtrl::OnDrawDescription](../Topic/CMFCToolTipCtrl::OnDrawDescription.md)||  
|[CMFCToolTipCtrl::OnDrawIcon](../Topic/CMFCToolTipCtrl::OnDrawIcon.md)|Zeigt ein QuickInfo\-Symbol an.|  
|[CMFCToolTipCtrl::OnDrawLabel](../Topic/CMFCToolTipCtrl::OnDrawLabel.md)|Gibt die QuickInfo\-Bezeichnung an oder berechnet die Bezeichnungsgröße.|  
|[CMFCToolTipCtrl::OnDrawSeparator](../Topic/CMFCToolTipCtrl::OnDrawSeparator.md)|Zeichnet die Trennlinie zwischen der QuickInfo\-Bezeichnung und \-Beschreibung.|  
|[CMFCToolTipCtrl::OnFillBackground](../Topic/CMFCToolTipCtrl::OnFillBackground.md)|Füllt den QuickInfo\-Hintergrund.|  
|[CMFCToolTipCtrl::SetDescription](../Topic/CMFCToolTipCtrl::SetDescription.md)|Legt die von der QuickInfo angezeigte Beschreibung fest.|  
|[CMFCToolTipCtrl::SetFixedWidth](../Topic/CMFCToolTipCtrl::SetFixedWidth.md)||  
|[CMFCToolTipCtrl::SetHotRibbonButton](../Topic/CMFCToolTipCtrl::SetHotRibbonButton.md)||  
|[CMFCToolTipCtrl::SetLocation](../Topic/CMFCToolTipCtrl::SetLocation.md)||  
|[CMFCToolTipCtrl::SetParams](../Topic/CMFCToolTipCtrl::SetParams.md)|Gibt die visuelle Darstellung einer QuickInfo mit einem `CMFCToolTipInfo`\-Objekt an.|  
  
## Hinweise  
 Verwenden Sie zum Implementieren von benutzerdefinierten QuickInfos in Ihrer Anwendung die `CMFCToolTipCtrl`\- `CMFCToolTipInfo` und [CTooltipManager Class](../../mfc/reference/ctooltipmanager-class.md)\-Objekte.  
  
 Befolgen Sie die folgenden Schritte, wenn Sie beispielsweise QuickInfo\-Sprechblasen verwenden möchten:  
  
 1.  Initialisieren Sie mit der [CWinAppEx Class](../../mfc/reference/cwinappex-class.md)\-Methode den QuickInfo\-Manager in Ihrer Anwendung.  
  
 2.  Erstellen Sie eine `CMFCToolTipInfo`\-Struktur, um den gewünschten visuellen Stil anzugeben:  
  
```  
CMFCToolTipInfo params;  
 params.m_bBoldLabel = FALSE;  
 params.m_bDrawDescription = FALSE;  
 params.m_bDrawIcon = FALSE;  
 params.m_bRoundedCorners = TRUE;  
 params.m_bDrawSeparator = FALSE;  
 if (m_bCustomColors)  
 {  
  params.m_clrFill = RGB (255, 255, 255);  
  params.m_clrFillGradient = RGB (228, 228, 240);  
  params.m_clrText = RGB (61, 83, 80);  
  params.m_clrBorder = RGB (144, 149, 168);  
 }  
```  
  
 3.  Legen Sie mit der [CTooltipManager::SetTooltipParams](../Topic/CTooltipManager::SetTooltipParams.md)\-Methode den visuellen Stil für alle QuickInfos in der Anwendung fest, indem Sie die im `CMFCToolTipInfo`\-Objekt definierten Stile verwenden:  
  
```  
theApp.GetTooltipManager ()->SetTooltipParams (AFX_TOOLTIP_TYPE_ALL,  
    RUNTIME_CLASS (CMFCToolTipCtrl), &params);  
```  
  
 Zum Steuern des QuickInfo\-Verhaltens und \-Renderings können Sie auch eine neue Klasse von `CMFCToolTipCtrl` ableiten.  Verwenden Sie zum Angeben einer neuen QuickInfo\-Steuerelementklasse die `CTooltipManager::SetTooltipParams`\-Methode:  
  
```  
myApp.GetTooltipManager ()->SetTooltipParams (AFX_TOOLTIP_TYPE_ALL,  
    RUNTIME_CLASS (CMyToolTipCtrl))  
```  
  
 Legen Sie zum Wiederherstellen der standardmäßigen QuickInfo\-Steuerelementklasse und zum Zurücksetzen des QuickInfo\-Formats auf die Standardeinstellung die Laufzeitklasse und die QuickInfo\-Parameter von `SetTooltipParams` auf NULL fest.  
  
```  
theApp.GetTooltipManager ()->SetTooltipParams (AFX_TOOLTIP_TYPE_ALL,  
    NULL, NULL);  
```  
  
## Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie Sie ein `CMFCToolTipCtrl`\-Objekt erstellen, die von der QuickInfo angezeigte Beschreibung und die Breite des Tooltip\-Steuerelements festlegen können.  
  
 [!CODE [NVC_MFC_RibbonApp#41](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_RibbonApp#41)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md)  
  
 [CMFCToolTipCtrl](../../mfc/reference/cmfctooltipctrl-class.md)  
  
## Anforderungen  
 **Header:** afxtooltipctrl.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CToolTipCtrl Class](../../mfc/reference/ctooltipctrl-class.md)   
 [CTooltipManager Class](../../mfc/reference/ctooltipmanager-class.md)   
 [CMFCToolTipInfo Class](../../mfc/reference/cmfctooltipinfo-class.md)   
 [CWinAppEx Class](../../mfc/reference/cwinappex-class.md)
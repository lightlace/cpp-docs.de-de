---
title: "CMFCPropertyGridToolTipCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCPropertyGridToolTipCtrl::PreTranslateMessage"
  - "~CMFCPropertyGridToolTipCtrl"
  - "PreTranslateMessage"
  - "CMFCPropertyGridToolTipCtrl.~CMFCPropertyGridToolTipCtrl"
  - "CMFCPropertyGridToolTipCtrl"
  - "CMFCPropertyGridToolTipCtrl.PreTranslateMessage"
  - "CMFCPropertyGridToolTipCtrl::~CMFCPropertyGridToolTipCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "~CMFCPropertyGridToolTipCtrl destructor"
  - "CMFCPropertyGridToolTipCtrl class"
  - "CMFCPropertyGridToolTipCtrl class, Destruktor"
  - "PreTranslateMessage method"
ms.assetid: 84b436e5-6695-4da0-9569-1a875e087711
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CMFCPropertyGridToolTipCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implementiert ein QuickInfosteuerelement, dem [CMFCPropertyGridCtrl Class](../../mfc/reference/cmfcpropertygridctrl-class.md) verwendet, um QuickInfo anzuzeigen.  
  
## Syntax  
  
```  
class CMFCPropertyGridToolTipCtrl : public CWnd  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|||  
|-|-|  
|Name|Description|  
|[CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl](../Topic/CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl.md)|Erstellt ein `CMFCPropertyGridToolTipCtrl`\-Objekt.|  
|`CMFCPropertyGridToolTipCtrl::~CMFCPropertyGridToolTipCtrl`|Destruktor.|  
  
### Öffentliche Methoden  
  
|||  
|-|-|  
|Name|Description|  
|[CMFCPropertyGridToolTipCtrl::Create](../Topic/CMFCPropertyGridToolTipCtrl::Create.md)|Stellt ein Fenster zum QuickInfosteuerelement erstellt.|  
|[CMFCPropertyGridToolTipCtrl::Deactivate](../Topic/CMFCPropertyGridToolTipCtrl::Deactivate.md)|Deaktiviert und blendet das QuickInfosteuerelement aus.|  
|[CMFCPropertyGridToolTipCtrl::GetLastRect](../Topic/CMFCPropertyGridToolTipCtrl::GetLastRect.md)|Gibt die Koordinaten der letzten Position des QuickInfosteuerelements zurück.|  
|[CMFCPropertyGridToolTipCtrl::Hide](../Topic/CMFCPropertyGridToolTipCtrl::Hide.md)|Blendet das QuickInfosteuerelement aus.|  
|`CMFCPropertyGridToolTipCtrl::PreTranslateMessage`|Wird von Klasse [CWinApp](../../mfc/reference/cwinapp-class.md), um Fenstermeldungen zu übersetzen, bevor sie an den [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) und [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows\-Funktionen weitergeleitet werden.  \(Überschreibungen [CWnd::PreTranslateMessage](../Topic/CWnd::PreTranslateMessage.md).\)|  
|[CMFCPropertyGridToolTipCtrl::SetTextMargin](../Topic/CMFCPropertyGridToolTipCtrl::SetTextMargin.md)|Legt den Abstand zwischen dem QuickInfo\-Text und dem Rahmen des QuickInfofensters fest.|  
|[CMFCPropertyGridToolTipCtrl::Track](../Topic/CMFCPropertyGridToolTipCtrl::Track.md)|Zeigt das QuickInfosteuerelement an.|  
  
## Hinweise  
 QuickInfo werden angezeigt, wenn der Mauszeiger auf einem Eigenschaftennamen gezeigt wird.  Die Klasse erfasst [CMFCPropertyGridToolTipCtrl](../../mfc/reference/cmfcpropertygridtooltipctrl-class.md) eine QuickInfo, dass sie leicht vom Benutzer lesbar ist.  Normalerweise wird die Position eines QuickInfos durch die Position des Zeigers bestimmt.  Mithilfe dieser Klasse verwendet, wird die QuickInfo über dem Eigenschaftennamen und ähnelt der natürlichen Eigenschafterweiterung, damit der Eigenschaftenname vollständig sichtbar ist.  
  
 MFC erstellt automatisch dieses Steuerelement und verwendet sie in [CMFCPropertyGridCtrl Class](../../mfc/reference/cmfcpropertygridctrl-class.md).  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie ein Objekt der Klasse `CMFCPropertyGridToolTipCtrl` erstellt und das QuickInfosteuerelement anzeigt.  
  
 [!CODE [NVC_MFC_RibbonApp#23](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_RibbonApp#23)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCPropertyGridToolTipCtrl](../../mfc/reference/cmfcpropertygridtooltipctrl-class.md)  
  
## Anforderungen  
 **Header:** afxpropertygridtooltipctrl.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)
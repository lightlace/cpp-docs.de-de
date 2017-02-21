---
title: "CMFCCaptionButton Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCCaptionButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCCaptionButton class"
ms.assetid: c5774b38-c0dd-414a-9ede-3b2f78f233ec
caps.latest.revision: 28
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 30
---
# CMFCCaptionButton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `CMFCCaptionButton`\-Klasse implementiert eine Schaltfläche, die in der Titelleiste für einen Hauptandockbereich oder ein Minirahmenfenster angezeigt wird.  In der Regel stellt das Framework Beschriftungsschaltflächen automatisch erstellt.  
  
## Syntax  
  
```  
class CMFCCaptionButton : public CObject  
```  
  
## Mitglieder  
  
### Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCCaptionButton::CMFCCaptionButton](../Topic/CMFCCaptionButton::CMFCCaptionButton.md)|Erstellt ein CMFCCaptionButton\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCCaptionButton::GetHit](../Topic/CMFCCaptionButton::GetHit.md)|Gibt den Befehl zurück, der durch die Schaltfläche dargestellt wird.|  
|[CMFCCaptionButton::GetIconID](../Topic/CMFCCaptionButton::GetIconID.md)|Gibt die Bild ID zurück, die mit der Schaltfläche zugeordnet ist.|  
|[CMFCCaptionButton::GetRect](../Topic/CMFCCaptionButton::GetRect.md)|Gibt das Rechteck zurück, das über die Schaltfläche belegt wird.|  
|[CMFCCaptionButton::GetSize](../Topic/CMFCCaptionButton::GetSize.md)|Gibt die Breite und Höhe der Schaltfläche zurück.|  
|[CMFCCaptionButton::IsMiniFrameButton](../Topic/CMFCCaptionButton::IsMiniFrameButton.md)|Gibt an, ob die zur Höhe zur Minigröße festgelegt ist.|  
|[CMFCCaptionButton::Move](../Topic/CMFCCaptionButton::Move.md)|Legt den Speicherort und Fensteranzeigezustand des Schaltflächenabgehobenen betrages fest.|  
|[CMFCCaptionButton::OnDraw](../Topic/CMFCCaptionButton::OnDraw.md)|Zeichnet die Beschriftungsschaltfläche.|  
|[CMFCCaptionButton::SetMiniFrameButton](../Topic/CMFCCaptionButton::SetMiniFrameButton.md)|Legt die Minigröße der Titelleiste fest.|  
  
## Hinweise  
 Sie können eine Klasse von ableiten und die [CPaneFrameWnd Class](../../mfc/reference/cpaneframewnd-class.md) geschützte Methode, `AddButton` verwenden, um Beschriftungsschaltflächen einem Minirahmenfenster hinzuzufügen.  
  
 CPaneFrameWnd.h definiert Befehl IDs für zwei Typen Beschriftungsschaltflächen:  
  
-   `AFX_CAPTION_BTN_PIN`, das eine Drehfeld anzeigt, wenn der Bereich andockbare Modus "Automatisches Ausblenden" unterstützt.  
  
-   `AFX_CAPTION_BTN_CLOSE`, das eine Schaltfläche **Schließen** angezeigt wird, wenn der Bereich geschlossen oder ausgeblendet werden kann.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie ein `CMFCCaptionButton`\-Objekt erstellt und die Minigröße der Titelleiste festgelegt wird.  
  
 [!CODE [NVC_MFC_RibbonApp#43](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_RibbonApp#43)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCCaptionButton](../../mfc/reference/cmfccaptionbutton-class.md)  
  
## Anforderungen  
 **Header:** afxcaptionbutton.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CPaneFrameWnd Class](../../mfc/reference/cpaneframewnd-class.md)   
 [CDockablePane Class](../../mfc/reference/cdockablepane-class.md)
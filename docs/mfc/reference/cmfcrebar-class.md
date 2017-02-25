---
title: "CMFCReBar Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCReBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCReBar class"
ms.assetid: 02a60e29-6224-49c1-9e74-e0a7d9f8d023
caps.latest.revision: 27
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 29
---
# CMFCReBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ein Objekt `CMFCReBar` ist eine Steuerleiste, die Layout, Persistenz\- und Zustandsinformationen für Infoleistensteuerelemente bereitstellt.  
  
## Syntax  
  
```  
class CMFCReBar : public CPane  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCReBar::AddBar](../Topic/CMFCReBar::AddBar.md)|Fügt ein Band einer Infoleiste hinzu.|  
|[CMFCReBar::CalcFixedLayout](../Topic/CMFCReBar::CalcFixedLayout.md)|\(Überschreibungen [CBasePane::CalcFixedLayout](../Topic/CBasePane::CalcFixedLayout.md).\)|  
|[CMFCReBar::CanFloat](../Topic/CMFCReBar::CanFloat.md)|\(Überschreibungen [CBasePane::CanFloat](../Topic/CBasePane::CanFloat.md).\)|  
|[CMFCReBar::Create](../Topic/CMFCReBar::Create.md)|Erstellt das Grundleistensteuerelement und fügt es dem `CMFCReBar`\-Objekt.|  
|[CMFCReBar::EnableDocking](../Topic/CMFCReBar::EnableDocking.md)|\(Überschreibungen [CBasePane::EnableDocking](../Topic/CBasePane::EnableDocking.md).\)|  
|[CMFCReBar::GetReBarBandInfoSize](../Topic/CMFCReBar::GetReBarBandInfoSize.md)||  
|[CMFCReBar::GetReBarCtrl](../Topic/CMFCReBar::GetReBarCtrl.md)|Stellt direkt auf die zugrunde liegenden [CReBarCtrl](../../mfc/reference/crebarctrl-class.md) allgemeine Steuerelemente bereit.|  
|[CMFCReBar::OnShowControlBarMenu](../Topic/CMFCReBar::OnShowControlBarMenu.md)|\(Überschreibungen [CPane::OnShowControlBarMenu](../Topic/CPane::OnShowControlBarMenu.md).\)|  
|[CMFCReBar::OnToolHitTest](../Topic/CMFCReBar::OnToolHitTest.md)|\(Überschreibungen [CWnd::OnToolHitTest](../Topic/CWnd::OnToolHitTest.md).\)|  
|[CMFCReBar::OnUpdateCmdUI](../Topic/CMFCReBar::OnUpdateCmdUI.md)|\(Überschreibungen [CBasePane::OnUpdateCmdUI](assetId:///e139f06a-9793-4ee2-bc3d-517389368c77).\)|  
|[CMFCReBar::SetPaneAlignment](../Topic/CMFCReBar::SetPaneAlignment.md)|\(Überschreibungen [CBasePane::SetPaneAlignment](../Topic/CBasePane::SetPaneAlignment.md).\)|  
  
## Hinweise  
 Ein Objekt `CMFCReBar` kann eine Vielzahl von untergeordneten Fenstern enthalten.  Dies schließt Eingabefelder, Symbolleisten und Listenfelder ein.  Sie können die Infoleiste programmgesteuert Größe ändern, oder der Benutzer kann die Infoleiste manuell Größe ändern, indem er seine Ziehpunktleiste zieht.  Sie können den Hintergrund eines Infoleistenobjekts in eine Bitmap der Auswahl festlegen.  
  
 Ein Infoleistenobjekt verhält sich wie ein Symbolleistenobjekt.  Ein Grundleistensteuerelement kann eine oder mehrere Bänder enthalten, und jedes Band kann eine Ziehpunktleiste, eine Bitmap, eine Beschriftung und ein untergeordnetes Fenster enthalten.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie verschiedene Methoden in der Klasse `CMFCReBar` verwendet.  Im Beispiel wird gezeigt, wie ein Grundleisten\-Steuerelement erstellt und ein Band ihm hinzugefügt wird.  Die Bandfunktionen als interne Symbolleiste.  Dieser Codeausschnitt ist Teil [Infoleisten\-Prüfling](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_RebarTest#1](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_RebarTest#1)]  
[!CODE [NVC_MFC_RebarTest#2](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_RebarTest#2)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md) [CCmdTarget](../../mfc/reference/ccmdtarget-class.md) [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md) [CPane](../../mfc/reference/cpane-class.md) [CMFCReBar](../../mfc/reference/cmfcrebar-class.md)  
  
## Anforderungen  
 **Header:** afxRebar.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CReBarCtrl Class](../../mfc/reference/crebarctrl-class.md)   
 [CPane Class](../../mfc/reference/cpane-class.md)
---
title: "CMFCDropDownToolBar Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCDropDownToolBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCDropDownToolBar class"
ms.assetid: 78818ec5-83ce-42fa-a0d4-2d9d5ecc8770
caps.latest.revision: 37
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 39
---
# CMFCDropDownToolBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine Symbolleiste, die angezeigt wird, wenn der Benutzer eine Symbolleisten\-Schaltfläche der obersten Ebene drückt und enthält.  
  
## Syntax  
  
```  
class CMFCDropDownToolBar : public CMFCToolBar  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCDropDownToolBar::AllowShowOnPaneMenu](../Topic/CMFCDropDownToolBar::AllowShowOnPaneMenu.md)|\(Überschreibungen `CPane::AllowShowOnPaneMenu`.\)|  
|[CMFCDropDownToolBar::LoadBitmap](../Topic/CMFCDropDownToolBar::LoadBitmap.md)|\(Überschreibungen [CMFCToolBar::LoadBitmap](../Topic/CMFCToolBar::LoadBitmap.md).\)|  
|[CMFCDropDownToolBar::LoadToolBar](../Topic/CMFCDropDownToolBar::LoadToolBar.md)|\(Überschreibungen [CMFCToolBar::LoadToolBar](../Topic/CMFCToolBar::LoadToolBar.md).\)|  
|[CMFCDropDownToolBar::OnLButtonUp](../Topic/CMFCDropDownToolBar::OnLButtonUp.md)||  
|[CMFCDropDownToolBar::OnMouseMove](../Topic/CMFCDropDownToolBar::OnMouseMove.md)||  
|[CMFCDropDownToolBar::OnSendCommand](../Topic/CMFCDropDownToolBar::OnSendCommand.md)|\(Überschreibungen `CMFCToolBar::OnSendCommand`.\)|  
|[CMFCDropDownToolBar::OnUpdateCmdUI](../Topic/CMFCDropDownToolBar::OnUpdateCmdUI.md)|\(Überschreibungen [CMFCToolBar::OnUpdateCmdUI](assetId:///571a38ab-2a56-4968-9796-273516126f80).\)|  
  
### Hinweise  
 Ein Objekt `CMFCDropDownToolBar` kombiniert das Aussehen einer Symbolleiste mit dem Verhalten eines Popupmenüs.  Wenn ein Benutzer und Threads eine Dropdown\-Symbolleistenschaltfläche \(siehe\), [CMFCDropDownToolbarButton Class](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md) drückt, wird eine Dropdown\-Symbolleiste, und der Benutzer kann eine Schaltfläche von der Dropdown\-Symbolleiste auswählen, indem er darauf bewegt werden und die Maustaste loslässt.  Nachdem der Benutzer eine Schaltfläche in der Dropdown\-Symbolleiste auswählt, wird diese Schaltfläche als die aktuelle Schaltfläche auf der Symbolleiste der obersten Ebene angezeigt.  
  
 Eine Dropdown\-Symbolleiste kann nicht angepasst werden oder angedockt werden, und weist keinen Tearoffen Zustand.  
  
 Die folgende Abbildung zeigt ein `CMFCDropDownToolBar`\-Objekt:  
  
 ![Beispiel für CMFCDropDownToolbar](../../mfc/reference/media/cmfcdropdown.png "CMFCDropDown")  
  
 Sie erstellen ein `CMFCDropDownToolBar`\-Objekt auf die gleiche Weise, wie Sie eine gewöhnliche Symbolleiste erstellen \(siehe [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md)\).  
  
 Um die Dropdown\-Symbolleiste in eine Symbolleiste Elemente einfügen:  
  
 1.  Reservieren Sie ein blindes Ressourcen\-ID für die Schaltfläche in der übergeordneten Symbolleistenressource.  
  
 2.  Erstellen Sie ein `CMFCDropDownToolBarButton`\-Objekt, das die Dropdown\-Symbolleiste enthält \(weitere Informationen finden Sie unter, [CMFCDropDownToolbarButton::CMFCDropDownToolbarButton](../Topic/CMFCDropDownToolbarButton::CMFCDropDownToolbarButton.md)\).  
  
 3.  Ersetzen Sie die blinde Schaltfläche durch `CMFCDropDownToolBarButton`\-Objekt, indem Sie [CMFCToolBar::ReplaceButton](../Topic/CMFCToolBar::ReplaceButton.md) verwenden.  
  
 Weitere Informationen zu Symbolleisten\-Schaltflächen, finden Sie unter [Exemplarische Vorgehensweise: Steuerelemente in eine Symbolleiste einfügen](../../mfc/walkthrough-putting-controls-on-toolbars.md).  Ein Beispiel einer Dropdown\-Symbolleiste, finden Sie das Beispielprojekt VisualStudioDemo.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie die `Create`\-Methode in der Klasse `CMFCDropDownToolBar` verwendet.  Dieser Codeausschnitt ist Teil [Visual Studio\-Demobeispiel](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_VisualStudioDemo#29](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_VisualStudioDemo#29)]  
[!CODE [NVC_MFC_VisualStudioDemo#30](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_VisualStudioDemo#30)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 [CMFCDropDownToolBar](../../mfc/reference/cmfcdropdowntoolbar-class.md)  
  
## Anforderungen  
 **Header:** afxdropdowntoolbar.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBar::Create](../Topic/CMFCToolBar::Create.md)   
 [CMFCToolBar::ReplaceButton](../Topic/CMFCToolBar::ReplaceButton.md)   
 [CMFCDropDownToolbarButton Class](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)   
 [Exemplarische Vorgehensweise: Steuerelemente in eine Symbolleiste einfügen](../../mfc/walkthrough-putting-controls-on-toolbars.md)
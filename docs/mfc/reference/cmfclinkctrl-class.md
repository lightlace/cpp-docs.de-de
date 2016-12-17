---
title: "CMFCLinkCtrl Class"
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
  - "CMFCLinkCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCLinkCtrl class"
ms.assetid: 80f3874d-7cc8-410e-9ff1-62a225f5034b
caps.latest.revision: 27
caps.handback.revision: "15"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCLinkCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Klasse erfasst `CMFCLinkCtrl` eine Schaltfläche als Link und ruft das Ziel des Links, wenn auf die Schaltfläche geklickt wird.  
  
## Syntax  
  
```  
class CMFCLinkCtrl : public CMFCButton  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCLinkCtrl::SetURL](../Topic/CMFCLinkCtrl::SetURL.md)|Zeigt ein angegebenes URL wie der Anmeldung an.|  
|[CMFCLinkCtrl::SetURLPrefix](../Topic/CMFCLinkCtrl::SetURLPrefix.md)|Legt das implizite Protokoll fest \(beispielsweise, "http: "\) des URL.|  
|[CMFCLinkCtrl::SizeToContent](../Topic/CMFCLinkCtrl::SizeToContent.md)|Ändert die Größe der Schaltfläche, um den Schaltflächentext oder \-Bitmap zu enthalten.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCLinkCtrl::OnDrawFocusRect](../Topic/CMFCLinkCtrl::OnDrawFocusRect.md)|Aufgerufen vom Framework vor dem Fokusrechteck auf der Schaltfläche wird gezeichnet.|  
  
## Hinweise  
 Wenn Sie auf eine Schaltfläche klicken, die von der `CMFCLinkCtrl`\-Klasse abgeleitet wird, führt das Framework die URL der Schaltfläche als Parameter an die Methode `ShellExecute`.  Anschließend wird die `ShellExecute`\-Methode das Ziel der URL.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie die Größe eines Objekts festgelegt `CMFCLinkCtrl` und wie eine URL und eine QuickInfo in einem `CMFCLinkCtrl`\-Objekt festgelegt wird.  Dieses Beispiel ist Teil [Neue Kontrollprobe](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_NewControls#9](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_NewControls#9)]  
[!CODE [NVC_MFC_NewControls#10](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_NewControls#10)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCButton](../../mfc/reference/cmfcbutton-class.md)  
  
 [CMFCLinkCtrl](../../mfc/reference/cmfclinkctrl-class.md)  
  
## Anforderungen  
 **Header:** afxlinkctrl.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CLinkCtrl Class](../../mfc/reference/clinkctrl-class.md)   
 [CMFCButton Class](../../mfc/reference/cmfcbutton-class.md)
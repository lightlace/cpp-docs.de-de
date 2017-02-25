---
title: "CHtmlEditView Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CHtmlEditView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHtmlEditView class"
ms.assetid: 166c8ba8-3fb5-4dd7-a9ea-5bca662d00f6
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CHtmlEditView Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt die Funktionalität der ActiveX\-Steuerelement browserbearbeitungsplattform im Kontext Dokument\-\/Ansichtarchitektur MFC bereit.  
  
## Syntax  
  
```  
  
class CHtmlEditView : public CHtmlView, public CHtmlEditCtrlBase< CHtmlEditView >  
  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CHtmlEditView::CHtmlEditView](../Topic/CHtmlEditView::CHtmlEditView.md)|Erstellt ein `CHtmlEditView`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CHtmlEditView::Create](../Topic/CHtmlEditView::Create.md)|Erstellt ein neues Fensterobjekt.|  
|[CHtmlEditView::GetDHtmlDocument](../Topic/CHtmlEditView::GetDHtmlDocument.md)|Gibt die **IHTMLDocument2**\-Schnittstelle im aktuellen Dokument zurück.|  
|[CHtmlEditView::GetStartDocument](../Topic/CHtmlEditView::GetStartDocument.md)|Ruft den Namen des standardmäßigen Dokuments für diese Ansicht ab.|  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 [CFormView](../../mfc/reference/cformview-class.md)  
  
 [CHtmlEditCtrlBase](../../mfc/reference/chtmleditctrlbase-class.md)  
  
 [CHtmlView](../../mfc/reference/chtmlview-class.md)  
  
 `CHtmlEditView`  
  
## Anforderungen  
 **Header:** afxhtml.h  
  
## Siehe auch  
 [HTMLEdit\-Beispiel](../../top/visual-cpp-samples.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)
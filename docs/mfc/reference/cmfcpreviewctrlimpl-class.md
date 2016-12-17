---
title: "CMFCPreviewCtrlImpl Class"
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
  - "CMFCPreviewCtrlImpl"
  - "afxwin/CMFCPreviewCtrlImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCPreviewCtrlImpl class"
ms.assetid: 06257fa0-54c9-478d-9d68-c9698c3f93ed
caps.latest.revision: 28
caps.handback.revision: "16"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCPreviewCtrlImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse implementiert ein Fenster, das auf ein Hostfenster platziert wird, das von der Shell für Reich\-Vorschau bereitgestellt wird.  
  
## Syntax  
  
```  
class CMFCPreviewCtrlImpl : public CWnd;  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCPreviewCtrlImpl::~CMFCPreviewCtrlImpl](../Topic/CMFCPreviewCtrlImpl::~CMFCPreviewCtrlImpl.md)|Zerstört ein Vorschausteuerobjekt.|  
|[CMFCPreviewCtrlImpl::CMFCPreviewCtrlImpl](../Topic/CMFCPreviewCtrlImpl::CMFCPreviewCtrlImpl.md)|Erstellt ein Vorschausteuerobjekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCPreviewCtrlImpl::Create](../Topic/CMFCPreviewCtrlImpl::Create.md)|Überladen.  Aufgerufen durch einen umfangreichen Vorschauhandler, um das Windows\-Fenster zu erstellen.|  
|[CMFCPreviewCtrlImpl::Destroy](../Topic/CMFCPreviewCtrlImpl::Destroy.md)|Aufgerufen durch einen umfangreichen Vorschauhandler, wenn dieses Steuerelement zerstören muss.|  
|[CMFCPreviewCtrlImpl::Focus](../Topic/CMFCPreviewCtrlImpl::Focus.md)|Legt den Eingabefokus auf dieses Steuerelement fest.|  
|[CMFCPreviewCtrlImpl::GetDocument](../Topic/CMFCPreviewCtrlImpl::GetDocument.md)|Gibt ein Dokument zurück, das an dieses Vorschausteuerelement verbunden ist.|  
|[CMFCPreviewCtrlImpl::Redraw](../Topic/CMFCPreviewCtrlImpl::Redraw.md)|Teilt dieses Steuerelement mit, neu zu entwerfen.|  
|[CMFCPreviewCtrlImpl::SetDocument](../Topic/CMFCPreviewCtrlImpl::SetDocument.md)|Aufgerufen durch den Vorschauhandler, um eine Beziehung zwischen der Dokumentenimplementierung und dem Vorschausteuerelement zu erstellen.|  
|[CMFCPreviewCtrlImpl::SetHost](../Topic/CMFCPreviewCtrlImpl::SetHost.md)|Legt ein neues übergeordnetes Element für dieses Steuerelement fest.|  
|[CMFCPreviewCtrlImpl::SetPreviewVisuals](../Topic/CMFCPreviewCtrlImpl::SetPreviewVisuals.md)|Aufgerufen durch einen umfangreichen Vorschauhandler, wenn grafische Elemente des Reichvorschauinhalts festlegen muss.|  
|[CMFCPreviewCtrlImpl::SetRect](../Topic/CMFCPreviewCtrlImpl::SetRect.md)|Legt ein neues umschließendes Rechteck für dieses Steuerelement fest.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCPreviewCtrlImpl::DoPaint](../Topic/CMFCPreviewCtrlImpl::DoPaint.md)|Aufgerufen vom Framework, um die Vorschau zu rendern.|  
  
### Geschützte Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCPreviewCtrlImpl::m\_clrBackColor](../Topic/CMFCPreviewCtrlImpl::m_clrBackColor.md)|Hintergrundfarbe des Vorschaufensters.|  
|[CMFCPreviewCtrlImpl::m\_clrTextColor](../Topic/CMFCPreviewCtrlImpl::m_clrTextColor.md)|Textfarbe des Vorschaufensters.|  
|[CMFCPreviewCtrlImpl::m\_font](../Topic/CMFCPreviewCtrlImpl::m_font.md)|Schriftart verwendet, um Text im Vorschaufenster anzuzeigen.|  
|[CMFCPreviewCtrlImpl::m\_pDocument](../Topic/CMFCPreviewCtrlImpl::m_pDocument.md)|Ein Zeiger auf ein Dokument, dessen Inhalt im \- Steuerelement in der Vorschau angezeigt wird.|  
  
## Hinweise  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCPreviewCtrlImpl](../../mfc/reference/cmfcpreviewctrlimpl-class.md)  
  
## Anforderungen  
 **Header:** afxwin.h
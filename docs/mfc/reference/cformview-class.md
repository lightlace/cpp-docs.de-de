---
title: "CFormView Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CFormView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFormView class"
  - "form views"
  - "Ansichten, containing controls"
ms.assetid: a99ec313-36f0-4f28-9d2b-de11de14ac19
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CFormView Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die für Formularansichten verwendete Basisklasse.  
  
## Syntax  
  
```  
class CFormView : public CScrollView  
```  
  
## Mitglieder  
  
### Geschützte Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CFormView::CFormView](../Topic/CFormView::CFormView.md)|Erstellt ein `CFormView`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CFormView::IsInitDlgCompleted](../Topic/CFormView::IsInitDlgCompleted.md)|Wird für die Synchronisierung während der Initialisierung verwendet.|  
  
## Hinweise  
 Eine Formularansicht ist im Wesentlichen eine Ansicht, die Steuerelemente enthält.  Diese Steuerelemente werden basierend auf einer Dialogfeldvorlagenressource angeordnet.  Verwenden Sie `CFormView`, wenn Sie Formulare in der Anwendung verwenden möchten.  Diese Ansichten unterstützen bei Bedarf mithilfe der [CScrollView](../../mfc/reference/cscrollview-class.md)\-Funktionalität den Bildlauf.  
  
 Beim [Erstellen einer formularbasierten Anwendung](../../mfc/reference/creating-a-forms-based-mfc-application.md) können Sie ihre Ansichtsklasse auf `CFormView` basieren, wodurch sie zu einer formularbasierten Anwendung wird.  
  
 Sie können auch neue [Formularthemen](../../mfc/form-views-mfc.md) in dokumentansichtbasierten Anwendungen einfügen.  Auch wenn die Anwendung ursprünglich keine Formulare unterstützte, fügt Visual C\+\+ diese Unterstützung hinzu, wenn Sie ein neues Formular einfügen.  
  
 Der MFC\-Anwendungs\-Assistent und der Befehl "Klasse hinzufügen" sind die bevorzugten Methoden zum Erstellen formularbasierter Anwendungen.  Informationen zum Erstellen einer formularbasierten Anwendung ohne Verwendung einer dieser Methoden finden Sie unter [Erstellen einer formularbasierten Anwendung](../../mfc/reference/creating-a-forms-based-mfc-application.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 `CFormView`  
  
## Anforderungen  
 **Header:** afxext.h  
  
## Siehe auch  
 [MFC\-Beispiel SNAPVW](../../top/visual-cpp-samples.md)   
 [MFC\-Beispiel VIEWEX](../../top/visual-cpp-samples.md)   
 [CScrollView Class](../../mfc/reference/cscrollview-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDialog Class](../../mfc/reference/cdialog-class.md)   
 [CScrollView Class](../../mfc/reference/cscrollview-class.md)   
 [CView::OnUpdate](../Topic/CView::OnUpdate.md)   
 [CView::OnInitialUpdate](../Topic/CView::OnInitialUpdate.md)   
 [CView::OnPrint](../Topic/CView::OnPrint.md)   
 [CWnd::UpdateData](../Topic/CWnd::UpdateData.md)   
 [CScrollView::ResizeParentToFit](../Topic/CScrollView::ResizeParentToFit.md)
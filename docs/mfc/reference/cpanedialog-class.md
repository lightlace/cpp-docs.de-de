---
title: "CPaneDialog Class"
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
  - "CPaneDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPaneDialog class"
  - "CPaneDialog constructor"
  - "CPaneDialog::CreateObject method"
  - "CPaneDialog::OnEraseBkgnd method"
  - "CPaneDialog::OnLButtonDblClk method"
  - "CPaneDialog::OnLButtonDown method"
  - "CPaneDialog::OnUpdateCmdUI method"
  - "CPaneDialog::OnWindowPosChanging method"
ms.assetid: 48a6bb91-4b92-40f5-8907-b3270b146cf6
caps.latest.revision: 27
caps.handback.revision: "17"
ms.author: "mblome"
manager: "ghogen"
---
# CPaneDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `CPaneDialog`\-Klasse unterstützt ein nicht modales Dialogfeld, andockbares.  
  
## Syntax  
  
```  
class CPaneDialog : public CDockablePane  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|`CPaneDialog::CPaneDialog`|Standardkonstruktor.|  
|`CPaneDialog::~CPaneDialog`|Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CPaneDialog::Create](../Topic/CPaneDialog::Create.md)|Stellt ein andockbares Dialogfeld erstellt und am `CPaneDialog` einem Objekt an.|  
|`CPaneDialog::CreateObject`|Wird vom Framework, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|`CPaneDialog::GetThisClass`|Wird vom Framework, um ein Zeiger auf [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)\-Objekt abzurufen, das diesem Klassentyp zugeordnet ist.|  
|[CPaneDialog::HandleInitDialog](../Topic/CPaneDialog::HandleInitDialog.md)|Bearbeitet die [WM\_INITDIALOG](http://msdn.microsoft.com/library/windows/desktop/ms645428) Meldung.  \(Definiert `CBasePane::HandleInitDialog` neu.\)|  
|`CPaneDialog::OnEraseBkgnd`|Bearbeiten [WM\_ERASEBKGND](http://msdn.microsoft.com/library/windows/desktop/ms648055) die Meldung.  \(Definiert [CWnd::OnEraseBkgnd](../Topic/CWnd::OnEraseBkgnd.md) neu.\)|  
|`CPaneDialog::OnLButtonDblClk`|Bearbeiten [WM\_LBUTTONDBLCLK](http://msdn.microsoft.com/library/windows/desktop/ms645606) die Meldung.  \(Definiert [CWnd::OnLButtonDblClk](../Topic/CWnd::OnLButtonDblClk.md) neu.\)|  
|`CPaneDialog::OnLButtonDown`|Bearbeiten [WM\_LBUTTONDOWN](http://msdn.microsoft.com/library/windows/desktop/ms645607) die Meldung.  \(Definiert [CWnd::OnLButtonDown](../Topic/CWnd::OnLButtonDown.md) neu.\)|  
|`CPaneDialog::OnUpdateCmdUI`|Aufgerufen vom Framework, um das Dialogfeldfenster zu aktualisieren.  \(Überschreibungen [CDockablePane::OnUpdateCmdUI](assetId:///5dd61606-1c12-40d4-b024-f3839aa5e2e0).\)|  
|`CPaneDialog::OnWindowPosChanging`|Bearbeitet die [WM\_WINDOWPOSCHANGING](http://msdn.microsoft.com/library/windows/desktop/ms632653) Meldung.  \(Definiert [CWnd::OnWindowPosChanging](../Topic/CWnd::OnWindowPosChanging.md) neu.\)|  
|[CPaneDialog::SetOccDialogInfo](../Topic/CPaneDialog::SetOccDialogInfo.md)|Gibt die Vorlage für ein Dialogfeld an, das ein OLE\-Steuerelement\-Container ist.|  
  
## Hinweise  
 Erstellen Sie ein `CPaneDialog`\-Objekt in zwei Schritten.  Erstellen Sie zuerst das Objekt im Code.  Zweitens Aufruf [CPaneDialog::Create](../Topic/CPaneDialog::Create.md).  Sie müssen eine gültige Ressourcenvorlagenname oder Vorlage ID angeben und einen Zeiger auf das übergeordnete Fenster übergeben.  Andernfalls schlägt der Erstellungsprozess aus.  Im Dialogfeld muss das WS\_CHILD\- und WS\_VISIBLE\-Format angeben.  Es wird empfohlen, dass Sie auch die WS\_CLIPCHILDREN\- und WS\_CLIPSIBLINGS\-Formate angeben.  Weitere Informationen finden Sie unter [Fensterstile](../../mfc/reference/window-styles.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
 [CPaneDialog](../../mfc/reference/cpanedialog-class.md)  
  
## Anforderungen  
 **Header:** afxpanedialog.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CDockablePane Class](../../mfc/reference/cdockablepane-class.md)   
 [Fensterstile](../../mfc/reference/window-styles.md)
---
title: "COleBusyDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleBusyDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleBusyDialog class"
  - "Server Busy dialog box"
  - "Server Not Responding dialog box"
ms.assetid: c881a532-9672-4c41-b51b-5ce4a7246a6b
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# COleBusyDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wird für den OLE\-Server ausgelastete nicht Dialogfelder der Reaktion oder des Servers.  
  
## Syntax  
  
```  
class COleBusyDialog : public COleDialog  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[COleBusyDialog::COleBusyDialog](../Topic/COleBusyDialog::COleBusyDialog.md)|Erstellt ein `COleBusyDialog`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[COleBusyDialog::DoModal](../Topic/COleBusyDialog::DoModal.md)|Zeigt das ausgelastete Dialogfeld OLE\-Servers an.|  
|[COleBusyDialog::GetSelectionType](../Topic/COleBusyDialog::GetSelectionType.md)|Bestimmt die Auswahl, die im Dialogfeld erfüllt ist.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[COleBusyDialog::m\_bz](../Topic/COleBusyDialog::m_bz.md)|Struktur des Typs **OLEUIBUSY**, der das Verhalten des Dialogfelds steuert.|  
  
## Hinweise  
 Erstellen Sie ein Objekt der Klasse `COleBusyDialog`, wenn Sie diese Dialogfelder aufrufen möchten.  Nachdem ein `COleBusyDialog`\-Objekt erstellt wurde, können Sie die [m\_bz](../Topic/COleBusyDialog::m_bz.md)\-Struktur verwenden, um die Werte oder die Zustände von Steuerelementen im Dialogfeld zu initialisieren.  Die `m_bz`\-Struktur ist vom Typ **OLEUIBUSY**.  Weitere Informationen über die Verwendung dieser Dialogklasse, finden Sie die [DoModal](../Topic/COleBusyDialog::DoModal.md)\-Memberfunktion.  
  
> [!NOTE]
>  Wird vom Assistenten erstellter Containercode der Anwendung diese Klasse.  
  
 Weitere Informationen finden Sie unter [OLEUIBUSY](http://msdn.microsoft.com/library/windows/desktop/ms682493) die Struktur in [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Weitere Informationen zu OLE\-Besondere Dialogfelder, finden Sie im Artikel [Dialogfelder in OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog\-Klasse](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleBusyDialog`  
  
## Anforderungen  
 **Header:**  afxodlgs.h  
  
## Siehe auch  
 [COleDialog Class](../../mfc/reference/coledialog-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleDialog Class](../../mfc/reference/coledialog-class.md)
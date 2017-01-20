---
title: "COleLinksDialog Class"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "COleLinksDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleLinksDialog class"
  - "Dialogfelder, OLE"
  - "Edit Links dialog box"
  - "OLE Edit Links dialog box"
ms.assetid: fb2eb638-2809-46db-ac74-392a732affc7
caps.latest.revision: 22
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# COleLinksDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wird zum Linkdialogfeld OLE Bearbeiten.  
  
## Syntax  
  
```  
class COleLinksDialog : public COleDialog  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[COleLinksDialog::COleLinksDialog](../Topic/COleLinksDialog::COleLinksDialog.md)|Erstellt ein `COleLinksDialog`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[COleLinksDialog::DoModal](../Topic/COleLinksDialog::DoModal.md)|Zeigt das Linkdialogfeld OLE Bearbeiten an.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[COleLinksDialog::m\_el](../Topic/COleLinksDialog::m_el.md)|Eine Struktur des Typs **OLEUIEDITLINKS**, der das Verhalten des Dialogfelds steuert.|  
  
## Hinweise  
 Erstellen Sie ein Objekt der Klasse `COleLinksDialog`, wenn Sie dieses Dialogfeld aufrufen möchten.  Nachdem ein `COleLinksDialog`\-Objekt erstellt wurde, können Sie die [m\_el](../Topic/COleLinksDialog::m_el.md)\-Struktur verwenden, um die Werte oder die Zustände von Steuerelementen im Dialogfeld zu initialisieren.  Die `m_el`\-Struktur ist vom Typ **OLEUIEDITLINKS**.  Weitere Informationen über die Verwendung dieser Dialogklasse, finden Sie die [DoModal](../Topic/COleLinksDialog::DoModal.md)\-Memberfunktion.  
  
> [!NOTE]
>  Wird vom Assistenten erstellter Containercode der Anwendung diese Klasse.  
  
 Weitere Informationen finden Sie unter [OLEUIEDITLINKS](http://msdn.microsoft.com/library/windows/desktop/ms678492) die Struktur in [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Weitere Informationen zu OLE\-Besondere Dialogfelder, finden Sie im Artikel [Dialogfelder in OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog\-Klasse](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleLinksDialog`  
  
## Anforderungen  
 **Header:**  afxodlgs.h  
  
## Siehe auch  
 [COleDialog Class](../../mfc/reference/coledialog-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleDialog Class](../../mfc/reference/coledialog-class.md)
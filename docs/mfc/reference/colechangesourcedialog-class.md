---
title: "COleChangeSourceDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleChangeSourceDialog"
  - "OLEUICHANGESOURCE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleChangeSourceDialog class"
  - "Dialogfelder, OLE"
  - "OLE Change Source dialog box"
  - "OLE-Dialogfelder, Change Source"
  - "OleUIChangeSource structure"
ms.assetid: d0e08be7-21ef-45e1-97af-fe27d99e3bac
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# COleChangeSourceDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wird zum OLE\-Änderungs\-Quelldialogfeld.  
  
## Syntax  
  
```  
class COleChangeSourceDialog : public COleDialog  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[COleChangeSourceDialog::COleChangeSourceDialog](../Topic/COleChangeSourceDialog::COleChangeSourceDialog.md)|Erstellt ein `COleChangeSourceDialog`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[COleChangeSourceDialog::DoModal](../Topic/COleChangeSourceDialog::DoModal.md)|Zeigt das OLE\-Änderungs\-Quelldialogfeld an.|  
|[COleChangeSourceDialog::GetDisplayName](../Topic/COleChangeSourceDialog::GetDisplayName.md)|Ruft den vollständigen Quellanzeigenamen ab.|  
|[COleChangeSourceDialog::GetFileName](../Topic/COleChangeSourceDialog::GetFileName.md)|Ruft den Dateinamen vom Quellennamen ab.|  
|[COleChangeSourceDialog::GetFromPrefix](../Topic/COleChangeSourceDialog::GetFromPrefix.md)|Ruft das Präfix der vorherigen Quelle ab.|  
|[COleChangeSourceDialog::GetItemName](../Topic/COleChangeSourceDialog::GetItemName.md)|Ruft den Elementnamen aus dem Quellennamen ab.|  
|[COleChangeSourceDialog::GetToPrefix](../Topic/COleChangeSourceDialog::GetToPrefix.md)|Ruft das Präfix der neuen Quelle ab|  
|[COleChangeSourceDialog::IsValidSource](../Topic/COleChangeSourceDialog::IsValidSource.md)|Gibt an, ob die Quelle gültig ist.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[COleChangeSourceDialog::m\_cs](../Topic/COleChangeSourceDialog::m_cs.md)|Eine Struktur, die das Verhalten des Dialogfelds steuert.|  
  
## Hinweise  
 Erstellen Sie ein Objekt der Klasse `COleChangeSourceDialog`, wenn Sie dieses Dialogfeld aufrufen möchten.  Nachdem ein `COleChangeSourceDialog`\-Objekt erstellt wurde, können Sie die [m\_cs](../Topic/COleChangeSourceDialog::m_cs.md)\-Struktur verwenden, um die Werte oder die Zustände von Steuerelementen im Dialogfeld zu initialisieren.  Die `m_cs`\-Struktur ist vom Typ [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160).  Weitere Informationen über die Verwendung dieser Dialogklasse, finden Sie die [DoModal](../Topic/COleChangeSourceDialog::DoModal.md)\-Memberfunktion.  
  
 Weitere Informationen finden Sie unter [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) die Struktur in [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Weitere Informationen zu OLE\-Besondere Dialogfelder, finden Sie im Artikel [Dialogfelder in OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog\-Klasse](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleChangeSourceDialog`  
  
## Anforderungen  
 **Header:**  afxodlgs.h  
  
## Siehe auch  
 [COleDialog Class](../../mfc/reference/coledialog-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleDialog Class](../../mfc/reference/coledialog-class.md)
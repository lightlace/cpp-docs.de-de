---
title: "COleChangeIconDialog Class"
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
  - "COleChangeIconDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Change Icon dialog box"
  - "COleChangeIconDialog class"
  - "Dialogfelder, OLE"
  - "OLE Change Icon dialog box"
  - "OLE-Dialogfelder, Change Icon"
ms.assetid: 8d6e131b-ddbb-4dff-a432-f239efda8e3d
caps.latest.revision: 22
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# COleChangeIconDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wird zum OLE\-Änderungs\-Symboldialogfeld.  
  
## Syntax  
  
```  
class COleChangeIconDialog : public COleDialog  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[COleChangeIconDialog::COleChangeIconDialog](../Topic/COleChangeIconDialog::COleChangeIconDialog.md)|Erstellt ein `COleChangeIconDialog`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[COleChangeIconDialog::DoChangeIcon](../Topic/COleChangeIconDialog::DoChangeIcon.md)|Führt die Änderung aus, die im Dialogfeld angegeben wird.|  
|[COleChangeIconDialog::DoModal](../Topic/COleChangeIconDialog::DoModal.md)|Zeigt das OLE 2\-Dialogfeld "Symbol ändern" an.|  
|[COleChangeIconDialog::GetIconicMetafile](../Topic/COleChangeIconDialog::GetIconicMetafile.md)|Ruft ein Handle an die Metadatei, die mit dem ikonenhaften Formular dieses Elements zugeordnet ist.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[COleChangeIconDialog::m\_ci](../Topic/COleChangeIconDialog::m_ci.md)|Eine Struktur, die das Verhalten des Dialogfelds steuert.|  
  
## Hinweise  
 Erstellen Sie ein Objekt der Klasse `COleChangeIconDialog`, wenn Sie dieses Dialogfeld aufrufen möchten.  Nachdem ein `COleChangeIconDialog`\-Objekt erstellt wurde, können Sie die [m\_ci](../Topic/COleChangeIconDialog::m_ci.md)\-Struktur verwenden, um die Werte oder die Zustände von Steuerelementen im Dialogfeld zu initialisieren.  Die `m_ci`\-Struktur ist vom Typ **OLEUICHANGEICON**.  Weitere Informationen über die Verwendung dieser Dialogklasse, finden Sie die [DoModal](../Topic/COleChangeIconDialog::DoModal.md)\-Memberfunktion.  
  
 Weitere Informationen finden Sie unter [OLEUICHANGEICON](http://msdn.microsoft.com/library/windows/desktop/ms680098) die Struktur in [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Weitere Informationen zu OLE\-Besondere Dialogfelder, finden Sie im Artikel [Dialogfelder in OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog\-Klasse](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleChangeIconDialog`  
  
## Anforderungen  
 **Header:**  afxodlgs.h  
  
## Siehe auch  
 [COleDialog Class](../../mfc/reference/coledialog-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleDialog Class](../../mfc/reference/coledialog-class.md)
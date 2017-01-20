---
title: "COleInsertDialog Class"
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
  - "COleInsertDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleInsertDialog class"
  - "Dialogfelder, OLE"
  - "Insert Object dialog box"
  - "OLE Insert Object dialog box"
ms.assetid: a9ec610b-abde-431e-bd01-c40159a66dbb
caps.latest.revision: 24
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# COleInsertDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wird zum Objektdialogfeld OLE INSERT.  
  
## Syntax  
  
```  
class COleInsertDialog : public COleDialog  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[COleInsertDialog::COleInsertDialog](../Topic/COleInsertDialog::COleInsertDialog.md)|Erstellt ein `COleInsertDialog`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[COleInsertDialog::CreateItem](../Topic/COleInsertDialog::CreateItem.md)|Erstellt das Element, das im Dialogfeld aktiviert ist.|  
|[COleInsertDialog::DoModal](../Topic/COleInsertDialog::DoModal.md)|Zeigt das Objektdialogfeld OLE INSERT an.|  
|[COleInsertDialog::GetClassID](../Topic/COleInsertDialog::GetClassID.md)|Ruft **CLSID** ab, das dem ausgewählten Element zugeordnet ist.|  
|[COleInsertDialog::GetDrawAspect](../Topic/COleInsertDialog::GetDrawAspect.md)|Teilt mit, ob das Element als Symbol zeichnet.|  
|[COleInsertDialog::GetIconicMetafile](../Topic/COleInsertDialog::GetIconicMetafile.md)|Ruft ein Handle an die Metadatei, die mit dem ikonenhaften Formular dieses Elements zugeordnet ist.|  
|[COleInsertDialog::GetPathName](../Topic/COleInsertDialog::GetPathName.md)|Ruft den vollständigen Pfad der Datei, die im Dialogfeld ausgewählt ist.|  
|[COleInsertDialog::GetSelectionType](../Topic/COleInsertDialog::GetSelectionType.md)|Ruft den Typ des Objekts ausgewählt ab.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[COleInsertDialog::m\_io](../Topic/COleInsertDialog::m_io.md)|Eine Struktur des Typs **OLEUIINSERTOBJECT**, der das Verhalten des Dialogfelds steuert.|  
  
## Hinweise  
 Erstellen Sie ein Objekt der Klasse `COleInsertDialog`, wenn Sie dieses Dialogfeld aufrufen möchten.  Nachdem ein `COleInsertDialog`\-Objekt erstellt wurde, können Sie die [m\_io](../Topic/COleInsertDialog::m_io.md)\-Struktur verwenden, um die Werte oder die Zustände von Steuerelementen im Dialogfeld zu initialisieren.  Die `m_io`\-Struktur ist vom Typ **OLEUIINSERTOBJECT**.  Weitere Informationen über die Verwendung dieser Dialogklasse, finden Sie die [DoModal](../Topic/COleInsertDialog::DoModal.md)\-Memberfunktion.  
  
> [!NOTE]
>  Wird vom Assistenten erstellter Containercode der Anwendung diese Klasse.  
  
 Weitere Informationen finden Sie unter [OLEUIINSERTOBJECT](http://msdn.microsoft.com/library/windows/desktop/ms691316) die Struktur in [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Weitere Informationen zu OLE\-Besondere Dialogfelder, finden Sie im Artikel [Dialogfelder in OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog\-Klasse](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleInsertDialog`  
  
## Anforderungen  
 **Header:**  afxodlgs.h  
  
## Siehe auch  
 [MFC\-Beispiel OCLIENT](../../top/visual-cpp-samples.md)   
 [COleDialog Class](../../mfc/reference/coledialog-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleDialog Class](../../mfc/reference/coledialog-class.md)
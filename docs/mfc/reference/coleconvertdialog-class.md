---
title: "COleConvertDialog Class"
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
  - "COleConvertDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleConvertDialog class"
  - "Konvertieren (Dialogfeld)"
  - "Dialogfelder, OLE"
  - "OLE Convert dialog box"
  - "OLE-Dialogfelder, Convert"
ms.assetid: a7c57714-31e8-4b78-834d-8ddd1b856a1c
caps.latest.revision: 22
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# COleConvertDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Weitere Informationen finden Sie unter [OLEUICONVERT](http://msdn.microsoft.com/library/windows/desktop/ms686657) die Struktur in [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Syntax  
  
```  
class COleConvertDialog : public COleDialog  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[COleConvertDialog::COleConvertDialog](../Topic/COleConvertDialog::COleConvertDialog.md)|Erstellt ein `COleConvertDialog`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[COleConvertDialog::DoConvert](../Topic/COleConvertDialog::DoConvert.md)|Führt die Konvertierung aus, die im Dialogfeld angegeben wird.|  
|[COleConvertDialog::DoModal](../Topic/COleConvertDialog::DoModal.md)|Zeigt das OLE\-Änderungs\-Elementdialogfeld an.|  
|[COleConvertDialog::GetClassID](../Topic/COleConvertDialog::GetClassID.md)|Ruft **CLSID** ab, das dem ausgewählten Element zugeordnet ist.|  
|[COleConvertDialog::GetDrawAspect](../Topic/COleConvertDialog::GetDrawAspect.md)|Gibt an, ob Element als Symbol zeichnet.|  
|[COleConvertDialog::GetIconicMetafile](../Topic/COleConvertDialog::GetIconicMetafile.md)|Ruft ein Handle an die Metadatei, die mit dem ikonenhaften Formular dieses Elements zugeordnet ist.|  
|[COleConvertDialog::GetSelectionType](../Topic/COleConvertDialog::GetSelectionType.md)|Ruft den Typ der Auswahl verwendet ab.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[COleConvertDialog::m\_cv](../Topic/COleConvertDialog::m_cv.md)|Eine Struktur, die das Verhalten des Dialogfelds steuert.|  
  
## Hinweise  
  
> [!NOTE]
>  Wird vom Assistenten erstellter Containercode der Anwendung diese Klasse.  
  
 Weitere Informationen zu OLE\-Besondere Dialogfelder, finden Sie im Artikel [Dialogfelder in OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog\-Klasse](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleConvertDialog`  
  
## Anforderungen  
 **Header:**  afxodlgs.h  
  
## Siehe auch  
 [COleDialog Class](../../mfc/reference/coledialog-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleDialog Class](../../mfc/reference/coledialog-class.md)
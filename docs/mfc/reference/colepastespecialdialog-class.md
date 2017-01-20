---
title: "COlePasteSpecialDialog Class"
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
  - "COlePasteSpecialDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COlePasteSpecialDialog class"
  - "Dialogfelder, Paste Special"
  - "OLE Paste Special dialog box"
  - "Paste Special dialog box"
ms.assetid: 0e82ef9a-9bbe-457e-8240-42c86a0534f7
caps.latest.revision: 24
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# COlePasteSpecialDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wird für das Dialogfeld OLE Inhalte einfügen.  
  
## Syntax  
  
```  
  
class COlePasteSpecialDialog : public COleDialog  
  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[COlePasteSpecialDialog::COlePasteSpecialDialog](../Topic/COlePasteSpecialDialog::COlePasteSpecialDialog.md)|Erstellt ein `COlePasteSpecialDialog`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[COlePasteSpecialDialog::AddFormat](../Topic/COlePasteSpecialDialog::AddFormat.md)|Fügt benutzerdefinierte Formate der Liste der Stile hinzu, die die Anwendung einfügen kann.|  
|[COlePasteSpecialDialog::AddLinkEntry](../Topic/COlePasteSpecialDialog::AddLinkEntry.md)|Fügt einen neuen Eintrag der Liste der unterstützten Zwischenablageformaten hinzu.|  
|[COlePasteSpecialDialog::AddStandardFormats](../Topic/COlePasteSpecialDialog::AddStandardFormats.md)|Fügt **CF\_BITMAP**, **CF\_DIB**, `CF_METAFILEPICT` hinzu, und optional `CF_LINKSOURCE` zur Liste der Stile, die die Anwendung einfügen kann.|  
|[COlePasteSpecialDialog::CreateItem](../Topic/COlePasteSpecialDialog::CreateItem.md)|Erstellt das Element im Containerdokument mit dem angegebenen Format.|  
|[COlePasteSpecialDialog::DoModal](../Topic/COlePasteSpecialDialog::DoModal.md)|Zeigt das Dialogfeld OLE Inhalte einfügen an.|  
|[COlePasteSpecialDialog::GetDrawAspect](../Topic/COlePasteSpecialDialog::GetDrawAspect.md)|Teilt mit, ob Element als Symbol oder nicht.|  
|[COlePasteSpecialDialog::GetIconicMetafile](../Topic/COlePasteSpecialDialog::GetIconicMetafile.md)|Ruft ein Handle an die Metadatei, die mit dem ikonenhaften Formular dieses Elements zugeordnet ist.|  
|[COlePasteSpecialDialog::GetPasteIndex](../Topic/COlePasteSpecialDialog::GetPasteIndex.md)|Ruft den Index der verfügbaren Pastenoptionen ab, der vom Benutzer ausgewählt wurde.|  
|[COlePasteSpecialDialog::GetSelectionType](../Topic/COlePasteSpecialDialog::GetSelectionType.md)|Ruft den Typ der Auswahl verwendet ab.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[COlePasteSpecialDialog::m\_ps](../Topic/COlePasteSpecialDialog::m_ps.md)|Eine Struktur des Typs **OLEUIPASTESPECIAL**, der die Funktion des Dialogfelds steuert.|  
  
## Hinweise  
 Erstellen Sie ein Objekt der Klasse `COlePasteSpecialDialog`, wenn Sie dieses Dialogfeld aufrufen möchten.  Nachdem ein `COlePasteSpecialDialog`\-Objekt erstellt wurde, können Sie die [AddFormat](../Topic/COlePasteSpecialDialog::AddFormat.md) und [AddStandardFormats](../Topic/COlePasteSpecialDialog::AddStandardFormats.md)\-Memberfunktionen verwenden, um Zwischenablageformate dem Dialogfeld hinzuzufügen.  Sie können die [m\_ps](../Topic/COlePasteSpecialDialog::m_ps.md)\-Struktur auch verwenden, um die Werte oder die Zustände von Steuerelementen im Dialogfeld zu initialisieren.  Die `m_ps`\-Struktur ist vom Typ **OLEUIPASTESPECIAL**.  
  
 Weitere Informationen finden Sie unter [OLEUIPASTESPECIAL](http://msdn.microsoft.com/library/windows/desktop/ms692434) die Struktur in [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Weitere Informationen zu OLE\-Besondere Dialogfelder, finden Sie im Artikel [Dialogfelder in OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog\-Klasse](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COlePasteSpecialDialog`  
  
## Anforderungen  
 **Header:**  afxodlgs.h  
  
## Siehe auch  
 [MFC\-Beispiel OCLIENT](../../top/visual-cpp-samples.md)   
 [COleDialog Class](../../mfc/reference/coledialog-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleDialog Class](../../mfc/reference/coledialog-class.md)
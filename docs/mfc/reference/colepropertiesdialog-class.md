---
title: "COlePropertiesDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COlePropertiesDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COlePropertiesDialog class"
  - "Dialogfelder, OLE"
  - "Object Properties dialog box"
  - "OLE-Dokumente, Ändern von Eigenschaften"
  - "OLE Object Properties dialog box"
  - "Eigenschaftenseiten, OLE"
ms.assetid: a54dbc89-1447-4329-bd01-00e98ec9e935
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# COlePropertiesDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Kapselt das OLE\-Objekt\-Eigenschaftdialogfeld Windows allgemeine.  
  
## Syntax  
  
```  
  
class COlePropertiesDialog : public COleDialog  
  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[COlePropertiesDialog::COlePropertiesDialog](../Topic/COlePropertiesDialog::COlePropertiesDialog.md)|Erstellt ein `COlePropertiesDialog`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[COlePropertiesDialog::DoModal](../Topic/COlePropertiesDialog::DoModal.md)|Zeigt das Dialogfeld an und ermöglicht dem Benutzer, um die Auswahl zu machen.|  
|[COlePropertiesDialog::OnApplyScale](../Topic/COlePropertiesDialog::OnApplyScale.md)|Aufgerufen vom Framework, wenn die Skalierung des Dokumentelements geändert hat.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[COlePropertiesDialog::m\_gp](../Topic/COlePropertiesDialog::m_gp.md)|Eine Struktur verwendet, um die "allgemeine" Seite `COlePropertiesDialog` eines Objekts zu initialisieren.|  
|[COlePropertiesDialog::m\_lp](../Topic/COlePropertiesDialog::m_lp.md)|Eine Struktur verwendet, um die Seite "Link" `COlePropertiesDialog` eines Objekts zu initialisieren.|  
|[COlePropertiesDialog::m\_op](../Topic/COlePropertiesDialog::m_op.md)|Eine Struktur verwendet, um das `COlePropertiesDialog`\-Objekt initialisieren.|  
|[COlePropertiesDialog::m\_psh](../Topic/COlePropertiesDialog::m_psh.md)|Eine Struktur verwendet, um zusätzliche benutzerdefinierte Eigenschaftenseiten hinzuzufügen.|  
|[COlePropertiesDialog::m\_vp](../Topic/COlePropertiesDialog::m_vp.md)|Eine Struktur verwendet, um die Seite "Ansichts" eines Objekts `COlePropertiesDialog` anzupassen.|  
  
## Hinweise  
 Allgemeine OLE\-Objekt\-Eigenschaftdialogfelder bieten eine einfache Möglichkeit, die Eigenschaften eines OLE\-Dokumentelements anzuzeigen und zu ändern, das mit Windows\-Standards in ähnlicher Weise konsistent ist.  Zu diesen Eigenschaften zählen unter anderem Informationen über die Datei dargestellt durch das Dokumentelement, Optionen zum Anzeigen der Symbol\- und Bildskalieren und Informationen über den Link des Elements \(wenn das Element verknüpft ist\).  
  
 Um ein `COlePropertiesDialog`\-Objekt zu verwenden, erstellen Sie zunächst das Objekt mithilfe des `COlePropertiesDialog`\-Konstruktors.  Nachdem das Dialogfeld erstellt wurde, rufen Sie die `DoModal`\-Memberfunktion auf, um das Dialogfeld anzuzeigen und dem Benutzer zu ermöglichen, um alle Eigenschaften des Elements ändern.  `DoModal` gibt zurück, ob der Benutzer OK \(**IDOK**\) oder die Schaltfläche Löschverhalten \(**IDCANCEL**\) ausgewählt hat.  Neben OK und zu den Abbrechen gibt es eine übernehmensschaltfläche.  Wenn der Benutzer auswählt, wenden Sie zu, werden alle Änderungen, die an den Eigenschaften des Dokumentelements vorgenommen werden, am Element angewendet und das Bild wird automatisch aktualisiert, aber bleibt aktiv.  
  
 Der [m\_psh](../Topic/COlePropertiesDialog::m_psh.md) Datenmember ist ein Zeiger auf eine Struktur **PROPSHEETHEADER**, und in den meisten Fällen müssen Sie nicht, um explizit auf sie zuzugreifen.  Eine Ausnahme ist, wenn Sie zusätzliche Eigenschaftenseiten zum standardmäßigen Allgemein hinaus benötigen, anzeigen und Seiten verknüpfen.  In diesem Fall können Sie den `m_psh` Datenmember ändern, um die benutzerdefinierten Seiten einzuschließen, bevor Sie die `DoModal`\-Memberfunktion aufrufen.  
  
 Weitere Informationen zu OLE\-Dialogfelder, finden Sie im Artikel [Dialogfelder in OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog\-Klasse](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COlePropertiesDialog`  
  
## Anforderungen  
 **Header:**  afxodlgs.h  
  
## Siehe auch  
 [MFC überprüft CIRC](../../top/visual-cpp-samples.md)   
 [COleDialog Class](../../mfc/reference/coledialog-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleDialog Class](../../mfc/reference/coledialog-class.md)   
 [CPropertyPage Class](../../mfc/reference/cpropertypage-class.md)
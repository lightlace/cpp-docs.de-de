---
title: "CMFCRibbonCustomizePropertyPage Class"
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
  - "GetThisClass"
  - "CMFCRibbonCustomizePropertyPage::CreateObject"
  - "CMFCRibbonCustomizePropertyPage"
  - "CMFCRibbonCustomizePropertyPage::~CMFCRibbonCustomizePropertyPage"
  - "CMFCRibbonCustomizePropertyPage.GetThisClass"
  - "CMFCRibbonCustomizePropertyPage.CreateObject"
  - "~CMFCRibbonCustomizePropertyPage"
  - "CreateObject"
  - "CMFCRibbonCustomizePropertyPage.~CMFCRibbonCustomizePropertyPage"
  - "CMFCRibbonCustomizePropertyPage::GetThisClass"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "~CMFCRibbonCustomizePropertyPage destructor"
  - "CMFCRibbonCustomizePropertyPage class"
  - "CMFCRibbonCustomizePropertyPage class, Destruktor"
  - "CreateObject method"
  - "GetThisClass method"
ms.assetid: ea32a99a-dfbe-401e-8975-aa191552532f
caps.latest.revision: 26
caps.handback.revision: "14"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCRibbonCustomizePropertyPage Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implementiert eine benutzerdefinierte Seite für das Dialogfeld **Anpassen** in den Anwendungen erläutert.  
  
## Syntax  
  
```  
class CMFCRibbonCustomizePropertyPage: public CMFCPropertyPage  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|||  
|-|-|  
|Name|Description|  
|[CMFCRibbonCustomizePropertyPage::CMFCRibbonCustomizePropertyPage](../Topic/CMFCRibbonCustomizePropertyPage::CMFCRibbonCustomizePropertyPage.md)|Erstellt ein `CMFCRibbonCustomizePropertyPage`\-Objekt.|  
|`CMFCRibbonCustomizePropertyPage::~CMFCRibbonCustomizePropertyPage`|Destruktor.|  
  
### Öffentliche Methoden  
  
|||  
|-|-|  
|Name|Description|  
|[CMFCRibbonCustomizePropertyPage::AddCustomCategory](../Topic/CMFCRibbonCustomizePropertyPage::AddCustomCategory.md)|Fügt eine benutzerdefinierte Kategorie dem **Befehle** Kombinationsfeld hinzu.|  
|`CMFCRibbonCustomizePropertyPage::CreateObject`|Wird vom Framework, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|`CMFCRibbonCustomizePropertyPage::GetThisClass`|Wird vom Framework, um ein Zeiger auf [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)\-Objekt abzurufen, das diesem Klassentyp zugeordnet ist.|  
|[CMFCRibbonCustomizePropertyPage::OnOK](../Topic/CMFCRibbonCustomizePropertyPage::OnOK.md)|Aufgerufen vom System, wenn ein Benutzer auf **OK** auf dem Dialogfeld **Anpassen** klickt.|  
  
## Hinweise  
 Wenn Sie benutzerdefinierte Befehle **Anpassen** dem Dialogfeld hinzufügen möchten, müssen Sie die AFX\_WM\_ON\_RIBBON\_CUSTOMIZE\-Meldung bearbeiten.  Im Meldungshandler instanziieren Sie ein `CMFCRibbonCustomizePropertyPage`\-Objekt auf dem Stapel.  Erstellen Sie eine Liste von benutzerdefinierten Befehlen, und rufen Sie dann `AddCustomCategory` auf, um die neue Seite dem Dialogfeld **Anpassen** hinzuzufügen.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie ein `CMFCRibbonCustomizePropertyPage`\-Objekt erstellt und eine benutzerdefinierte Kategorie hinzugefügt wird.  
  
 [!CODE [NVC_MFC_RibbonApp#22](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_RibbonApp#22)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog\-Klasse](../../mfc/reference/cdialog-class.md)  
  
 [CPropertyPage](../../mfc/reference/cpropertypage-class.md)  
  
 [CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md)  
  
 [CMFCRibbonCustomizePropertyPage](../../mfc/reference/cmfcribboncustomizepropertypage-class.md)  
  
## Anforderungen  
 **Header:** afxribboncustomizedialog.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)
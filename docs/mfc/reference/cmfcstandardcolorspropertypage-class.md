---
title: "CMFCStandardColorsPropertyPage Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCStandardColorsPropertyPage"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCStandardColorsPropertyPage class"
ms.assetid: b84b7cfb-bb24-4c65-804a-5b642cb64400
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CMFCStandardColorsPropertyPage Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt eine Eigenschaftenseite dar, der Benutzer verwenden, um Standardfarben in einem Dialogfeld auszuwählen.  
  
## Syntax  
  
```  
class CMFCStandardColorsPropertyPage : public CPropertyPage  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|||  
|-|-|  
|Name|Description|  
|`CMFCStandardColorsPropertyPage::CMFCStandardColorsPropertyPage`|Standardkonstruktor.|  
  
### Öffentliche Methoden  
  
|||  
|-|-|  
|Name|Description|  
|`CMFCStandardColorsPropertyPage::CreateObject`|Wird vom Framework, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|`CMFCStandardColorsPropertyPage::GetThisClass`|Wird vom Framework, um ein Zeiger auf [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)\-Objekt abzurufen, das diesem Klassentyp zugeordnet ist.|  
  
### Hinweise  
 Die `CMFCColorDialog`\-Klasse verwendet diese Klasse, um die Standardfarbeigenschaftenseite anzuzeigen.  Weitere Informationen zur `CMFCColorDialog`\-Komponente finden Sie unter [CMFCColorDialog Class](../../mfc/reference/cmfccolordialog-class.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog\-Klasse](../../mfc/reference/cdialog-class.md)  
  
 [CPropertyPage](../../mfc/reference/cpropertypage-class.md)  
  
 [CMFCStandardColorsPropertyPage](../../mfc/reference/cmfcstandardcolorspropertypage-class.md)  
  
## Anforderungen  
 **Header:** afxstandardcolorspropertypage.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCColorDialog Class](../../mfc/reference/cmfccolordialog-class.md)   
 [CMFCCustomColorsPropertyPage Class](../../mfc/reference/cmfccustomcolorspropertypage-class.md)
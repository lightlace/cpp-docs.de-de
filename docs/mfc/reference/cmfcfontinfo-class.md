---
title: "CMFCFontInfo Class"
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
  - "CMFCFontInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCFontInfo class"
  - "CMFCFontInfo::CMFCFontInfo constructor"
ms.assetid: f88329b2-d74e-4921-9441-a3bb6536a049
caps.latest.revision: 26
caps.handback.revision: "14"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCFontInfo Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `CMFCFontInfo`\-Klasse beschreibt den Namen und andere Attribute einer Schriftart.  
  
## Syntax  
  
```  
class CMFCFontInfo : public CObject  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|`CMFCFontInfo`|Erstellt ein `CMFCFontInfo`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCFontInfo::GetFullName](../Topic/CMFCFontInfo::GetFullName.md)|Ruft die verketteten Namen einer Schriftart und des Zeichensatzes ab \(Skript\).|  
  
### Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCFontInfo::m\_nCharSet](../Topic/CMFCFontInfo::m_nCharSet.md)|Ein Wert, der den Zeichensatz \(Skript\) zugeordnet mit der Schriftart angibt.|  
|[CMFCFontInfo::m\_nPitchAndFamily](../Topic/CMFCFontInfo::m_nPitchAndFamily.md)|Ein Wert, der die Schriftbreite und die Familie der Schriftarten angibt.|  
|[CMFCFontInfo::m\_nType](../Topic/CMFCFontInfo::m_nType.md)|Ein Wert, der den Typ der Schriftarten angibt.|  
|[CMFCFontInfo::m\_strName](../Topic/CMFCFontInfo::m_strName.md)|Der Name der Schriftarten; beispielsweise **Arial**.|  
|[CMFCFontInfo::m\_strScript](../Topic/CMFCFontInfo::m_strScript.md)|Der Name eines Zeichensatzes \(Skript\) zugeordnet mit der Schriftart.|  
  
## Hinweise  
 Sie können ein `CMFCFontInfo`\-Objekt auf ein Element der [CMFCToolBarFontComboBox Class](../../mfc/reference/cmfctoolbarfontcombobox-class.md)\-Klasse anfügen.  Rufen Sie die [CMFCToolBarFontComboBox::GetFontDesc](../Topic/CMFCToolBarFontComboBox::GetFontDesc.md)\-Methode auf, um einen Zeiger auf einen `CMFCFontInfo`\-Objekt abzurufen.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie verschiedene Member der Klasse `CMFCFontInfo` verwendet.  Das Beispiel zeigt, wie ein `CMFCFontInfo`\-Objekt von `CMFCRibbonFontComboBox` abgerufen wird und wie auf ihre lokalen Variablen zugreift.  Dieses Beispiel ist Teil [MS Demobeispiel Office 2007](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_MSOffice2007Demo#6](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_MSOffice2007Demo#6)]  
  
## Anforderungen  
 **Header:** afxtoolbarfontcombobox.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarFontComboBox Class](../../mfc/reference/cmfctoolbarfontcombobox-class.md)   
 [CMFCToolBarFontSizeComboBox Class](../../mfc/reference/cmfctoolbarfontsizecombobox-class.md)
---
title: "COlePropertyPage Class"
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
  - "COlePropertyPage"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COlePropertyPage class"
  - "Benutzerdefinierte Steuerelemente [MFC], Eigenschaften"
  - "displaying properties"
  - "OLE property pages"
  - "Eigenschaften [C++], Anzeigen"
  - "Eigenschaftenseiten, OLE"
ms.assetid: e9972872-8e6b-4550-905e-d36a274d64dc
caps.latest.revision: 23
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# COlePropertyPage Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wird verwendet, um die Eigenschaften eines benutzerdefinierten Steuerelements in einer grafischen Oberfläche anzuzeigen, ähnlich einem Dialogfeld.  
  
## Syntax  
  
```  
class AFX_NOVTABLE COlePropertyPage : public CDialog  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[COlePropertyPage::COlePropertyPage](../Topic/COlePropertyPage::COlePropertyPage.md)|Erstellt ein `COlePropertyPage`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[COlePropertyPage::GetControlStatus](../Topic/COlePropertyPage::GetControlStatus.md)|Gibt an, ob der Benutzer den Wert im Steuerelement geändert hat.|  
|[COlePropertyPage::GetObjectArray](../Topic/COlePropertyPage::GetObjectArray.md)|Gibt das Array zurück, das durch die Eigenschaftenseite bearbeitet wird.|  
|[COlePropertyPage::GetPageSite](../Topic/COlePropertyPage::GetPageSite.md)|Gibt einen Zeiger auf die `IPropertyPageSite`\-Schnittstelle der Eigenschaftenseite zurück.|  
|[COlePropertyPage::IgnoreApply](../Topic/COlePropertyPage::IgnoreApply.md)|Bestimmt das aktivieren, nicht die übernehmensschaltfläche steuert.|  
|[COlePropertyPage::IsModified](../Topic/COlePropertyPage::IsModified.md)|Gibt an, ob der Benutzer die Eigenschaftenseite geändert hat.|  
|[COlePropertyPage::OnEditProperty](../Topic/COlePropertyPage::OnEditProperty.md)|Aufgerufen vom Framework, wenn der Benutzer eine Eigenschaft bearbeitet.|  
|[COlePropertyPage::OnHelp](../Topic/COlePropertyPage::OnHelp.md)|Aufgerufen vom Framework, wenn die Benutzeraufrufe helfen.|  
|[COlePropertyPage::OnInitDialog](../Topic/COlePropertyPage::OnInitDialog.md)|Aufgerufen vom Framework, wenn die Eigenschaftenseite initialisiert wird.|  
|[COlePropertyPage::OnObjectsChanged](../Topic/COlePropertyPage::OnObjectsChanged.md)|Aufgerufen vom Framework, wenn ein anderes OLE\-Steuerelement, mit neuen Eigenschaften, ausgewählt ist.|  
|[COlePropertyPage::OnSetPageSite](../Topic/COlePropertyPage::OnSetPageSite.md)|Aufgerufen vom Framework, wenn der Eigenschaftenrahmen die Site der Seite bietet.|  
|[COlePropertyPage::SetControlStatus](../Topic/COlePropertyPage::SetControlStatus.md)|Legt ein Flag fest, ob der Benutzer den Wert im Steuerelement geändert hat.|  
|[COlePropertyPage::SetDialogResource](../Topic/COlePropertyPage::SetDialogResource.md)|Legt die Dialogfeldressource der Eigenschaftenseite fest.|  
|[COlePropertyPage::SetHelpInfo](../Topic/COlePropertyPage::SetHelpInfo.md)|Legt den kurzen Hilfetext der Eigenschaftenseite, den Namen der Hilfedatei und den Hilfekontext fest.|  
|[COlePropertyPage::SetModifiedFlag](../Topic/COlePropertyPage::SetModifiedFlag.md)|Legt ein Flag fest, ob der Benutzer die Eigenschaftenseite geändert hat.|  
|[COlePropertyPage::SetPageName](../Topic/COlePropertyPage::SetPageName.md)|Legt den Namen der Eigenschaftenseite fest \(Beschriftung\).|  
  
## Hinweise  
 Beispielsweise enthält möglicherweise eine Eigenschaftenseite ein Bearbeitungssteuerelement, das dem Benutzer ermöglicht, die Beschriftungseigenschaft des Steuerelements anzuzeigen und zu ändern.  
  
 Jede Ressource oder Bestandskontrolleeigenschaft kann ein Dialogfeld\-Steuerelement verfügen, das dem Benutzer des Steuerelements ermöglicht, den aktuellen Eigenschaftswert anzuzeigen und diesen Wert nach Bedarf zu ändern.  
  
 Weitere Informationen zur Verwendung von `COlePropertyPage`, finden Sie im Artikel [ActiveX\-Steuerelemente: Eigenschaftenseiten](../../mfc/mfc-activex-controls-property-pages.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog\-Klasse](../../mfc/reference/cdialog-class.md)  
  
 `COlePropertyPage`  
  
## Anforderungen  
 **Header:**  afxctl.h  
  
## Siehe auch  
 [MFC überprüft CIRC3](../../top/visual-cpp-samples.md)   
 [MFC\-Beispiel TESTHELP](../../top/visual-cpp-samples.md)   
 [CDialog Class](../../mfc/reference/cdialog-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDialog Class](../../mfc/reference/cdialog-class.md)
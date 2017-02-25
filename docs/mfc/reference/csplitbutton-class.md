---
title: "CSplitButton Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSplitButton class"
ms.assetid: 6844d0a9-6408-4e44-9b5f-57628ed8bad6
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CSplitButton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Klasse stellt ein `CSplitButton` SplitButton\-Steuerelement dar.  Das SplitButton\-Steuerelement führt ein Standardverhalten, wenn ein Benutzer auf den Hauptteil der Schaltfläche klickt, und es wird ein Dropdownmenü an, wenn ein Benutzer auf den Dropdownpfeil der Schaltfläche klickt.  
  
## Syntax  
  
```  
class CSplitButton : public CButton  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CSplitButton::CSplitButton](../Topic/CSplitButton::CSplitButton.md)|Erstellt ein `CSplitButton`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CSplitButton::Create](../Topic/CSplitButton::Create.md)|Erstellt ein SplitButton\-Steuerelement mit angegebenen Formaten und weist dieses dem aktuellen `CSplitButton`\-Objekt.|  
|[CSplitButton::SetDropDownMenu](../Topic/CSplitButton::SetDropDownMenu.md)|Legt das Dropdownmenü fest, das angezeigt wird, wenn ein Benutzer auf den Dropdownpfeil des aktuellen Steuerelements der Auswahlschaltfläche klickt.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CSplitButton::OnDropDown](../Topic/CSplitButton::OnDropDown.md)|Bearbeitet die `BCN_DROPDOWN` Benachrichtigung, der das System sendet, wenn ein Benutzer auf den Dropdownpfeil des aktuellen Steuerelements der Auswahlschaltfläche klickt.|  
  
## Hinweise  
 Die `CSplitButton`\-Klasse wird von [CButton](../../mfc/reference/cbutton-class.md)\-Klasse abgeleitet.  Das SplitButton\-Steuerelement ist ein Schaltflächen\-Steuerelement, dessen Format `BS_SPLITBUTTON` ist.  Es wird ein benutzerdefiniertes Menü an, wenn ein Benutzer auf den Dropdownpfeil klicken.  Weitere Informationen finden Sie in `BS_SPLITBUTTON` und `BS_DEFSPLITBUTTON` Stile in [Schaltflächen\-Formate](http://msdn.microsoft.com/library/windows/desktop/bb775951).  
  
 Die folgende Abbildung stellt ein Dialogfeld dar, das ein Pager\-Steuerelement und einen \(1\) SplitButton\-Steuerelement enthält.  Klicken Sie auf den Dropdownpfeil \(2\) ist bereits geklickt wurde und das Untermenü \(3\) wird angezeigt.  
  
 ![Dialogfeld mit einer Trennschaltfläche und einem Pagersteuerelement.](../../mfc/reference/media/splitbutton_pager.png "SplitButton\_Pager")  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 `CSplitButton`  
  
## Anforderungen  
 **Header:** afxcmn.h  
  
 Diese Klasse wird in [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] und höher unterstützt.  
  
 Zusätzliche Anforderungen für diese Klasse werden in [Anforderungen für die Erstellung von Windows Vista\-Standardsteuerelementen](../../mfc/build-requirements-for-windows-vista-common-controls.md) beschrieben.  
  
## Siehe auch  
 [CSplitButton Class](../../mfc/reference/csplitbutton-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CButton Class](../../mfc/reference/cbutton-class.md)
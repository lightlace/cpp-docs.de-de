---
title: "CMFCDesktopAlertWndButton Class"
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
  - "CMFCDesktopAlertWndButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCDesktopAlertWndButton class"
ms.assetid: df39a0c8-0c39-4ab0-8c64-78c5b2c4ecaf
caps.latest.revision: 23
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCDesktopAlertWndButton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ermöglicht die einem Desktopwarnungsdialogfeld hinzugefügt werden, Schaltflächen.  
  
## Syntax  
  
```  
class CMFCDesktopAlertWndButton : public CMFCButton  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|||  
|-|-|  
|Name|Description|  
|`CMFCDesktopAlertWndButton::CMFCDesktopAlertWndButton`|Standardkonstruktor.|  
|`CMFCDesktopAlertWndButton::~CMFCDesktopAlertWndButton`|Destruktor.|  
  
### Öffentliche Methoden  
  
|||  
|-|-|  
|Name|Description|  
|[CMFCDesktopAlertWndButton::IsCaptionButton](../Topic/CMFCDesktopAlertWndButton::IsCaptionButton.md)|Bestimmt, ob die Schaltfläche im ausgewählten aktiven Bereich des Dialogfelds angezeigt wird.|  
|[CMFCDesktopAlertWndButton::IsCloseButton](../Topic/CMFCDesktopAlertWndButton::IsCloseButton.md)|Bestimmt, ob die Schaltfläche das benutzerdefinierte Dialogfeld enthält.|  
  
### Datenmember  
  
|||  
|-|-|  
|Name|Description|  
|`CMFCDesktopAlertWndButton::m_bIsCaptionButton`|Ein boolescher Wert, der angibt, ob die Schaltfläche im ausgewählten aktiven Bereich des Dialogfelds angezeigt wird.|  
|`CMFCDesktopAlertWndButton::m_bIsCloseButton`|Ein boolescher Wert, der angibt, ob die Schaltfläche das benutzerdefinierte Dialogfeld enthält.|  
  
### Hinweise  
 Standardmäßig legt der Konstruktor die `m_bIsCaptionButton` und `m_bIsCloseButton` Datenmember zu `FALSE` fest.  Das Objekt `CMFCDesktopAlertDialog` des übergeordneten Elements wird `m_bIsCaptionButton` zu `TRUE` fest, wenn die Schaltfläche im aktiven Bereich des Dialogfelds ausgewählten positioniert wird.  Die `CMFCDesktopAlertDialog`\-Klasse erstellt ein Objekt die `CMFCDesktopAlertWndButton` dient als die Schaltfläche, die das benutzerdefinierte Dialogfeld enthält und `m_bIsCloseButton` zu `TRUE` festgelegt wird.  
  
 Fügen Sie `CMFCDesktopAlertWndButton`\-Objekte einem `CMFCDesktopAlertDialog`\-Objekt hinzu, wie Sie eine beliebige Schaltfläche hinzufügen.  Weitere Informationen zur `CMFCDesktopAlertDialog`\-Komponente finden Sie unter [CMFCDesktopAlertDialog Class](../../mfc/reference/cmfcdesktopalertdialog-class.md).  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie die `SetImage`\-Methode in der Klasse `CMFCDesktopAlertWndButton` verwendet.  Dieser Codeausschnitt ist Teil [Desktop\-wachsames Demobeispiel](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_DesktopAlertDemo#4](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_DesktopAlertDemo#4)]  
[!CODE [NVC_MFC_DesktopAlertDemo#5](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_DesktopAlertDemo#5)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCButton](../../mfc/reference/cmfcbutton-class.md)  
  
 [CMFCDesktopAlertWndButton](../../mfc/reference/cmfcdesktopalertwndbutton-class.md)  
  
## Anforderungen  
 **Header:** afxdesktopalertwnd.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCDesktopAlertDialog Class](../../mfc/reference/cmfcdesktopalertdialog-class.md)
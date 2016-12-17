---
title: "CMFCRibbonApplicationButton Class"
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
  - "CMFCRibbonApplicationButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonApplicationButton class"
ms.assetid: beb81757-fabd-4641-9130-876ba8505b78
caps.latest.revision: 25
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCRibbonApplicationButton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implementiert eine spezielle Schaltfläche in der oberen linken Ecke des Anwendungsfensters.  Wenn sie geklickt wird, wird auf die Schaltfläche ein Menü, das normalerweise allgemeine **Datei** Befehle wie **Öffnen**, **Speichern** und **Beenden** enthält.  
  
## Syntax  
  
```  
class CMFCRibbonApplicationButton : public CMFCRibbonButton  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCRibbonApplicationButton::CMFCRibbonApplicationButton](../Topic/CMFCRibbonApplicationButton::CMFCRibbonApplicationButton.md)|erstellt und initialisiert ein `CMFCRibbonApplicationButton`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|`CMFCRibbonApplicationButton::CreateObject`|Wird vom Framework, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|`CMFCRibbonApplicationButton::GetThisClass`|Wird vom Framework, um ein Zeiger auf [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)\-Objekt abzurufen, das diesem Klassentyp zugeordnet ist.|  
|[CMFCRibbonApplicationButton::SetImage](../Topic/CMFCRibbonApplicationButton::SetImage.md)|Weist ein Bild zur Menüband\-Anwendungsschaltfläche zu.|  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie verschiedene Methoden in der Klasse `CMFCRibbonApplicationButton` verwendet.  Im Beispiel wird gezeigt, wie ein Bild zur Anwendungsschaltfläche zuweist und wie die QuickInfo festgelegt werden.  Dieser Codeausschnitt ist Teil [Clientbeispiel Videofunktionen](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_DrawClient#4](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_DrawClient#4)]  
[!CODE [NVC_MFC_DrawClient#5](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_DrawClient#5)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonApplicationButton](../../mfc/reference/cmfcribbonapplicationbutton-class.md)  
  
## Anforderungen  
 **Header:** afxRibbonBar.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonButton Class](../../mfc/reference/cmfcribbonbutton-class.md)
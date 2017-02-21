---
title: "CMFCAcceleratorKey Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCAcceleratorKey"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCAcceleratorKey class"
ms.assetid: d140fbf7-23db-45ea-a63e-414a5ec7b3d5
caps.latest.revision: 36
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 38
---
# CMFCAcceleratorKey Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine Hilfsklasse, die virtuelle Tastenzuordnung und Formatierung implementiert.  
  
## Syntax  
  
```  
class CMFCAcceleratorKey : public CObject  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCAcceleratorKey::CMFCAcceleratorKey](../Topic/CMFCAcceleratorKey::CMFCAcceleratorKey.md)|Erstellt ein `CMFCAcceleratorKey`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCAcceleratorKey::Format](../Topic/CMFCAcceleratorKey::Format.md)|Übersetzt die ACCEL\-Struktur zu ihrer visuellen Darstellung.|  
|[CMFCAcceleratorKey::SetAccelerator](../Topic/CMFCAcceleratorKey::SetAccelerator.md)|Legt die Zugriffstaste für das `CMFCAcceleratorKey`\-Objekt fest.|  
  
## Hinweise  
 Zugriffstasten werden auch als Tastenkombinationen.  Wenn Sie Tastenkombinationen anzeigen möchten, die ein Benutzer eingibt, ordnet [CMFCAcceleratorKeyAssignCtrl Class](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md) Tastenkombinationen, wie Alt\+Shift\+S, zu einem benutzerdefinierten Textformat, wie "ALT \+ UMSCHALT\+S" zu.  Jedes `CMFCAcceleratorKey`\-Objektzuordnungen eine einzelne Tastenkombination einem Textformat.  
  
 Weitere Informationen dazu, wie Tastenkombinationen und Zugriffstastentabellen, finden Sie unter [CKeyboardManager Class](../../mfc/reference/ckeyboardmanager-class.md) verwendet.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie ein `CMFCAcceleratorKey`\-Objekt erstellt und wie die `Format`\-Methode verwendet.  
  
 [!CODE [NVC_MFC_RibbonApp#30](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_RibbonApp#30)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md)  
  
## Anforderungen  
 **Header:** afxacceleratorkey.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CKeyboardManager Class](../../mfc/reference/ckeyboardmanager-class.md)
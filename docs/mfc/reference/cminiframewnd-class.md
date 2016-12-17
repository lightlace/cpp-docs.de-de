---
title: "CMiniFrameWnd Class"
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
  - "CMiniFrameWnd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMiniFrameWnd class"
  - "mini-frame windows"
  - "Symbolleisten [C++]"
ms.assetid: b8f534ed-0532-4d8e-9657-5595cf677749
caps.latest.revision: 21
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# CMiniFrameWnd Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt ein Rahmenfenster mit halber Höhe dar, das in der Regel um unverankerte Symbolleisten sichtbar ist.  
  
## Syntax  
  
```  
class CMiniFrameWnd : public CFrameWnd  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMiniFrameWnd::CMiniFrameWnd](../Topic/CMiniFrameWnd::CMiniFrameWnd.md)|Erstellt ein `CMiniFrameWnd`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMiniFrameWnd::Create](../Topic/CMiniFrameWnd::Create.md)|Erstellt ein Objekt `CMiniFrameWnd` nach Konstruktion.|  
|[CMiniFrameWnd::CreateEx](../Topic/CMiniFrameWnd::CreateEx.md)|Erstellt ein Objekt `CMiniFrameWnd` \(mit zusätzlichen Optionen\) nach Konstruktion.|  
  
## Hinweise  
 Diese Minirahmenfenster verhalten sich wie normale Rahmenfenster, außer dass sie haben nicht zu minimieren, maximieren\/Schaltflächen und Menüs, oder Sie müssen einen einzelnen Mausklick auf dem Systemmenü, sie schließen nur.  
  
 Um ein `CMiniFrameWnd`\-Objekt zu verwenden, definieren Sie zuerst das Objekt.  Rufen Sie dann die [Erstellen Sie](../Topic/CMiniFrameWnd::Create.md)\-Memberfunktion auf, um das Minirahmenfenster anzuzeigen.  
  
 Weitere Informationen dazu, wie `CMiniFrameWnd`\-Objekte, finden Sie im Artikel [andockbare Symbolleisten und unverankerte](../../mfc/docking-and-floating-toolbars.md) verwendet.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 `CMiniFrameWnd`  
  
## Anforderungen  
 **Header:** afxwin.h  
  
## Siehe auch  
 [CFrameWnd Class](../../mfc/reference/cframewnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CFrameWnd Class](../../mfc/reference/cframewnd-class.md)
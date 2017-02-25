---
title: "CClientDC Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CClientDC"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CClientDC class"
  - "CDC-Klasse, device contexts for client areas"
  - "client-area device context"
  - "device contexts, Clientbereich"
ms.assetid: 8a871d6b-06f8-496e-9fa3-9a5780848369
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CClientDC Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Kümmert sich um Aufrufen der [GetDC](http://msdn.microsoft.com/library/windows/desktop/dd144871) Windows\-Funktionen zur Konstruktionszeit und [ReleaseDC](http://msdn.microsoft.com/library/windows/desktop/dd162920) an der Zerstörungszeit.  
  
## Syntax  
  
```  
  
class CClientDC : public CDC  
  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CClientDC::CClientDC](../Topic/CClientDC::CClientDC.md)|Erstellt ein Objekt, das `CClientDC` an `CWnd` verbunden ist.|  
  
### Geschützte Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CClientDC::m\_hWnd](../Topic/CClientDC::m_hWnd.md)|`HWND` des Fensters, für das dieses `CClientDC` gültig ist.|  
  
## Hinweise  
 Dies bedeutet, dass der Gerätekontext, der einem `CClientDC`\-Objekt zugeordnet, der Clientbereich eines Fensters ist.  
  
 Weitere Informationen zu `CClientDC`, finden Sie unter [Gerätekontexte](../../mfc/device-contexts.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDC](../../mfc/reference/cdc-class.md)  
  
 `CClientDC`  
  
## Anforderungen  
 **Header:** afxwin.h  
  
## Siehe auch  
 [MFC\-Beispiel MDI](../../top/visual-cpp-samples.md)   
 [CDC\-Klasse](../../mfc/reference/cdc-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDC\-Klasse](../../mfc/reference/cdc-class.md)
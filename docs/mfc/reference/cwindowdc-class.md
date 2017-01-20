---
title: "CWindowDC Class"
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
  - "CWindowDC"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWindowDC class"
  - "device contexts, Fenster"
  - "screen output classes"
ms.assetid: 876a3641-4cde-471c-b0d1-fe58b32af79c
caps.latest.revision: 22
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# CWindowDC Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Abgeleitet von `CDC`.  
  
## Syntax  
  
```  
class CWindowDC : public CDC  
```  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CWindowDC::CWindowDC](../Topic/CWindowDC::CWindowDC.md)|Erstellt ein `CWindowDC`\-Objekt.|  
  
### Geschützte Datenmember  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CWindowDC::m\_hWnd](../Topic/CWindowDC::m_hWnd.md)|Das `HWND`, an das `CWindowDC` angefügt ist.|  
  
## Hinweise  
 Ruft die Windows\-Funktion [GetWindowDC](http://msdn.microsoft.com/library/windows/desktop/dd144947\(v=vs.85\).aspx) zur Konstruktionszeit und [ReleaseDC](http://msdn.microsoft.com/library/windows/desktop/dd162920\(v=vs.85\).aspx) zur Zerstörungszeit auf.  Dies bedeutet, dass ein `CWindowDC`\-Objekt auf den ganzen Bildschirmbereich eines [CWnd](../../mfc/reference/cwnd-class.md)\-Elements zugreift \(sowohl Client als auch Nicht\-Client\-Bereiche\).  
  
 Weitere Informationen über die Verwendung von `CWindowDC` finden Sie unter [Gerätekontexte](../../mfc/device-contexts.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDC](../../mfc/reference/cdc-class.md)  
  
 `CWindowDC`  
  
## Anforderungen  
 Header: afxwin.h  
  
## Siehe auch  
 [CDC\-Klasse](../../mfc/reference/cdc-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDC\-Klasse](../../mfc/reference/cdc-class.md)
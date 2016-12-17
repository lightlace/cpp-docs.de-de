---
title: "CPaintDC Class"
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
  - "CPaintDC"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPaintDC class"
  - "OnPaint handler"
  - "WM_PAINT message"
ms.assetid: 7e245baa-bf9b-403e-a637-7218adf28fab
caps.latest.revision: 22
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# CPaintDC Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine Gerätekontextklasse wird von abgeleitet [CDC](../../mfc/reference/cdc-class.md).  
  
## Syntax  
  
```  
class CPaintDC : public CDC  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CPaintDC::CPaintDC](../Topic/CPaintDC::CPaintDC.md)|Erstellt `CPaintDC`, das angegebene [CWnd](../../mfc/reference/cwnd-class.md) verbunden ist.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CPaintDC::m\_ps](../Topic/CPaintDC::m_ps.md)|Enthält [PAINTSTRUCT](../../mfc/reference/paintstruct-structure.md), das verwendet wird, um den Clientbereich zu zeichnen.|  
  
### Geschützte Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CPaintDC::m\_hWnd](../Topic/CPaintDC::m_hWnd.md)|`HWND`, zu denen dieses Objekt `CPaintDC` angefügt wird.|  
  
## Hinweise  
 Es wird [CWnd::BeginPaint](../Topic/CWnd::BeginPaint.md) zur Konstruktionszeit und [CWnd::EndPaint](../Topic/CWnd::EndPaint.md) an der Zerstörungszeit aus.  
  
 Ein Objekt `CPaintDC` kann bei der Reaktion nur verwendet werden [WM\_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213) auf eine Meldung, normalerweise in der `OnPaint` Meldungshandlermemberfunktion.  
  
 Weitere Informationen zur Verwendung von `CPaintDC`, finden Sie unter [Gerätekontexte](../../mfc/device-contexts.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDC](../../mfc/reference/cdc-class.md)  
  
 `CPaintDC`  
  
## Anforderungen  
 **Header:** afxwin.h  
  
## Siehe auch  
 [MFC Sampling MDI](../../top/visual-cpp-samples.md)   
 [CDC\-Klasse](../../mfc/reference/cdc-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)
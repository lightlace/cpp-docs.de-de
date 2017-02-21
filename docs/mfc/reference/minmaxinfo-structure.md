---
title: "MINMAXINFO-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MINMAXINFO"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MINMAXINFO-Struktur"
ms.assetid: be6fb578-f98a-4581-9ada-be9df308ed2f
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# MINMAXINFO-Struktur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `MINMAXINFO`\-Struktur enthält Informationen über die maximierte Größe eines Fensters und Position und die minimale und maximale Nachverfolgungsgröße.  
  
## Syntax  
  
```  
  
      typedef struct tagMINMAXINFO {  
   POINT ptReserved;  
   POINT ptMaxSize;  
   POINT ptMaxPosition;  
   POINT ptMinTrackSize;  
   POINT ptMaxTrackSize;  
} MINMAXINFO;  
```  
  
#### Parameter  
 *ptReserved*  
 Für die interne Verwendung vorgesehen.  
  
 *ptMaxSize*  
 Gibt der maximierten Breite \(point.x\) und der point.y maximierten \(Höhe\) des Fensters an.  
  
 `ptMaxPosition`  
 Gibt die Position der linken Seite des Fensters \(point.x maximierten\) und Position des oberen maximierten Fensters an \(point.y\).  
  
 *ptMinTrackSize*  
 Gibt die minimale Nachverfolgungsbreite \(point.x\) und die minimale Höhe verfolgenden \(point.y\) des Fensters an.  
  
 *ptMaxTrackSize*  
 Gibt die maximale Nachverfolgungsbreite \(point.x\) und der maximale verfolgenden Höhe \(point.y\) des Fensters an.  
  
## Anforderungen  
 **Header:** winuser.h  
  
## Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnGetMinMaxInfo](../Topic/CWnd::OnGetMinMaxInfo.md)
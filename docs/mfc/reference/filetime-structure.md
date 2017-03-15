---
title: "FILETIME-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "FILETIME"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "FILETIME-Structure"
ms.assetid: e09557e2-b6d7-4dd5-a5b9-6328bca88595
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# FILETIME-Struktur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `FILETIME`\-Struktur ist ein 64\-Bit\-Wert, der die Anzahl der Intervall von 100 Nanosekunden seit dem 1. Januar 1601 darstellt.  
  
## Syntax  
  
```  
  
      typedef struct _FILETIME {  
   DWORD dwLowDateTime;   /* low 32 bits  */  
   DWORD dwHighDateTime;  /* high 32 bits */  
} FILETIME, *PFILETIME, *LPFILETIME;  
```  
  
#### Parameter  
 *dwLowDateTime*  
 Gibt die Bits des Tiefs 32 der Dateizeit an.  
  
 *dwHighDateTime*  
 Gibt die Bits des Wichtigkeitswert 32 der Dateizeit an.  
  
## Anforderungen  
 **Header:** windef.h  
  
## Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CTime::CTime](../Topic/CTime::CTime.md)
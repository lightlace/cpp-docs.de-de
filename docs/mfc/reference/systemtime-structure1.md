---
title: "SYSTEMTIME-Struktur"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "SYSTEMTIME"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SYSTEMTIME-Struktur"
ms.assetid: 9aaef4d6-de79-4fa1-8158-86b245ef5bff
caps.latest.revision: 15
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# SYSTEMTIME-Struktur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Struktur `SYSTEMTIME` stellt ein Datum und eine Uhrzeit dar, mit jeweils einzelnen Membern für Monat, Tag, Jahr, Wochentag, Stunde, Minute, Sekunde und Millisekunde.  
  
## Syntax  
  
```  
  
      typedef struct _SYSTEMTIME {  
   WORD wYear;  
   WORD wMonth;  
   WORD wDayOfWeek;  
   WORD wDay;  
   WORD wHour;  
   WORD wMinute;  
   WORD wSecond;  
   WORD wMilliseconds;  
} SYSTEMTIME;  
```  
  
#### Parameter  
 *wYear*  
 Das aktuelle Jahr.  
  
 *wMonth*  
 Der aktuelle Monat; Januar ist 1.  
  
 *wDayOfWeek*  
 Der aktuelle Wochentag; Sonntag ist 0, Montag ist 1, usw.  
  
 *wDay*  
 Der aktuelle Tag des Monats.  
  
 *wHour*  
 Die aktuelle Stunde.  
  
 *wMinute*  
 Die aktuelle Minute.  
  
 *wSecond*  
 Der aktuelle Sekunde.  
  
 *wMilliseconds*  
 Die aktuelle Millisekunde.  
  
## Beispiel  
 [!CODE [NVC_MFC_Utilities#39](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_Utilities#39)]  
  
## Anforderungen  
 **Header:** winbase.h  
  
## Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CTime::CTime](../Topic/CTime::CTime.md)
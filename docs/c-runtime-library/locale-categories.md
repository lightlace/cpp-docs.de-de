---
title: "Gebietsschemakategorien | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "LC_MAX"
  - "LC_MIN"
  - "LC_MONETARY"
  - "LC_TIME"
  - "LC_NUMERIC"
  - "LC_COLLATE"
  - "LC_CTYPE"
  - "LC_ALL"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LC_ALL-Konstante"
  - "LC_COLLATE-Konstante"
  - "LC_CTYPE-Konstante"
  - "LC_MAX-Konstante"
  - "LC_MIN-Konstante"
  - "LC_MONETARY-Konstante"
  - "LC_NUMERIC-Konstante"
  - "LC_TIME-Konstante"
  - "Lokale Konstanten"
ms.assetid: 868f1493-fe5d-4722-acab-bfcd374a063a
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Gebietsschemakategorien
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntax  
  
```  
  
#include <locale.h>  
  
```  
  
## Hinweise  
 Gebietsschemakategorien sind die Manifestkonstanten, die von der Lokalisierungsroutinen verwendet werden, um anzugeben, die Teil Gebietsschemainformationen eines Programms verwendet wird.  Das Gebietsschema bezeichnet die Stelle an \(oder Land\/Region\) für die bestimmte Aspekte des Programms angepasst werden können.  vom Gebietsschema Bereichseinschließung, beispielsweise, die Formatierung von Datumsangaben oder Währungsformat.  
  
|Gebietsschemakategorie|Teile des Programms auswirken|  
|----------------------------|-----------------------------------|  
|`LC_ALL`|Alle gebietsschemaspezifische Verhalten \(alle Kategorien\)|  
|`LC_COLLATE`|Verhalten von `strcoll` und `strxfrm`\-Funktionen|  
|`LC_CTYPE`|Verhalten der ZeichenBehandlung funktioniert \(bis **isdigit**, `isxdigit`, `mbstowcs` und `mbtowc`, die unverändert sind\)|  
|`LC_MAX`|Identisch mit `LC_TIME`|  
|`LC_MIN`|Identisch mit `LC_ALL`|  
|`LC_MONETARY`|Währungsformatierungsinformationen zurückgegeben durch die `localeconv`\-Funktion|  
|`LC_NUMERIC`|Dezimaltrennzeichenzeichen für formatierte Ausgabeprogramme \(beispielsweise, `printf`\), Datenkonvertierungsroutinen und die nicht\-monetären Formatierungsinformationen von Funktion `localeconv` zurückgegeben|  
|`LC_TIME`|Verhalten der `strftime`\-Funktion|  
  
 Ein Beispiel finden Sie unter [setlocale, \_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md).  
  
## Siehe auch  
 [localeconv](../c-runtime-library/reference/localeconv.md)   
 [setlocale, \_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [strcoll\-Funktionen](../c-runtime-library/strcoll-functions.md)   
 [strftime, wcsftime, \_strftime\_l, \_wcsftime\_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)   
 [strxfrm, wcsxfrm, \_strxfrm\_l, \_wcsxfrm\_l](../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)   
 [Globale Konstanten](../c-runtime-library/global-constants.md)
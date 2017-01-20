---
title: "_daylight, _dstbias, _timezone und _tzname"
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
  - "tzname"
  - "_timezone"
  - "timezone"
  - "_daylight"
  - "_tzname"
  - "daylight"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Zeitzonen"
  - "Anpassungen der Uhrzeit"
  - "Zeitzonenvariablen"
  - "_tzname-Funktion"
  - "_daylight-Funktion"
  - "_timezone-Funktion"
  - "daylight-Funktion"
  - "Anpassungen der lokalen Zeit"
  - "Zeitzonenfunktion"
  - "tzname-Funktion"
  - "Zeitzonenvariablen"
ms.assetid: d06c7292-6b99-4aba-b284-16a96570c856
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# _daylight, _dstbias, _timezone und _tzname
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`_daylight`, `_dstbias`, `_timezone` und `_tzname` werden in einigen Zeitraum und Datumsroutinen, Ortszeitanpassungen vorzunehmen verwendet.  Diese globalen Variablen sind für die sichereren funktionalen Versionen veraltet, die anstelle der globalen Variablen verwendet werden sollten.  
  
|Globale Variable|Funktionale Entsprechung|  
|----------------------|------------------------------|  
|`_daylight`|[\_get\_daylight](../c-runtime-library/reference/get-daylight.md)|  
|`_dstbias`|[\_get\_dstbias](../c-runtime-library/reference/get-dstbias.md)|  
|`_timezone`|[\_get\_timezone](../c-runtime-library/reference/get-timezone.md)|  
|`_tzname`|[\_get\_tzname](../c-runtime-library/reference/get-tzname.md)|  
  
 Sie werden in Time.h folgendermaßen deklariert.  
  
## Syntax  
  
```  
extern int _daylight;   
extern int _dstbias;   
extern long _timezone;   
extern char *_tzname[2];  
```  
  
## Hinweise  
 Auf einem Aufruf an `_ftime`, werden `localtime` oder `_tzset`, die Werte von `_daylight`, `_dstbias`, `_timezone` und `_tzname` vom Wert der Umgebungsvariablen `TZ` bestimmt.  Wenn Sie nicht explizit den Wert `TZ` festlegen, enthalten `_tzname[0]` und `_tzname[1]` die Standardeinstellungen "von PST" und "PDT" bzw.  Die Zeitmanipulationsfunktionen \([\_tzset](../c-runtime-library/reference/tzset.md), [\_ftime](../c-runtime-library/reference/ftime-ftime32-ftime64.md) und [localtime](../c-runtime-library/reference/localtime-localtime32-localtime64.md)\) versuchen, die Werte von `_daylight`, `_dstbias` und `_timezone` festlegen, die das Betriebssystem für den Standardwert jeder Variable abfragen.  Die globalen Variablenwerte der Zeitzone werden in der folgenden Tabelle dargestellt.  
  
|Variable|Wert|  
|--------------|----------|  
|`_daylight`|Wert ungleich 0 \(null\), wenn Sommerzeit \(dst\)\- Zone in `TZ` angegeben wird oder vom Betriebssystem ab; andernfalls 0.  Der Standardwert ist 1.|  
|`_dstbias`|Offset für Sommerzeit.|  
|`_timezone`|Unterschied in Sekunden zwischen koordinierter Weltzeit und Ortszeit.  Der Standardwert ist 28,800.|  
|`_tzname[0]`|Zeitzonenname ist von der `TZ` \- Umgebungsvariable.  Der Standardwert ist "PST".|  
|`_tzname[1]`|DST\-Zonenname berechnete von der Umgebungsvariablen `TZ`.  Der Standardwert ist "PDT" \(pazifische Sommerzeit\).|  
  
## Siehe auch  
 [Globale Variablen](../c-runtime-library/global-variables.md)   
 [\_get\_daylight](../c-runtime-library/reference/get-daylight.md)   
 [\_get\_dstbias](../c-runtime-library/reference/get-dstbias.md)   
 [\_get\_timezone](../c-runtime-library/reference/get-timezone.md)   
 [\_get\_tzname](../c-runtime-library/reference/get-tzname.md)
---
title: "Globale Variablen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.variables"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Globale Variablen"
  - "Globale Variablen, Microsoft -Laufzeitbibliothek"
  - "Variablen, Global"
ms.assetid: 01d1551c-2f0c-4f72-935c-6442caccf84f
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# Globale Variablen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Microsoft C\-Laufzeitbibliothek bietet die folgenden globalen Variablen oder Makros.  Mehrere dieser globalen Variablen oder Makros sind veraltet und wurden durch sicherere, funktionsbereite Versionen ersetzt, die Sie anstelle der globalen Variablen verwenden sollten.  
  
|Variable|Beschreibung|  
|--------------|------------------|  
|[\_\_argc, \_\_argv, \_\_wargv](../c-runtime-library/argc-argv-wargv.md)|Enthält die Befehlszeilenargumente.|  
|[\_daylight, \_dstbias, \_timezone und \_tzname](../c-runtime-library/daylight-dstbias-timezone-and-tzname.md)|Veraltet.  Verwenden Sie stattdessen `_get_daylight`, `_get_dstbias`, `_get_timezone` und `_get_tzname`.<br /><br /> Wird an die lokale Zeit angepasst und in einigen Datums\- und Zeitfunktionen verwendet.|  
|[errno, \_doserrno, \_sys\_errlist und \_sys\_nerr](../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)|Veraltet.  Verwenden Sie stattdessen `_get_errno`, `_set_errno`, `_get_doserrno`, `_set_doserrno`, `perror` und `strerror`.<br /><br /> Speichert Fehlercodes und damit zusammenhängende Informationen.|  
|[\_environ, \_wenviron](../c-runtime-library/environ-wenviron.md)|Veraltet.  Verwenden Sie stattdessen `getenv_s`, `_wgetenv_s`, `_dupenv_s`, `_wdupenv_s`, `_putenv_s` und `_wputenv_s`.<br /><br /> Zeiger zu Arrays mit Zeigern zu den Prozessumgebungszeichenfolgen, Initialisierung beim Starten.|  
|[\_fmode](../c-runtime-library/fmode.md)|Veraltet.  Verwenden Sie stattdessen `_get_fmode` oder `_set_fmode`.<br /><br /> Legt Standard\-Dateiübersetzungsmodus fest.|  
|[\_iob](../c-runtime-library/iob.md)|Array mit E\/A\-Steuerungsstruktur für die Konsole, Dateien und Geräte.|  
|[\_pctype, \_pwctype, \_wctype, \_mbctype, \_mbcasemap](../c-runtime-library/pctype-pwctype-wctype-mbctype-mbcasemap.md)|Enthält Informationen, die von den Zeichenklassifizierungsfunktionen verwendet werden.|  
|[\_pgmptr, \_wpgmptr](../c-runtime-library/pgmptr-wpgmptr.md)|Veraltet.  Verwenden Sie stattdessen `_get_pgmptr` oder `_get_wpgmptr`.<br /><br /> Initialisiert beim Programmstart mit dem vollqualifizierten oder relativen Pfad des Programms, dem vollständigen Programmnamen oder dem Programmnamen ohne Dateinamenerweiterung, abhängig davon, wie das Programm aufgerufen wurde.|  
  
## Siehe auch  
 [C\-Laufzeitbibliotheksverweis](../c-runtime-library/c-run-time-library-reference.md)   
 [Globale Konstanten](../c-runtime-library/global-constants.md)   
 [\_\_argc, \_\_argv, \_\_wargv](../c-runtime-library/argc-argv-wargv.md)   
 [\_get\_daylight](../c-runtime-library/reference/get-daylight.md)   
 [\_get\_dstbias](../c-runtime-library/reference/get-dstbias.md)   
 [\_get\_timezone](../c-runtime-library/reference/get-timezone.md)   
 [\_get\_tzname](../c-runtime-library/reference/get-tzname.md)   
 [perror](../c-runtime-library/reference/perror-wperror.md)   
 [strerror](../c-runtime-library/reference/strerror-strerror-wcserror-wcserror.md)   
 [\_get\_doserrno](../c-runtime-library/reference/get-doserrno.md)   
 [\_set\_doserrno](../c-runtime-library/reference/set-doserrno.md)   
 [\_get\_errno](../c-runtime-library/reference/get-errno.md)   
 [\_set\_errno](../c-runtime-library/reference/set-errno.md)   
 [\_dupenv\_s, \_wdupenv\_s](../c-runtime-library/reference/dupenv-s-wdupenv-s.md)   
 [getenv, \_wgetenv](../c-runtime-library/reference/getenv-wgetenv.md)   
 [getenv\_s, \_wgetenv\_s](../c-runtime-library/reference/getenv-s-wgetenv-s.md)   
 [\_putenv, \_wputenv](../c-runtime-library/reference/putenv-wputenv.md)   
 [\_putenv\_s, \_wputenv\_s](../c-runtime-library/reference/putenv-s-wputenv-s.md)   
 [\_get\_fmode](../c-runtime-library/reference/get-fmode.md)   
 [\_set\_fmode](../c-runtime-library/reference/set-fmode.md)
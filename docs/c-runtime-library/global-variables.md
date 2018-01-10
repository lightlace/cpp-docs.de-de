---
title: Globale Variablen | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: c.variables
dev_langs: C++
helpviewer_keywords:
- global variables
- variables, global
- global variables, Microsoft run-time library
ms.assetid: 01d1551c-2f0c-4f72-935c-6442caccf84f
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fec44138379e3510f353f0fdd99f7a6a1905f9cc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="global-variables"></a>Globale Variablen
Die Microsoft C-Laufzeitbibliothek bietet die folgenden globalen Variablen oder Makros. Mehrere dieser globalen Variablen oder Makros sind veraltet und wurden durch sicherere, funktionsbereite Versionen ersetzt, die Sie anstelle der globalen Variablen verwenden sollten.  
  
|Variable|description|  
|--------------|-----------------|  
|[__argc, \__argv, \__wargv](../c-runtime-library/argc-argv-wargv.md)|Enthält die Befehlszeilenargumente.|  
|[_daylight, _dstbias, _timezone, and _tzname](../c-runtime-library/daylight-dstbias-timezone-and-tzname.md)|Veraltet. Verwenden Sie stattdessen `_get_daylight`, `_get_dstbias`, `_get_timezone` und `_get_tzname`.<br /><br /> Wird an die lokale Zeit angepasst und in einigen Datums- und Zeitfunktionen verwendet.|  
|[errno, _doserrno, _sys_errlist, and _sys_nerr](../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)|Veraltet. Verwenden Sie stattdessen `_get_errno`, `_set_errno`, `_get_doserrno`, `_set_doserrno`, `perror` und `strerror`.<br /><br /> Speichert Fehlercodes und damit zusammenhängende Informationen.|  
|[_environ, _wenviron](../c-runtime-library/environ-wenviron.md)|Veraltet. Verwenden Sie stattdessen `getenv_s`, `_wgetenv_s`, `_dupenv_s`, `_wdupenv_s`, `_putenv_s` und `_wputenv_s`.<br /><br /> Zeiger zu Arrays mit Zeigern zu den Prozessumgebungszeichenfolgen, Initialisierung beim Starten.|  
|[_fmode](../c-runtime-library/fmode.md)|Veraltet. Verwenden Sie stattdessen `_get_fmode` oder `_set_fmode`.<br /><br /> Legt Standard-Dateiübersetzungsmodus fest.|  
|[_iob](../c-runtime-library/iob.md)|Array mit E/A-Steuerungsstruktur für die Konsole, Dateien und Geräte.|  
|[_pctype, _pwctype, _wctype, _mbctype, _mbcasemap](../c-runtime-library/pctype-pwctype-wctype-mbctype-mbcasemap.md)|Enthält Informationen, die von den Zeichenklassifizierungsfunktionen verwendet werden.|  
|[_pgmptr, _wpgmptr](../c-runtime-library/pgmptr-wpgmptr.md)|Veraltet. Verwenden Sie stattdessen `_get_pgmptr` oder `_get_wpgmptr`.<br /><br /> Initialisiert beim Programmstart mit dem vollqualifizierten oder relativen Pfad des Programms, dem vollständigen Programmnamen oder dem Programmnamen ohne Dateierweiterung, abhängig davon, wie das Programm aufgerufen wurde.|  
  
## <a name="see-also"></a>Siehe auch  
 [C-Laufzeitbibliotheksreferenz](../c-runtime-library/c-run-time-library-reference.md)   
 [Global Constants (Globale Konstanten)](../c-runtime-library/global-constants.md)   
 [__argc, \__argv, \__wargv](../c-runtime-library/argc-argv-wargv.md)   
 [_get_daylight](../c-runtime-library/reference/get-daylight.md)   
 [_get_dstbias](../c-runtime-library/reference/get-dstbias.md)   
 [_get_timezone](../c-runtime-library/reference/get-timezone.md)   
 [_get_tzname](../c-runtime-library/reference/get-tzname.md)   
 [perror](../c-runtime-library/reference/perror-wperror.md)   
 [strerror](../c-runtime-library/reference/strerror-strerror-wcserror-wcserror.md)   
 [_get_doserrno](../c-runtime-library/reference/get-doserrno.md)   
 [_set_doserrno](../c-runtime-library/reference/set-doserrno.md)   
 [_get_errno](../c-runtime-library/reference/get-errno.md)   
 [_set_errno](../c-runtime-library/reference/set-errno.md)   
 [_dupenv_s, _wdupenv_s](../c-runtime-library/reference/dupenv-s-wdupenv-s.md)   
 [getenv, _wgetenv](../c-runtime-library/reference/getenv-wgetenv.md)   
 [getenv_s, _wgetenv_s](../c-runtime-library/reference/getenv-s-wgetenv-s.md)   
 [_putenv, _wputenv](../c-runtime-library/reference/putenv-wputenv.md)   
 [_putenv_s, _wputenv_s](../c-runtime-library/reference/putenv-s-wputenv-s.md)   
 [_get_fmode](../c-runtime-library/reference/get-fmode.md)   
 [_set_fmode](../c-runtime-library/reference/set-fmode.md)
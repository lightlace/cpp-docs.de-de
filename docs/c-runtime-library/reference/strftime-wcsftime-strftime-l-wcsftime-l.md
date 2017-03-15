---
title: "strftime, wcsftime, _strftime_l, _wcsftime_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "strftime"
  - "_wcsftime_l"
  - "_strftime_l"
  - "wcsftime"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-time-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_tcsftime"
  - "strftime"
  - "wcsftime"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_strftime_l-Funktion"
  - "strftime-Funktion"
  - "tcsftime-Funktion"
  - "_wcsftime_l-Funktion"
  - "wcsftime-Funktion"
  - "_tcsftime-Funktion"
  - "Uhrzeitzeichenfolgen"
ms.assetid: 6330ff20-4729-4c4a-82af-932915d893ea
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# strftime, wcsftime, _strftime_l, _wcsftime_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Formatieren Sie eine Zeitzeichenfolge.  
  
## Syntax  
  
```  
size_t strftime(  
   char *strDest,  
   size_t maxsize,  
   const char *format,  
   const struct tm *timeptr   
);  
size_t _strftime_l(  
   char *strDest,  
   size_t maxsize,  
   const char *format,  
   const struct tm *timeptr,  
   _locale_t locale  
);  
size_t wcsftime(  
   wchar_t *strDest,  
   size_t maxsize,  
   const wchar_t *format,  
   const struct tm *timeptr   
);  
size_t _wcsftime_l(  
   wchar_t *strDest,  
   size_t maxsize,  
   const wchar_t *format,  
   const struct tm *timeptr,  
   _locale_t locale  
);  
```  
  
#### Parameter  
 `strDest`  
 Ausgabezeichenfolge.  
  
 `maxsize`  
 Größe des Puffers `strDest`, gemessen in Zeichen \(`char` oder `wchart_t`\).  
  
 `format`  
 Formatsteuerzeichenfolge.  
  
 `timeptr`  
 `tm` Datenstruktur.  
  
 `locale`  
 Das zu verwendende Gebietsschema.  
  
## Rückgabewert  
 `strftime` gibt die Anzahl von Zeichen zurück, die in `strDest` abgelegt werden und `wcsftime` gibt die entsprechende Anzahl der Breitzeichen zurück.  
  
 Wenn die Gesamtanzahl der Zeichen, einschließlich das abschließende NULL\-Zeichen, mehr als ist, geben `maxsize`, `strftime` und `wcsftime` 0 zurück und der Inhalt von `strDest` ist unbestimmt.  
  
 Die Anzahl der Zeichen in `strDest` entspricht der Anzahl von Literalzeichen in `format` sowie sämtliche Zeichen, die möglicherweise über `format` Formatierungscodes hinzugefügt werden.  Das abschließende NULL\-Zeichen eine Zeichenfolge ist jedoch im Rückgabewert gezählt.  
  
## Hinweise  
 Die Funktionen `strftime` und `wcsftime` formatieren den Zeitwert `tm` in `timeptr` entsprechend dem angegebenen `format`\-Argument und Ergebnisse im Puffer `strDest`*.* Auf höchster `maxsize` werden Zeichen in der Zeichenfolge angeordnet.  Eine Beschreibung der Felder in der `timeptr`\-Struktur, finden Sie unter [asctime](../../c-runtime-library/reference/asctime-wasctime.md).  `wcsftime` ist die Breitzeichenentsprechung von `strftime`; die ZeichenfolgeZeigerargumentpunkte in eine Zeichenfolge mit Breitzeichen.  Anderenfalls verhalten sich diese Funktionen identisch.  
  
> [!NOTE]
>  In Versionen vor Visual C\+\+ 2005, wurde die Dokumentation jeweils `format` als Parameter von `wcsftime`, der Datentyp `const wchar_t *` lassen, aber die tatsächliche Implementierung des Datentyps `format` war `const char *`.  Die Implementierung des Datentyps `format` wurde aktualisiert, um die vorherige aktuelle und Dokumentation h. `const wchar_t *` an.  
  
 Diese Funktion überprüft ihre Parameter.  Wenn `strDest`, `format` oder `timeptr` ein NULL\-Zeiger ist, oder wenn die Datenstruktur `tm`, die von `timeptr` behandelt wird, nicht gültig ist \(beispielsweise, wenn es aus Bereichswerten für die Zeit oder das Datum out enthält\) oder die Zeichenfolge `format` ein ungültiger Formatierungscode enthält, wird der ungültige Parameterhandler aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, gibt die Funktion 0 zurück und stellt `errno` auf `EINVAL` ein.  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_tcsftime`|`strftime`|`strftime`|`wcsftime`|  
  
 Das `format`\-Argument besteht aus mindestens Codes; wie in `printf`, werden die Formatierungscodes von einem Prozentzeichen \(`%`\) vorangestellt.  Zeichen, die nicht mit `%` beginnen, werden unverändert in das `strDest` kopiert *.* Die `LC_TIME` Kategorie des aktuellen Gebietsschemas beeinflusst die Ausgabeformatierung von `strftime`. \(Weitere Informationen zu `LC_TIME`, finden Sie unter [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).\) Die Features ohne das Suffix `_l` verwenden das gerade angegebene Gebietsschema.  Die Versionen dieser Funktionen mit dem Suffix `_l` sind identisch, allerdings wird das Gebietsschema als Parameter verwenden und die aktuell festgelegten anstelle des Gebietsschemas.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
 Die Formatierungscodes für `strftime` sind nachfolgend aufgeführt:  
  
 `%a`  
 Abgekürzter Wochentagsname  
  
 `%A`  
 Vollständiger Wochentagsname  
  
 `%b`  
 Abgekürzter Monatsname  
  
 `%B`  
 Vollständiger Monatsname  
  
 `%c`  
 Datums\- und Zeitdarstellung entsprechend für Gebietsschema  
  
 `%d`  
 Tag des Monats als Dezimalzahl \(01 \- 31\)  
  
 `%H`  
 24 Stunde im der Stil \(00 \- 23\)  
  
 `%I`  
 12 Stunde in einem \-Stunden\-Format \(01 \- 12\)  
  
 `%j`  
 Tag des Jahres als Dezimalzahl \(001 \- 366\)  
  
 `%m`  
 Monat als Dezimalzahl \(01 \- 12\)  
  
 `%M`  
 Minute als Dezimalzahl \(00 \- 59\)  
  
 `%p`  
 Aktueller Uhr\-\/Uhrindikator des Gebietsschemas für 12\-Stunden\-Format  
  
 `%S`  
 Zweite als Dezimalzahl \(00 \- 59\)  
  
 `%U`  
 Woche des Jahres als Dezimalzahl, mit Sonntag als ersten Tag der Woche \(00 \- 53\)  
  
 `%w`  
 Wochentag als Dezimalzahl \(0 \- 6; Sonntag ist 0\)  
  
 `%W`  
 Woche des Jahres als Dezimalzahl, mit Montag als ersten Tag der Woche \(00 \- 53\)  
  
 `%x`  
 Datumsdarstellung für aktuelle Gebietsschema  
  
 `%X`  
 Zeitdarstellung für aktuelle Gebietsschema  
  
 `%y`  
 Jahr ohne Jahrhundert, als Dezimalzahl \(00 \- 99\)  
  
 `%Y`  
 Jahr mit Jahrhundert, als Dezimalzahl  
  
 `%z, %Z`  
 Jedes der Zeitzonenname oder die Zeitzonenabkürzung, abhängig von Registrierungseinstellungen; keine Zeichen, wenn Zeitzone nicht bekannt ist  
  
 `%%`  
 Prozentzeichen  
  
 Wie in der Funktion `printf`, kann das `#`\-Flag jeden Formatierungscode voran.  In diesem Fall wird die Bedeutung des Formatcodes wie folgt geändert.  
  
|Formatcode|Bedeutung|  
|----------------|---------------|  
|`%#a, %#A, %#b, %#B, %#p, %#X, %#z, %#Z, %#%`|`#`\-Flag wird ignoriert.|  
|`%#c`|Lange Datums\- und Zeitdarstellung, verwenden für aktuelle Gebietsschema.  Zum Beispiel: "Am Dienstag, den 14. März 1995, 12:41: 29 ".|  
|`%#x`|Lange Datumsdarstellung, verwenden dem aktuellen Gebietsschema.  Zum Beispiel: "Am Dienstag, den 14. März 1995".|  
|`%#d, %#H, %#I, %#j, %#m, %#M, %#S, %#U, %#w, %#W, %#y, %#Y`|Entfernen Sie führende Nullen \(falls vorhanden\).|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`strftime`|\<time.h\>|  
|`wcsftime`|\<time.h oder\> wchar.h \<\>|  
|`_strftime_l`|\<time.h\>|  
|`_wcsftime_l`|\<time.h oder\> wchar.h \<\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
 Im Beispiel für [time](../../c-runtime-library/reference/time-time32-time64.md).  
  
## .NET Framework-Entsprechung  
  
-   [System::DateTime::ToLongDateString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongdatestring.aspx)  
  
-   [System::DateTime::ToLongTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongtimestring.aspx)  
  
-   [System::DateTime::ToShortDateString](https://msdn.microsoft.com/en-us/library/system.datetime.toshortdatestring.aspx)  
  
-   [System::DateTime::ToShortTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.toshorttimestring.aspx)  
  
-   [System::DateTime::ToString](https://msdn.microsoft.com/en-us/library/system.datetime.tostring.aspx)  
  
## Siehe auch  
 [Locale](../../c-runtime-library/locale.md)   
 [Uhrzeitverwaltung](../../c-runtime-library/time-management.md)   
 [Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [strcoll\-Funktionen](../../c-runtime-library/strcoll-functions.md)   
 [strxfrm, wcsxfrm, \_strxfrm\_l, \_wcsxfrm\_l](../../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)
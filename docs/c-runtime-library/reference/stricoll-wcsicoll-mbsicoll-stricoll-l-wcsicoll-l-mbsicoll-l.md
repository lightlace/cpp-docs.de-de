---
title: "_stricoll, _wcsicoll, _mbsicoll, _stricoll_l, _wcsicoll_l, _mbsicoll_l"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "_mbsicoll_l"
  - "_stricoll_l"
  - "_mbsicoll"
  - "_wcsicoll_l"
  - "_wcsicoll"
  - "_stricoll"
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
  - "api-ms-win-crt-multibyte-l1-1-0.dll"
  - "api-ms-win-crt-string-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "stricoll"
  - "_stricoll"
  - "_wcsicoll"
  - "mbsicoll_l"
  - "_mbsicoll"
  - "_ftcsicoll"
  - "wcsicoll_l"
  - "_tcsicoll"
  - "mbsicoll"
  - "stricoll_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ftcsicoll-Funktion"
  - "_mbsicoll-Funktion"
  - "_mbsicoll_l-Funktion"
  - "_stricoll-Funktion"
  - "_stricoll_l-Funktion"
  - "_tcsicoll-Funktion"
  - "_wcsicoll-Funktion"
  - "Codepages, Verwenden für Zeichenfolgevergleiche"
  - "ftcsicoll-Funktion"
  - "mbsicoll-Funktion"
  - "mbsicoll_l-Funktion"
  - "stricoll-Funktion"
  - "stricoll_l-Funktion"
  - "Zeichenfolgenvergleich [C++], Kulturspezifisch"
  - "Zeichenfolgen [C++], Vergleichen nach Codepage"
  - "tcsicoll-Funktion"
ms.assetid: 8ec93016-5a49-49d2-930f-721566661d82
caps.latest.revision: 22
caps.handback.revision: "22"
ms.author: "corob"
manager: "ghogen"
---
# _stricoll, _wcsicoll, _mbsicoll, _stricoll_l, _wcsicoll_l, _mbsicoll_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vergleicht Zeichenfolgen mithilfe gebietsschemaspezifischen Informationen.  
  
> [!IMPORTANT]
>  `_mbsicoll` und `_mbsicoll_l` können nicht in Anwendungen verwendet werden, die in Windows\-Runtime ausgeführt werden.  Weitere Informationen finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
int _stricoll(  
   const char *string1,  
   const char *string2   
);  
int _wcsicoll(  
   const wchar_t *string1,  
   const wchar_t *string2   
);  
int _mbsicoll(  
   const unsigned char *string1,  
   const unsigned char *string2   
);  
int _stricoll_l(  
   const char *string1,  
   const char *string2,  
   _locale_t locale  
);  
int _wcsicoll_l(  
   const wchar_t *string1,  
   const wchar_t *string2,  
   _locale_t locale  
);  
int _mbsicoll_l(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   _locale_t locale  
);  
```  
  
#### Parameter  
 `string1, string2`  
 Zu vergleichende mit NULL endende Zeichenfolgen.  
  
 `locale`  
 Das zu verwendende Gebietsschema.  
  
## Rückgabewert  
 Jede dieser Funktionen gibt einen Wert zurück, der die Beziehung zwischen `string1` mit `string2`*,* wie folgt angibt.  
  
|Rückgabewert|Verhältnis von string1 zu string2|  
|------------------|---------------------------------------|  
|\< 0|`string1` kleiner als `string2`|  
|0|`string1` identisch mit `string2`|  
|\> 0|`string1` größer als `string2`|  
|`_NLSCMPERROR`|Es ist ein Fehler aufgetreten.|  
  
 Jede dieser Funktion gibt `_NLSCMPERROR` zurück.  Um `_NLSCMPERROR` zu verwenden, nehmen Sie entweder `STRING.H` oder `MBSTRING.H` auf.  `_wcsicoll` kann fehlschlagen, wenn `string1` oder `string2` NULL ist oder Codes mit Breitzeichen außerhalb der Domäne der Sortierreihenfolge enthält.  Wenn ein Fehler auftritt, legt `_wcsicoll``errno` möglicherweise auf `EINVAL` fest.  Um einen Aufruf von `_wcsicoll` auf einen Fehler zu überprüfen, legen Sie `errno` auf 0 fest, und überprüfen Sie dann `errno`, nachdem Sie `_wcsicoll` aufgerufen haben.  
  
## Hinweise  
 Jede dieser Funktionen vergleicht `string1` und `string2` ohne Beachtung der Groß\-\/Kleinschreibung entsprechend der derzeit verwendeten Codepage.  Diese Funktionen sollten nur verwendet werden, wenn es in der aktuellen Codepage einen Unterschied zwischen der Reihenfolge des Zeichensatzes und der lexikografischen Reihenfolge gibt, und dieser Unterschied für den Zeichenfolgenvergleich relevant ist.  
  
 `_stricmp` unterscheidet sich dadurch von `_stricoll`, dass der `_stricmp`\-Vergleich von `LC_CTYPE` beeinflusst wird, während der `_stricoll`\-Vergleich den Kategorien `LC_CTYPE` und `LC_COLLATE` des Gebietsschemas entspricht.  Weitere Informationen zur `LC_COLLATE`\-Kategorie finden Sie unter [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md) und [Gebietsschemakategorien](../../c-runtime-library/locale-categories.md).  Die Versionen dieser Funktionen ohne das `_l`\-Suffix verwenden das aktuelle Gebietsschema. Die Versionen mit dem `_l`\-Suffix sind beinahe identisch, verwenden jedoch stattdessen das ihnen übergebene Gebietsschema.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
 Mit allen diesen Funktionen werden ihre Parameter überprüft.  Wenn entweder `string1` oder `string2``NULL`\-Zeiger sind, wird der Handler für ungültige Parameter aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, geben diese Funktionen `_NLSCMPERROR` zurück und stellen `errno` auf `EINVAL` ein.  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_tcsicoll`|`_stricoll`|`_mbsicoll`|`_wcsicoll`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_stricoll`, `_stricoll_l`|\<string.h\>|  
|`_wcsicoll`, `_wcsicoll_l`|\<wchar.h\>, \<string.h\>|  
|`_mbsicoll`, `_mbsicoll_l`|\<mbstring.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## .NET Framework-Entsprechung  
 [System::String::Compare](https://msdn.microsoft.com/en-us/library/system.string.compare.aspx)  
  
## Siehe auch  
 [Locale](../../c-runtime-library/locale.md)   
 [Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)   
 [strcoll\-Funktionen](../../c-runtime-library/strcoll-functions.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [\_mbsnbcoll, \_mbsnbcoll\_l, \_mbsnbicoll, \_mbsnbicoll\_l](../../c-runtime-library/reference/mbsnbcoll-mbsnbcoll-l-mbsnbicoll-mbsnbicoll-l.md)   
 [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [strcmp, wcscmp, \_mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [\_stricmp, \_wcsicmp, \_mbsicmp, \_stricmp\_l, \_wcsicmp\_l, \_mbsicmp\_l](../../c-runtime-library/reference/stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)   
 [strncmp, wcsncmp, \_mbsncmp, \_mbsncmp\_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [\_strnicmp, \_wcsnicmp, \_mbsnicmp, \_strnicmp\_l, \_wcsnicmp\_l, \_mbsnicmp\_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strxfrm, wcsxfrm, \_strxfrm\_l, \_wcsxfrm\_l](../../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)
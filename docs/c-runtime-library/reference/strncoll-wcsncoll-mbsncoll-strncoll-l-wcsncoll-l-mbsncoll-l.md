---
title: "_strncoll, _wcsncoll, _mbsncoll, _strncoll_l, _wcsncoll_l, _mbsncoll_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_strncoll"
  - "_mbsncoll_l"
  - "_wcsncoll"
  - "_wcsncoll_l"
  - "_mbsncoll"
  - "_strncoll_l"
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
  - "mbsncoll_l"
  - "strncoll"
  - "_wcsncoll"
  - "_tcsnccoll"
  - "_ftcsnccoll"
  - "wcsncoll"
  - "_mbsncoll"
  - "wcsncoll_l"
  - "strncoll_l"
  - "_ftcsncoll"
  - "_strncoll"
  - "_tcsncoll"
  - "mbsncoll"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ftcsnccoll-Funktion"
  - "_ftcsncoll-Funktion"
  - "_mbsncoll-Funktion"
  - "_mbsncoll_l-Funktion"
  - "_strncoll-Funktion"
  - "_strncoll_l-Funktion"
  - "_tcsnccoll-Funktion"
  - "_tcsncoll-Funktion"
  - "_wcsncoll-Funktion"
  - "_wcsncoll_l-Funktion"
  - "Codepages, Verwenden für Zeichenfolgevergleiche"
  - "ftcsnccoll-Funktion"
  - "ftcsncoll-Funktion"
  - "mbsncoll-Funktion"
  - "mbsncoll_l-Funktion"
  - "Zeichenfolgen [C++], Vergleichen nach Codepage"
  - "strncoll-Funktion"
  - "strncoll_l-Funktion"
  - "tcsnccoll-Funktion"
  - "tcsncoll-Funktion"
  - "wcsncoll-Funktion"
  - "wcsncoll_l-Funktion"
ms.assetid: e659a5a4-8afe-4033-8e72-17ffd4bdd8e9
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# _strncoll, _wcsncoll, _mbsncoll, _strncoll_l, _wcsncoll_l, _mbsncoll_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vergleicht Zeichenfolgen mithilfe gebietsschemaspezifischen Informationen.  
  
> [!IMPORTANT]
>  `_mbsncoll` und `_mbsncoll_l` können in Anwendungen, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausgeführt werden, nicht verwendet werden.  Weitere Informationen finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
int _strncoll(  
   const char *string1,  
   const char *string2,  
   size_t count   
);  
int _wcsncoll(  
   const wchar_t *string1,  
   const wchar_t *string2,  
   size_t count   
);  
int _mbsncoll(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count   
);  
int _strncoll_l(  
   const char *string1,  
   const char *string2,  
   size_t count,  
   _locale_t locale  
);  
int _wcsncoll_l(  
   const wchar_t *string1,  
   const wchar_t *string2,  
   size_t count,  
   _locale_t locale  
);  
int _mbsncoll_l(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count,  
   _locale_t locale  
);  
```  
  
#### Parameter  
 `string1, string2`  
 Zu vergleichende mit NULL endende Zeichenfolgen.  
  
 `count`  
 Die Anzahl der zu vergleichenden Zeichen.  
  
 `locale`  
 Das zu verwendende Gebietsschema.  
  
## Rückgabewert  
 Jede dieser Funktionen gibt einen Wert zurück, der die Beziehung der Teilzeichenfolgen von `string1` und `string2` wie folgt angibt.  
  
|Rückgabewert|Verhältnis von string1 zu string2|  
|------------------|---------------------------------------|  
|\< 0|`string1` ist kleiner als `string2`.|  
|0|`string1` ist identisch mit `string2`.|  
|\> 0|`string1` ist größer als `string2`.|  
  
 Jede dieser Funktion gibt `_NLSCMPERROR` zurück.  Um `_NLSCMPERROR` zu verwenden, fügen Sie STRING.h oder MBSTRING.h ein.  `_wcsncoll` kann fehlschlagen, wenn `string1` oder `string2` NULL ist oder Codes mit Breitzeichen außerhalb der Domäne der Sortierreihenfolge enthält.  Wenn ein Fehler auftritt, legt `_wcsncoll``errno` möglicherweise auf `EINVAL` fest.  Um einen Aufruf von `_wcsncoll` auf einen Fehler zu überprüfen, legen Sie `errno` auf 0 fest, und überprüfen Sie dann `errno`, nachdem Sie `_wcsncoll` aufgerufen haben.  
  
## Hinweise  
 Entsprechend der aktuell verwendeten Codepage vergleicht jede dieser Funktionen ohne Berücksichtigung der Groß\- und Kleinschreibung die ersten `count`\-Zeichen in `string1` und `string2`.  Diese Funktionen sollten nur verwendet werden, wenn es in der Codepage einen Unterschied zwischen der Reihenfolge des Zeichensatzes und der lexikografischen Reihenfolge gibt, und dieser Unterschied für den Zeichenfolgenvergleich relevant ist.  Die Reihenfolge des Zeichensatzes ist vom Gebietsschema abhängig.  Die Versionen dieser Funktionen ohne das `_l`\-Suffix verwenden das aktuelle Gebietsschemas, aber die Versionen mit dem `_l`\-Suffix verwenden das übergebene Gebietsschema.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
 Mit allen diesen Funktionen werden ihre Parameter überprüft.  Wenn entweder `string1` oder `string2` ein NULL\-Zeiger ist oder wenn`count` größer als `INT_MAX` ist, wird der Handler für ungültige Parameter aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, geben diese Funktionen `_NLSCMPERROR` zurück und stellen `errno` auf `EINVAL` ein.  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE und \_MBCS nicht definiert.|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|-------------------------------------------|----------------------|-------------------------|  
|`_tcsnccoll`|`_strncoll`|`_mbsncoll`|`_wcsncoll`|  
|`_tcsncoll`|`_strncoll`|[\_mbsnbcoll](../../c-runtime-library/reference/mbsnbcoll-mbsnbcoll-l-mbsnbicoll-mbsnbicoll-l.md)|`_wcsncoll`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_strncoll`, `_strncoll_l`|\<string.h\>|  
|`_wcsncoll`, `_wcsncoll_l`|\<wchar.h\> oder \<string.h\>|  
|`_mbsncoll`, `_mbsncoll_l`|\<mbstring.h\>|  
  
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
---
title: "strcoll, wcscoll, _mbscoll, _strcoll_l, _wcscoll_l, _mbscoll_l"
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
  - "wcscoll"
  - "_mbscoll"
  - "_mbscoll_l"
  - "strcoll"
  - "_strcoll_l"
  - "_wcscoll_l"
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
  - "wcscoll"
  - "_mbscoll"
  - "_tcscoll"
  - "_ftcscoll"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Codepages, Verwenden für Zeichenfolgevergleiche"
  - "mbscoll-Funktion"
  - "wcscoll_l-Funktion"
  - "ftcscoll-Funktion"
  - "wcscoll-Funktion"
  - "_strcoll_l-Funktion"
  - "tcscoll-Funktion"
  - "_ftcscoll-Funktion"
  - "_tcscoll-Funktion"
  - "_wcscoll_l-Funktion"
  - "_mbscoll-Funktion"
  - "strcoll_l-Funktion"
  - "strcoll-Funktionen"
  - "Zeichenfolgen [C++], Vergleichen nach Codepage"
ms.assetid: 900a7540-c7ec-4c2f-b292-7a85f63e3fe8
caps.latest.revision: 20
caps.handback.revision: "20"
ms.author: "corob"
manager: "ghogen"
---
# strcoll, wcscoll, _mbscoll, _strcoll_l, _wcscoll_l, _mbscoll_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vergleicht Zeichenfolgen mithilfe des aktuellen Gebietsschemas oder einer angegebenen LC\_COLLATE\-Konvertierungszustandskategorie.  
  
> [!IMPORTANT]
>  `_mbscoll` und `_mbscoll_l` können nicht in Anwendungen verwendet werden, die in Windows\-Runtime ausgeführt werden.  Weitere Informationen finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
int strcoll(  
   const char *string1,  
   const char *string2   
);  
int wcscoll(  
   const wchar_t *string1,  
   const wchar_t *string2   
);  
int _mbscoll(  
   const unsigned char *string1,  
   const unsigned char *string2   
);  
int _strcoll_l(  
   const char *string1,  
   const char *string2,  
   _locale_t locale   
);  
int wcscoll_l(  
   const wchar_t *string1,  
   const wchar_t *string2,  
   _locale_t locale   
);  
int _mbscoll_l(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   _locale_t locale   
);  
```  
  
#### Parameter  
 `string1`, `string2`  
 Zu vergleichende mit NULL endende Zeichenfolgen.  
  
 `locale`  
 Zu verwendendes Gebietsschema.  
  
## Rückgabewert  
 Jede dieser Funktionen gibt einen Wert zurück, der die Beziehung zwischen `string1` mit `string2`*,* wie folgt angibt.  
  
|Rückgabewert|Verhältnis von string1 zu string2|  
|------------------|---------------------------------------|  
|\< 0|`string1` kleiner als `string2`|  
|0|`string1` identisch mit `string2`|  
|\> 0|`string1` größer als `string2`|  
  
 Jede dieser Funktionen gibt bei einem Fehler `_NLSCMPERROR` zurück.  Um `_NLSCMPERROR` zu verwenden, fügen Sie entweder STRING.H oder MBSTRING.H. ein.  `wcscoll` kann fehlschlagen, wenn `string1` oder `string2` NULL ist oder Codes mit Breitzeichen außerhalb der Domäne der Sortierreihenfolge enthält.  Wenn ein Fehler auftritt, legt `wcscoll``errno` möglicherweise auf `EINVAL` fest.  Um einen Aufruf von `wcscoll` auf einen Fehler zu überprüfen, legen Sie `errno` auf 0 fest, und überprüfen Sie dann `errno`, nachdem Sie `wcscoll` aufgerufen haben.  
  
## Hinweise  
 Jede dieser Funktionen vergleicht `string1` und `string2` unter Beachtung der Groß\-\/Kleinschreibung entsprechend der derzeit verwendeten Codepage.  Diese Funktionen sollten nur verwendet werden, wenn es in der aktuellen Codepage einen Unterschied zwischen der Reihenfolge des Zeichensatzes und der lexikografischen Reihenfolge gibt, und dieser Unterschied für den Zeichenfolgenvergleich relevant ist.  
  
 Mit allen diesen Funktionen werden ihre Parameter überprüft.  Wenn entweder `string1` oder `string2` ein NULL\-Zeiger ist oder wenn `count` größer als `INT_MAX` ist, wird der Handler für ungültige Parameter aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, geben diese Funktionen `_NLSCMPERROR` zurück und stellen `errno` auf `EINVAL` ein.  
  
 Der Vergleich der beiden Zeichenfolgen ist ein gebietsschemaabhängiger Vorgang, da jedes Gebietsschema andere Regeln für die Sortierung von Zeichen besitzt.  Die Versionen dieser Funktionen ohne das `_l`\-Suffix verwenden für dieses gebietsschemaabhängige Verhalten das aktuelle Gebietsschema des Threads. Die Versionen mit dem `_l`\-Suffix sind mit der entsprechenden Funktion ohne Suffix identisch, verwenden jedoch den ihnen übergebenen Gebietsschemaparameter anstelle des aktuellen Gebietsschemas.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_tcscoll`|`strcoll`|`_mbscoll`|`wcscoll`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`strcoll`|\<string.h\>|  
|`wcscoll`|\<wchar.h\>, \<string.h\>|  
|`_mbscoll`, `_mbscoll_l`|\<mbstring.h\>|  
|`_strcoll_l`|\<string.h\>|  
|`_wcscoll_l`|\<wchar.h\>, \<string.h\>|  
  
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
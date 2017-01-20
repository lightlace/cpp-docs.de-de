---
title: "_mbsnbcoll, _mbsnbcoll_l, _mbsnbicoll, _mbsnbicoll_l"
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
  - "_mbsnbicoll_l"
  - "_mbsnbcoll_l"
  - "_mbsnbcoll"
  - "_mbsnbicoll"
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
apitype: "DLLExport"
f1_keywords: 
  - "mbsnbicoll"
  - "mbsnbcoll"
  - "mbsnbicoll_l"
  - "_mbsnbcoll"
  - "_mbsnbicoll"
  - "_ftcsnicoll"
  - "_ftcsncoll"
  - "mbsnbcoll_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mbsnbcoll-Funktion"
  - "_mbsnbcoll_l-Funktion"
  - "_mbsnbicoll-Funktion"
  - "_mbsnbicoll_l-Funktion"
  - "_tcsncoll-Funktion"
  - "_tcsnicoll-Funktion"
  - "mbsnbcoll-Funktion"
  - "mbsnbcoll_l-Funktion"
  - "mbsnbicoll-Funktion"
  - "mbsnbicoll_l-Funktion"
  - "tcsncoll-Funktion"
  - "tcsnicoll-Funktion"
ms.assetid: d139ed63-ccba-4458-baa2-61cbcef03e94
caps.latest.revision: 21
caps.handback.revision: "21"
ms.author: "corob"
manager: "ghogen"
---
# _mbsnbcoll, _mbsnbcoll_l, _mbsnbicoll, _mbsnbicoll_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vergleicht `n` Bytes von zwei Multibyte\-Zeichenfolgen mithilfe von Multibyte\-Codepage\-Informationen.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows\-Runtime ausgeführt werden.  Weitere Informationen finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
int _mbsnbcoll(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count   
);  
int _mbsnbcoll_l(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count,  
   _locale_t locale  
);  
int _mbsnbicoll(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count   
);  
int _mbsnbicoll_l(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count,  
   _locale_t locale  
);  
```  
  
#### Parameter  
 `string1, string2`  
 Zu vergleichende Zeichenfolgen.  
  
 `count`  
 Anzahl der zu vergleichenden Bytes.  
  
 `locale`  
 Zu verwendendes Gebietsschema.  
  
## Rückgabewert  
 Der Rückgabewert gibt die Beziehung der untergeordneten Zeichenfolgen von `string1` und `string2` an.  
  
|Rückgabewert|**Beschreibung**|  
|------------------|----------------------|  
|\< 0|Die untergeordnete Zeichenfolge `string1` ist kleiner als die untergeordnete Zeichenfolge `string2`.|  
|0|Die untergeordnete Zeichenfolge `string1` ist mit der untergeordneten Zeichenfolge `string2` identisch.|  
|\> 0|Die untergeordnete Zeichenfolge `string1` ist größer als die untergeordnete Zeichenfolge `string2`.|  
  
 Wenn `string1` oder `string2` gleich `NULL` ist oder `count` größer als `INT_MAX` ist, wird der Handler für ungültige Parameter aufgerufen \(siehe [Parametervalidierung](../../c-runtime-library/parameter-validation.md)\).  Wenn die weitere Ausführung zugelassen wird, geben diese Funktionen `_NLSCMPERROR` zurück und stellen `errno` auf `EINVAL` ein.  Um `_NLSCMPERROR` zu verwenden, fügen Sie entweder String.h oder Mbstring.h ein.  
  
## Hinweise  
 Jede dieser Funktionen sortiert höchstens die ersten `count`\-Bytes in `string1` und `string2` und gibt einen Wert zurück, der die Beziehung zwischen den resultierenden untergeordneten Zeichenfolgen von `string1` und `string2` angibt.  Wenn das endgültige Byte der Teilzeichenfolge von `string1` oder `string2` ein führendes Byte ist, ist es nicht Teil des Vergleichs. Diese Funktionen vergleichen nur vollständige Zeichen in den untergeordneten Zeichenfolgen.  `_mbsnbicoll` ist eine Version von `_mbsnbcoll` ohne Berücksichtigung von Groß\- und Kleinschreibung.  Wie `_mbsnbcmp` und `_mbsnbicmp` sortieren `_mbsnbcoll` und `_mbsnbicoll` die beiden Multibyte\-Zeichenfolgen entsprechend der lexikografischen Reihenfolge, die von der aktuell verwendeten Multibyte\-[Codepage](../../c-runtime-library/code-pages.md) angegeben wird.  
  
 Bei manchen Codepages und entsprechenden Zeichensätzen kann die Reihenfolge der Zeichen im Zeichensatz möglicherweise von der lexikografischen Reihenfolge abweichen.  Im "C "\-Gebietsschema ist dies nicht der Fall: Die Reihenfolge der Zeichen im ASCII\-Zeichensatz entspricht der lexikografischen Reihenfolge der Zeichen.  In bestimmten europäischen Codepages beispielsweise steht im Zeichensatz das Zeichen "a" \(Wert 0x61\) vor dem Zeichen "ä" \(Wert 0xE4\), das Zeichen "ä" steht lexikografisch gesehen jedoch vor dem Zeichen "a".  Um in solch einem Fall einen lexikografischen Vergleich von Zeichenfolgen nach Bytes durchzuführen, verwenden Sie `_mbsnbcoll` anstelle von `_mbsnbcmp`, und um nur die Zeichenfolgengleichheit zu überprüfen, verwenden Sie `_mbsnbcmp`.  
  
 Da die `coll`\-Funktionen Zeichenfolgen für Vergleiche lexikografisch sortieren, während die `cmp`\-Funktionen nur die Zeichenfolgengleichheit testen, sind die `coll`\-Funktionen wesentlich langsamer als die entsprechenden `cmp`\-Versionen.  Daher sollten die `coll`\-Funktionen nur verwendet werden, wenn es in der aktuellen Codepage einen Unterschied zwischen der Reihenfolge des Zeichensatzes und der lexikografischen Reihenfolge gibt, und dieser Unterschied für den Zeichenfolgenvergleich relevant ist.  
  
 Der Ausgabewert ist von der `LC_CTYPE`\-Kategorieneinstellung des Gebietsschemas betroffen; weitere Informationen finden Sie unter [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).  Die Versionen dieser Funktionen ohne das `_l`\-Suffix verwenden das aktuelle Gebietsschema für dieses vom Gebietsschema abhängige Verhalten; die Versionen mit dem `_l`\-Suffix sind beinahe identisch, verwenden jedoch stattdessen den ihnen übergebenen Gebietsschemaparameter.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
### Zuordnung generischer Textroutinen  
  
|Tchar.h\-Routine|\_UNICODE und \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|------------------------------------------|----------------------|-------------------------|  
|`_tcsncoll`|[\_strncoll](../../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|`_mbsnbcoll`|[\_wcsncoll](../../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|  
|`_tcsncoll_l`|[\_strncoll, \_wcsncoll, \_mbsncoll, \_strncoll\_l, \_wcsncoll\_l, \_mbsncoll\_l](../../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|`_mbsnbcoll_l`|[\_wcsncoll\_l](../../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|  
|`_tcsnicoll`|[\_strnicoll](../../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|`_mbsnbicoll`|[\_wcsnicoll](../../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|  
|`_tcsnicoll_l`|[\_strnicoll\_l](../../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|`_mbsnbicoll_l`|[\_wcsnicoll\_l](../../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_mbsnbcoll`|\<mbstring.h\>|  
|`_mbsnbcoll_l`|\<mbstring.h\>|  
|`_mbsnbicoll`|\<mbstring.h\>|  
|`_mbsnbicoll_l`|\<mbstring.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Siehe auch  
 [Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)   
 [\_mbsnbcat, \_mbsnbcat\_l](../../c-runtime-library/reference/mbsnbcat-mbsnbcat-l.md)   
 [\_mbsnbcmp, \_mbsnbcmp\_l](../../c-runtime-library/reference/mbsnbcmp-mbsnbcmp-l.md)   
 [\_mbsnbicmp, \_mbsnbicmp\_l](../../c-runtime-library/reference/mbsnbicmp-mbsnbicmp-l.md)   
 [strcoll\-Funktionen](../../c-runtime-library/strcoll-functions.md)   
 [strncmp, wcsncmp, \_mbsncmp, \_mbsncmp\_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [\_strnicmp, \_wcsnicmp, \_mbsnicmp, \_strnicmp\_l, \_wcsnicmp\_l, \_mbsnicmp\_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)
---
title: "_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l"
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
  - "_stricmp_l"
  - "_mbsicmp"
  - "_wcsicmp"
  - "_mbsicmp_l"
  - "_stricmp"
  - "_wcsicmp_l"
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
  - "_ftcsicmp"
  - "_stricmp"
  - "wcsicmp_l"
  - "_wcsicmp"
  - "_tcsicmp"
  - "_strcmpi"
  - "stricmp_l"
  - "_mbsicmp"
  - "_fstricmp"
  - "mbsicmp_l"
  - "mbsicmp"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_fstricmp-Funktion"
  - "_ftcsicmp-Funktion"
  - "_mbsicmp-Funktion"
  - "_mbsicmp_l-Funktion"
  - "_strcmpi-Funktion"
  - "_stricmp-Funktion"
  - "_stricmp_l-Funktion"
  - "_tcsicmp-Funktion"
  - "_wcsicmp-Funktion"
  - "_wcsicmp_l-Funktion"
  - "fstricmp-Funktion"
  - "ftcsicmp-Funktion"
  - "mbsicmp-Funktion"
  - "mbsicmp_l-Funktion"
  - "stricmp_l-Funktion"
  - "Zeichenfolgenvergleich [C++], Kleinbuchstaben"
  - "Zeichenfolgen [C++], Vergleichen"
  - "tcsicmp-Funktion"
  - "wcsicmp_l-Funktion"
ms.assetid: 0e1ee515-0d75-435a-a445-8875d4669b50
caps.latest.revision: 28
caps.handback.revision: "26"
ms.author: "corob"
manager: "ghogen"
---
# _stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Führt einen Vergleich von Zeichenfolgen ohne Beachtung der Groß\-\/Kleinschreibung durch.  
  
> [!IMPORTANT]
>  `_mbsicmp` und `_mbsicmp_l` können nicht in Anwendungen verwendet werden, die in Windows\-Runtime ausgeführt werden.  Weitere Informationen finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
int _stricmp(  
   const char *string1,  
   const char *string2   
);  
int _wcsicmp(  
   const wchar_t *string1,  
   const wchar_t *string2   
);  
int _mbsicmp(  
   const unsigned char *string1,  
   const unsigned char *string2   
);  
int _stricmp_l(  
   const char *string1,  
   const char *string2,  
   _locale_t locale  
);  
int _wcsicmp_l(  
   const wchar_t *string1,  
   const wchar_t *string2,  
   _locale_t locale  
);  
int _mbsicmp_l(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   _locale_t locale  
);  
```  
  
#### Parameter  
 `string1, string2`  
 Zu vergleichende mit NULL endende Zeichenfolgen.  
  
 `locale`  
 Zu verwendendes Gebietsschema.  
  
## Rückgabewert  
 Der Rückgabewert gibt die Beziehung zwischen `string1` und `string2` wie folgt an.  
  
|Rückgabewert|Beschreibung|  
|------------------|------------------|  
|\< 0|`string1` kleiner als `string2`|  
|0|`string1` identisch mit `string2`|  
|\> 0|`string1` größer als `string2`|  
  
 Bei einem Fehler gibt `_mbsicmp` `_NLSCMPERROR` zurück \(definiert in \<string.h\> und \<mbstring.h\>\).  
  
## Hinweise  
 Die `_stricmp`\-Funktion vergleicht der Reihe nach `string1` und `string2` nach dem Konvertieren jedes Zeichens in Kleinbuchstaben, und gibt einen Wert zurück, der ihre Beziehung angibt.  `_stricmp` unterscheidet sich von `_stricoll` dahingehend, dass der `_stricmp`\-Vergleich nur von `LC_CTYPE` beeinflusst wird, durch den bestimmt wird, welche Zeichen Großbuchstaben und welche Kleinbuchstaben sind.  Die `_stricoll`\-Funktion vergleicht Zeichenfolgen gemäß der Kategorien `LC_CTYPE` und `LC_COLLATE` des Gebietsschemas, das sowohl Groß\-\/Kleinschreibung als auch die Sortierreihenfolge umfasst.  Weitere Informationen zur `LC_COLLATE`\-Kategorie finden Sie unter [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md) und [Gebietsschemakategorien](../../c-runtime-library/locale-categories.md).  Die Versionen dieser Funktionen ohne das `_l`\-Suffix verwenden das aktuelle Gebietsschema für gebietsschemaabhängiges Verhalten.  Die Versionen mit dem Suffix sind identisch, verwenden allerdings das übergebene Gebietsschema.  Wenn das Gebietsschema nicht festgelegt wurde, wird das C\-Gebietsschema verwendet.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
> [!NOTE]
>  `_stricmp` entspricht `_strcmpi`.  Sie sind austauschbar, `_stricmp` ist jedoch der bevorzugte Standard.  
  
 Die `_strcmpi`\-Funktion entspricht `_stricmp` und wird nur aus Gründen der Abwärtskompatibilität bereitgestellt.  
  
 Da `_stricmp` Kleinbuchstabenvergleiche ausführt, kann es zu unerwartetem Verhalten kommen.  
  
 Um zu veranschaulichen, wann eine Groß\-\/Kleinschreibungskonvertierung durch `_stricmp` sich auf das Ergebnis eines Vergleichs auswirkt, wird angenommen, dass Sie über die beiden Zeichenfolgen JOHNSTON und JOHN\_HENRY verfügen.  Die Zeichenfolge JOHN\_HENRY gilt als kleiner als JOHNSTON, da der Unterstrich "\_" einen niedrigeren ASCII\-Wert als ein kleingeschriebenes "S" aufweist.  Tatsächlich gelten alle Zeichen, die einen ASCII\-Wert zwischen 91 und 96 aufweisen, als kleiner als jeder beliebige Buchstabe.  
  
 Wenn die [strcmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)\-Funktion anstelle von `_stricmp` verwendet wird, ist JOHN\_HENRY größer als JOHNSTON.  
  
 `_wcsicmp` und `_mbsicmp` sind Breitzeichen\- und Multibytezeichenversionen von `_stricmp`.  Die Argumente und der Rückgabewert von `_wcsicmp` sind Breitzeichen\-Zeichenfolgen; die von `_mbsicmp` sind Mehrbyte\-Zeichenfolgen.  `_mbsicmp` erkennt Multibyte\-Zeichenfolgen entsprechend der aktuellen Multibyte\-Codepage und gibt bei einem Fehler `_NLSCMPERROR` zurück.  Weitere Informationen finden Sie unter [Codepages](../../c-runtime-library/code-pages.md).  Diese drei Funktionen verhalten sich andernfalls identisch.  
  
 `_wcsicmp` und `wcscmp` verhalten sich identisch, außer dass `wcscmp` die Argumente nicht in Kleinbuchstaben konvertiert, bevor diese verglichen werden.  `_mbsicmp` und `_mbscmp` verhalten sich identisch, außer dass `_mbscmp` die Argumente nicht in Kleinbuchstaben konvertiert, bevor diese verglichen werden.  
  
 Sie müssen [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md) für `_wcsicmp` aufrufen, um mit Latin 1\-Zeichen zu arbeiten.  Das C\-Gebietsschema ist standardmäßig aktiviert, deshalb ist z. B. "ä" nicht identisch mit "Ä".  Rufen Sie `setlocale` mit einem anderen Gebietsschema als dem C\-Gebietsschema auf, bevor Sie `_wcsicmp` aufrufen.  Das folgende Beispiel zeigt, wie `_wcsicmp` vom Gebietsschema abhängt:  
  
```  
// crt_stricmp_locale.c  
#include <string.h>  
#include <stdio.h>  
#include <locale.h>  
  
int main() {  
   setlocale(LC_ALL,"C");   // in effect by default  
   printf("\n%d",_wcsicmp(L"ä", L"Ä"));   // compare fails  
   setlocale(LC_ALL,"");  
   printf("\n%d",_wcsicmp(L"ä", L"Ä"));   // compare succeeds  
}  
```  
  
 Eine Alternative besteht darin, [\_create\_locale, \_wcreate\_locale](../../c-runtime-library/reference/create-locale-wcreate-locale.md) aufzurufen und das zurückgegebene Gebietsschemaobjekt als Parameter an `_wcsicmp_l` zu übergeben.  
  
 Mit allen diesen Funktionen werden ihre Parameter überprüft.  Wenn entweder `string1` oder `string2` ein NULL\-Zeiger ist, wird, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben, der Handler für ungültige Parameter aufgerufen.  Wenn die weitere Ausführung zugelassen wird, geben diese Funktionen `_NLSCMPERROR` zurück und stellen `errno` auf `EINVAL` ein.  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE und \_MBCS nicht definiert.|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|-------------------------------------------|----------------------|-------------------------|  
|`_tcsicmp`|`_stricmp`|`_mbsicmp`|`_wcsicmp`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_stricmp`, `_stricmp_l`|\<string.h\>|  
|`_wcsicmp`, `_wcsicmp_l`|\<string.h\> oder \<wchar.h\>|  
|`_mbsicmp`, `_mbsicmp_l`|\<mbstring.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
  
```  
// crt_stricmp.c  
  
#include <string.h>  
#include <stdio.h>  
#include <stdlib.h>  
  
char string1[] = "The quick brown dog jumps over the lazy fox";  
char string2[] = "The QUICK brown dog jumps over the lazy fox";  
  
int main( void )  
{  
   char tmp[20];  
   int result;  
  
   // Case sensitive  
   printf( "Compare strings:\n   %s\n   %s\n\n", string1, string2 );  
   result = strcmp( string1, string2 );  
   if( result > 0 )  
      strcpy_s( tmp, _countof(tmp), "greater than" );  
   else if( result < 0 )  
      strcpy_s( tmp, _countof(tmp), "less than" );  
   else  
      strcpy_s( tmp, _countof(tmp), "equal to" );  
   printf( "   strcmp:   String 1 is %s string 2\n", tmp );  
  
   // Case insensitive (could use equivalent _stricmp)  
   result = _stricmp( string1, string2 );  
   if( result > 0 )  
      strcpy_s( tmp, _countof(tmp), "greater than" );  
   else if( result < 0 )  
      strcpy_s( tmp, _countof(tmp), "less than" );  
   else  
      strcpy_s( tmp, _countof(tmp), "equal to" );  
   printf( "   _stricmp:  String 1 is %s string 2\n", tmp );  
}  
```  
  
  **Zeichenfolgen vergleichen:**  
 **Der schnelle braune Hund springt über den faulen Fuchs.**  
 **Der SCHNELLE braune Hund springt über den faulen Fuchs.**  
 **strcmp:   Zeichenfolge 1 ist größer als Zeichenfolge 2**  
 **\_stricmp: Zeichenfolge 1 ist gleich Zeichenfolge 2**   
## .NET Framework-Entsprechung  
 [System::String::Compare](https://msdn.microsoft.com/en-us/library/system.string.compare.aspx)  
  
## Siehe auch  
 [Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)   
 [memcmp, wmemcmp](../../c-runtime-library/reference/memcmp-wmemcmp.md)   
 [\_memicmp, \_memicmp\_l](../../c-runtime-library/reference/memicmp-memicmp-l.md)   
 [strcmp, wcscmp, \_mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [strcoll\-Funktionen](../../c-runtime-library/strcoll-functions.md)   
 [strncmp, wcsncmp, \_mbsncmp, \_mbsncmp\_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [\_strnicmp, \_wcsnicmp, \_mbsnicmp, \_strnicmp\_l, \_wcsnicmp\_l, \_mbsnicmp\_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strrchr, wcsrchr, \_mbsrchr, \_mbsrchr\_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [\_strset, \_strset\_l, \_wcsset, \_wcsset\_l, \_mbsset, \_mbsset\_l](../../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)   
 [strspn, wcsspn, \_mbsspn, \_mbsspn\_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)
---
title: "strrchr, wcsrchr, _mbsrchr, _mbsrchr_l"
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
  - "strrchr"
  - "wcsrchr"
  - "_mbsrchr"
  - "_mbsrchr_l"
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
  - "_tcsrchr"
  - "_ftcsrchr"
  - "strrchr"
  - "wcsrchr"
  - "_mbsrchr"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ftcsrchr-Funktion"
  - "_mbsrchr-Funktion"
  - "_mbsrchr_l-Funktion"
  - "_tcsrchr-Funktion"
  - "Zeichen [C++], Überprüfen von"
  - "ftcsrchr-Funktion"
  - "mbsrchr-Funktion"
  - "mbsrchr_l-Funktion"
  - "Überprüfen von Zeichenfolgen"
  - "Zeichenfolgen [C++], Scannen"
  - "strrchr-Funktion"
  - "tcsrchr-Funktion"
  - "wcsrchr-Funktion"
ms.assetid: 75cf2664-758e-49bb-bf6b-8a139cd474d2
caps.latest.revision: 28
caps.handback.revision: "28"
ms.author: "corob"
manager: "ghogen"
---
# strrchr, wcsrchr, _mbsrchr, _mbsrchr_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Durchsucht eine Zeichenfolge nach dem letzten Vorkommen eines Zeichens.  
  
> [!IMPORTANT]
>  `_mbsrchr` und `_mbsrchr_l` können nicht in Anwendungen verwendet werden, die in Windows\-Runtime ausgeführt werden.  Weitere Informationen finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
char *strrchr(  
   const char *str,  
   int c   
); // C only  
char *strrchr(  
   char *str,  
   int c   
); // C++ only  
const char *strrchr(  
   const char *str,  
   int c   
); // C++ only  
wchar_t *wcsrchr(  
   const wchar_t *str,  
   wchar_t c   
); // C only  
wchar_t *wcsrchr(  
   wchar_t *str,  
   wchar_t c   
); // C++ only  
const wchar_t *wcsrchr(  
   const wchar_t *str,  
   wchar_t c   
); // C++ only  
unsigned char *_mbsrchr(  
   const unsigned char *str,  
   unsigned int c   
); // C only  
unsigned char *_mbsrchr(  
   unsigned char *str,  
   unsigned int c   
); // C++ only  
const unsigned char *_mbsrchr(  
   const unsigned char *str,  
   unsigned int c   
); // C++ only  
unsigned char *_mbsrchr_l(  
   const unsigned char *str,  
   unsigned int c,  
   _locale_t locale  
); // C only  
unsigned char *_mbsrchr_l(  
   unsigned char *str,  
   unsigned int c,  
   _locale_t locale  
); // C++ only  
const unsigned char *_mbsrchr_l(  
   const unsigned char *str,  
   unsigned int c,  
   _locale_t locale  
); // C++ only  
```  
  
#### Parameter  
 `str`  
 Zu suchende mit NULL endende Zeichenfolge.  
  
 `c`  
 Zu suchende Zeichen.  
  
 `locale`  
 Zu verwendendes Gebietsschema.  
  
## Rückgabewert  
 Gibt einen Zeiger auf das letzte Vorkommen von `c` in `str` oder `NULL`  zurück, wenn `c` nicht gefunden wird.  
  
## Hinweise  
 Die `strrchr`\-Funktion sucht das letzte Vorkommen von `c` \(konvertiert in `char`\) in `str`.  Die Suche enthält das abschließende NULL\-Zeichen.  
  
 `wcsrchr` und `_mbsrchr` sind Breitzeichen\- und Multibytezeichenversionen von `strrchr`.  Die Argumente und der Rückgabewert von `wcsrchr`  sind Breitzeichenzeichenfolgen; die von `_mbsrchr` sind Multibyte\-Zeichenfolgen.  
  
 In C akzeptieren diese Funktionen einen `const`\-Zeiger als erstes Argument.  In C\+\+ sind zwei Überladungen verfügbar.  Die Überladung, die einen Zeiger zu `const` akzeptiert, gibt einen Zeiger zu `const` zurück; die Version, die einen Zeiger auf Nicht\-`const` akzeptiert, gibt einen Zeiger auf Nicht\-`const` zurück.  Das Makro \_CONST\_CORRECT\_OVERLOADS wird definiert, wenn sowohl die `const`\-Version als auch die Nicht\-`const`\-Version dieser Funktionen verfügbar sind.  Wenn Sie das Nicht\-`const`\-Verhalten für beide C\+\+\-Überladungen benötigen, definieren Sie das Symbol \_CONST\_RETURN.  
  
 `_mbsrchr` überprüft die eigenen Parameter.  Wenn `str` den Wert `NULL` annimmt, wird der ungültige Parameterhandler, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben, aufgerufen.  Wenn die weitere Ausführung zugelassen wird, wird `errno`  auf `EINVAL`  festgelegt und `_mbsrchr`  gibt 0 zurück.  `strrchr` und `wcsrchr` überprüfen ihre Parameter nicht.  Diese drei Funktionen verhalten sich andernfalls identisch.  
  
 Die Ausgabewert ist von der Einstellung der `LC_CTYPE` \-Kategorieeinstellung des Gebietsschemas betroffen. Weitere Informationen finden Sie unter [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).  Die Versionen dieser Funktionen ohne das `_l`\-Suffix verwenden das aktuelle Gebietsschema für dieses vom Gebietsschema abhängige Verhalten; die Versionen mit dem `_l`\-Suffix sind beinahe identisch, verwenden jedoch stattdessen den ihnen übergebenen Gebietsschemaparameter.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_tcsrchr`|`strrchr`|`_mbsrchr`|`wcsrchr`|  
|**nicht verfügbar**|**nicht verfügbar**|`_mbsrchr_l`|**nicht verfügbar**|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`strrchr`|\<string.h\>|  
|`wcsrchr`|\<string.h\> oder \<wchar.h\>|  
|`_mbsrchr`, `_mbsrchr_l`|\<mbstring.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
 Ein Beispiel für die Verwendung `strrchr` finden Sie unter [strchr](../../c-runtime-library/reference/strchr-wcschr-mbschr-mbschr-l.md).  
  
## .NET Framework-Entsprechung  
 [System::String::LastIndexOf](https://msdn.microsoft.com/en-us/library/system.string.lastindexof.aspx)  
  
## Siehe auch  
 [Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [Interpretation von Mehrbytezeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [strchr, wcschr, \_mbschr, \_mbschr\_l](../../c-runtime-library/reference/strchr-wcschr-mbschr-mbschr-l.md)   
 [strcspn, wcscspn, \_mbscspn, \_mbscspn\_l](../../c-runtime-library/reference/strcspn-wcscspn-mbscspn-mbscspn-l.md)   
 [\_strnicmp, \_wcsnicmp, \_mbsnicmp, \_strnicmp\_l, \_wcsnicmp\_l, \_mbsnicmp\_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strpbrk, wcspbrk, \_mbspbrk, \_mbspbrk\_l](../../c-runtime-library/reference/strpbrk-wcspbrk-mbspbrk-mbspbrk-l.md)   
 [strspn, wcsspn, \_mbsspn, \_mbsspn\_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)
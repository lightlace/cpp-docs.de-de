---
title: "strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mbsncpy_s_l"
  - "wcsncpy_s"
  - "_strncpy_s_l"
  - "strncpy_s"
  - "_mbsncpy_s"
  - "_wcsncpy_s_l"
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
  - "_tcsncpy_s"
  - "_wcsncpy_s_l"
  - "strncpy_s"
  - "_strncpy_s_l"
  - "wcsncpy_s"
  - "_tcsncpy_s_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_mbsnbcpy_s-Funktion"
  - "_mbsnbcpy_s_l-Funktion"
  - "_strncpy_s_l-Funktion"
  - "_tcsncpy_s-Funktion"
  - "_tcsncpy_s_l-Funktion"
  - "_wcsncpy_s_l-Funktion"
  - "Kopieren von Zeichenfolgen"
  - "mbsncpy_s-Funktion"
  - "mbsncpy_s_l-Funktion"
  - "Zeichenfolgen [C++], Kopieren"
  - "strncpy_s-Funktion"
  - "strncpy_s_l-Funktion"
  - "wcsncpy_s-Funktion"
  - "wcsncpy_s_l-Funktion"
ms.assetid: a971c800-94d1-4d88-92f3-a2fe236a4546
caps.latest.revision: 47
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 47
---
# strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Kopiert Zeichen aus einer Zeichenfolge in eine andere.  Diese Versionen von [strncpy, \_strncpy\_l, wcsncpy, \_wcsncpy\_l, \_mbsncpy, \_mbsncpy\_l](../../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md) enthalten Sicherheitserweiterungen wie unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
> [!IMPORTANT]
>  `_mbsncpy_s` und `_mbsncpy_s_l` können nicht in Anwendungen verwendet werden, die in Windows\-Runtime ausgeführt werden.  Weitere Informationen finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
errno_t strncpy_s(  
   char *strDest,  
   size_t numberOfElements,  
   const char *strSource,  
   size_t count  
);  
errno_t _strncpy_s_l(  
   char *strDest,  
   size_t numberOfElements,  
   const char *strSource,  
   size_t count,  
   _locale_t locale  
);  
errno_t wcsncpy_s(  
   wchar_t *strDest,  
   size_t numberOfElements,  
   const wchar_t *strSource,  
   size_t count   
);  
errno_t _wcsncpy_s_l(  
   wchar_t *strDest,  
   size_t numberOfElements,  
   const wchar_t *strSource,  
   size_t count,  
   _locale_t locale  
);  
errno_t _mbsncpy_s(  
   unsigned char *strDest,  
   size_t numberOfElements,  
   const unsigned char *strSource,  
   size_t count   
);  
errno_t _mbsncpy_s_l(  
   unsigned char *strDest,  
   size_t numberOfElements,  
   const unsigned char *strSource,  
   size_t count,  
   locale_t locale  
);  
template <size_t size>  
errno_t strncpy_s(  
   char (&strDest)[size],  
   const char *strSource,  
   size_t count  
); // C++ only  
template <size_t size>  
errno_t _strncpy_s_l(  
   char (&strDest)[size],  
   const char *strSource,  
   size_t count,  
   _locale_t locale  
); // C++ only  
template <size_t size>  
errno_t wcsncpy_s(  
   wchar_t (&strDest)[size],  
   const wchar_t *strSource,  
   size_t count   
); // C++ only  
template <size_t size>  
errno_t _wcsncpy_s_l(  
   wchar_t (&strDest)[size],  
   const wchar_t *strSource,  
   size_t count,  
   _locale_t locale  
); // C++ only  
template <size_t size>  
errno_t _mbsncpy_s(  
   unsigned char (&strDest)[size],  
   const unsigned char *strSource,  
   size_t count   
); // C++ only  
template <size_t size>  
errno_t _mbsncpy_s_l(  
   unsigned char (&strDest)[size],  
   const unsigned char *strSource,  
   size_t count,  
   locale_t locale  
); // C++ only  
```  
  
#### Parameter  
 `strDest`  
 Zielzeichenfolge.  
  
 `numberOfElements`  
 Die Größe der Zielzeichenfolge in Zeichen.  
  
 `strSource`  
 Quellzeichenfolge.  
  
 `count`  
 Die Anzahl der zu kopierenden Zeichen oder [\_TRUNCATE](../../c-runtime-library/truncate.md).  
  
 `locale`  
 Das zu verwendende Gebietsschema.  
  
## Rückgabewert  
 Null wenn erfolgreich, `STRUNCATE` bei abgeschnittenen Daten, andernfalls ein Fehlercode.  
  
### Fehlerbedingungen  
  
|`strDest`|`numberOfElements`|`strSource`|Rückgabewert|Inhalt von `strDest`|  
|---------------|------------------------|-----------------|------------------|--------------------------|  
|`NULL`|any|any|`EINVAL`|nicht geändert|  
|any|any|`NULL`|`EINVAL`|`strDest`\[0\] auf 0 festgelegt|  
|any|0|any|`EINVAL`|nicht geändert|  
|nicht `NULL`|zu klein|any|`ERANGE`|`strDest`\[0\] auf 0 festgelegt|  
  
## Hinweise  
 Diese Funktionen versuchen, die ersten `D`\-Zeichen aus `strSource` nach `strDest` zu kopieren. `D` ist dabei geringer an `count` und die Länge von `strSource`.  Wenn diese `D`\-Zeichen in `strDest` passen \(dessen Größe als `numberOfElements` angegeben ist\) und noch Platz für einen NULL\-Terminator ist, dann werden diese Zeichen kopiert und ein abschließendes NULL\-Zeichen wird angefügt. Andernfalls wird `strDest`\[0\] auf das Nullzeichen festgelegt und der Handler für ungültige Parameter wird aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  
  
 Zu der oberen Aufführung gibt es eine Ausnahme.  Wenn `count``_TRUNCATE` ist, wird so viel von `strSource` wie in `strDest` passt kopiert, wobei noch Platz für das abschließende NULL\-Zeichen bleibt, das immer angefügt wird.  
  
 Beispiel:  
  
 `char dst[5];`  
  
 `strncpy_s(dst, 5, "a long string", 5);`  
  
 bedeutet, dass `strncpy_s` fünf Zeichen in einen fünf Bytes langen Puffer kopieren soll. Somit gäbe es keinen Platz für den NULL\-Terminator und `strncpy_s` weist der Zeichenfolge NULL zu und ruft den Handler für ungültige Parameter auf.  
  
 Wenn ein Abschneideverhalten erforderlich ist, verwenden Sie `_TRUNCATE` oder \(`size` – 1\):  
  
 `strncpy_s(dst, 5, "a long string", _TRUNCATE);`  
  
 `strncpy_s(dst, 5, "a long string", 4);`  
  
 Wenn – im Gegensatz zu `strncpy` – der Wert `count` größer als die Länge von `strSource` ist, dann wird die Zielzeichenfolge bis zur Länge von `count` NICHT mit NULL\-Zeichen aufgefüllt.  
  
 Wenn sich Quell\- und Zielzeichenfolgen überlappen, ist das Verhalten von `strncpy_s` undefiniert.  
  
 Wenn `strDest` oder `strSource` oder `NULL` ist oder `numberOfElements` 0 ist, wird der Handler für ungültige Parameter aufgerufen.  Wenn die weitere Ausführung zugelassen wird, gibt die Funktion `EINVAL` zurück und setzt `errno` auf `EINVAL`.  
  
 `wcsncpy_s` und `_mbsncpy_s` sind Breitzeichen\- und Multibytezeichenversionen von `strncpy_s`.  Die Argumente und der Rückgabewert von `wcsncpy_s` und `mbsncpy_s` unterscheiden sich entsprechend.  Diese sechs Funktionen verhalten sich andernfalls identisch.  
  
 Der Ausgabewert ist von der `LC_CTYPE`\-Kategorieneinstellung des Gebietsschemas betroffen; weitere Informationen finden Sie unter [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).  Die Versionen dieser Funktionen ohne das `_l`\-Suffix verwenden das aktuelle Gebietsschema für dieses vom Gebietsschema abhängige Verhalten; die Versionen mit dem `_l`\-Suffix sind beinahe identisch, verwenden jedoch stattdessen den ihnen übergebenen Gebietsschemaparameter.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
 In C\+\+ wird die Verwendung dieser Funktionen durch Vorlagenüberladungen vereinfacht; die Überladungen können automatisch Rückschlüsse auf die Pufferlänge ziehen \(wodurch kein Größenargument mehr angegeben werden muss\), und sie können automatisch die älteren, nicht sicheren Funktionen durch ihre neueren, sicheren Entsprechungen ersetzen.  Weitere Informationen finden Sie unter [Sichere Vorlagenüberladungen](../../c-runtime-library/secure-template-overloads.md).  
  
 Die Debugversionen dieser Funktionen füllen zunächst den Puffer mit "0xFD" auf.  Mit [\_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md) deaktivieren Sie dieses Verhalten.  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_tcsncpy_s`|`strncpy_s`|`_mbsnbcpy_s`|`wcsncpy_s`|  
|`_tcsncpy_s_l`|`_strncpy_s_l`|`_mbsnbcpy_s_l`|`_wcsncpy_s_l`|  
  
> [!NOTE]
>  \_strncpy\_s\_l, `_wcsncpy_s_l` und `_mbsncpy_s_l` haben keine Gebietsschemaabhängigkeit, werden nur für `_tcsncpy_s_l` bereitgestellt und sollen nicht direkt aufgerufen werden.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`strncpy_s`, `_strncpy_s_l`|\<string.h\>|  
|`wcsncpy_s`, `_wcsncpy_s_l`|\<string.h\> oder \<wchar.h\>|  
|`_mbsncpy_s`, `_mbsncpy_s_l`|\<mbstring.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
  
```  
// crt_strncpy_s_1.cpp  
// compile with: /MTd  
  
// these #defines enable secure template overloads  
// (see last part of Examples() below)  
#define _CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES 1   
#define _CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT 1  
  
#include <stdio.h>  
#include <stdlib.h>  
#include <string.h>  
#include <crtdbg.h>  // For _CrtSetReportMode  
#include <errno.h>  
  
// This example uses a 10-byte destination buffer.  
  
errno_t strncpy_s_tester( const char * src,  
                          int count )  
{  
   char dest[10];  
  
   printf( "\n" );  
  
   if ( count == _TRUNCATE )  
      printf( "Copying '%s' to %d-byte buffer dest with truncation semantics\n",  
               src, _countof(dest) );  
   else  
      printf( "Copying %d chars of '%s' to %d-byte buffer dest\n",  
              count, src, _countof(dest) );  
  
   errno_t err = strncpy_s( dest, _countof(dest), src, count );  
  
   printf( "    new contents of dest: '%s'\n", dest );  
  
   return err;  
}  
  
void Examples()  
{  
   strncpy_s_tester( "howdy", 4 );  
   strncpy_s_tester( "howdy", 5 );  
   strncpy_s_tester( "howdy", 6 );  
  
   printf( "\nDestination buffer too small:\n" );  
   strncpy_s_tester( "Hi there!!", 10 );  
  
   printf( "\nTruncation examples:\n" );  
  
   errno_t err = strncpy_s_tester( "How do you do?", _TRUNCATE );  
   printf( "    truncation %s occur\n", err == STRUNCATE ? "did"  
                                                       : "did not" );  
  
   err = strncpy_s_tester( "Howdy.", _TRUNCATE );  
   printf( "    truncation %s occur\n", err == STRUNCATE ? "did"  
                                                       : "did not" );  
  
   printf( "\nSecure template overload example:\n" );  
  
   char dest[10];  
   strncpy( dest, "very very very long", 15 );  
   // With secure template overloads enabled (see #defines at  
   // top of file), the preceding line is replaced by  
   //    strncpy_s( dest, _countof(dest), "very very very long", 15 );  
   // Instead of causing a buffer overrun, strncpy_s invokes  
   // the invalid parameter handler.  
   // If secure template overloads were disabled, strncpy would  
   // copy 15 characters and overrun the dest buffer.  
   printf( "    new contents of dest: '%s'\n", dest );  
}  
  
void myInvalidParameterHandler(  
   const wchar_t* expression,  
   const wchar_t* function,   
   const wchar_t* file,   
   unsigned int line,   
   uintptr_t pReserved)  
{  
   wprintf(L"Invalid parameter handler invoked: %s\n", expression);  
}  
  
int main( void )  
{  
   _invalid_parameter_handler oldHandler, newHandler;  
  
   newHandler = myInvalidParameterHandler;  
   oldHandler = _set_invalid_parameter_handler(newHandler);  
   // Disable the message box for assertions.  
   _CrtSetReportMode(_CRT_ASSERT, 0);  
  
   Examples();  
}  
```  
  
  **Copying 4 chars of 'howdy' to 10\-byte buffer dest**  
 **new contents of dest: 'howd'**  
**Copying 5 chars of 'howdy' to 10\-byte buffer dest**  
 **new contents of dest: 'howdy'**  
**Copying 6 chars of 'howdy' to 10\-byte buffer dest**  
 **new contents of dest: 'howdy'**  
**Destination buffer too small:**  
**Copying 10 chars of 'Hi there\!\!' to 10\-byte buffer dest**  
**Invalid parameter handler invoked: \(L"Buffer is too small" && 0\)**  
 **new contents of dest: ''**  
**Truncation examples:**  
**Copying 'How do you do?' to 10\-byte buffer dest with truncation semantics**  
 **new contents of dest: 'How do yo'**  
 **truncation did occur**  
**Copying 'Howdy.' to 10\-byte buffer dest with truncation semantics**  
 **new contents of dest: 'Howdy.'**  
 **truncation did not occur**  
**Secure template overload example:**  
**Invalid parameter handler invoked: \(L"Buffer is too small" && 0\)**  
 **new contents of dest: ''**   
## Beispiel  
  
```  
// crt_strncpy_s_2.c  
// contrasts strncpy and strncpy_s  
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   char a[20] = "test";  
   char s[20];  
  
   // simple strncpy usage:  
  
   strcpy_s( s, 20, "dogs like cats" );  
   printf( "Original string:\n   '%s'\n", s );  
  
   // Here we can't use strncpy_s since we don't   
   // want null termination  
   strncpy( s, "mice", 4 );  
   printf( "After strncpy (no null-termination):\n   '%s'\n", s );  
   strncpy( s+5, "love", 4 );  
   printf( "After strncpy into middle of string:\n   '%s'\n", s );  
  
   // If we use strncpy_s, the string is terminated   
   strncpy_s( s, _countof(s), "mice", 4 );  
   printf( "After strncpy_s (with null-termination):\n   '%s'\n", s );  
  
}  
```  
  
  **Original string:**  
 **'dogs like cats'**  
**After strncpy \(no null\-termination\):**  
 **'mice like cats'**  
**After strncpy into middle of string:**  
 **'mice love cats'**  
**After strncpy\_s \(with null\-termination\):**  
 **'mice'**   
## .NET Framework-Entsprechung  
 [System::String::Copy](https://msdn.microsoft.com/en-us/library/system.string.copy.aspx)  
  
## Siehe auch  
 [Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [Interpretation von Mehrbytezeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [\_mbsnbcpy, \_mbsnbcpy\_l](../../c-runtime-library/reference/mbsnbcpy-mbsnbcpy-l.md)   
 [strcat\_s, wcscat\_s, \_mbscat\_s](../../c-runtime-library/reference/strcat-s-wcscat-s-mbscat-s.md)   
 [strcmp, wcscmp, \_mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [strcpy\_s, wcscpy\_s, \_mbscpy\_s](../../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md)   
 [strncat\_s, \_strncat\_s\_l, wcsncat\_s, \_wcsncat\_s\_l, \_mbsncat\_s, \_mbsncat\_s\_l](../../c-runtime-library/reference/strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md)   
 [strncmp, wcsncmp, \_mbsncmp, \_mbsncmp\_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [\_strnicmp, \_wcsnicmp, \_mbsnicmp, \_strnicmp\_l, \_wcsnicmp\_l, \_mbsnicmp\_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strrchr, wcsrchr, \_mbsrchr, \_mbsrchr\_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [\_strset, \_strset\_l, \_wcsset, \_wcsset\_l, \_mbsset, \_mbsset\_l](../../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)   
 [strspn, wcsspn, \_mbsspn, \_mbsspn\_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)
---
title: strncat_s, _strncat_s_l, wcsncat_s, _wcsncat_s_l, _mbsncat_s, _mbsncat_s_l | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wcsncat_s_l
- wcsncat_s
- _mbsncat_s_l
- _mbsncat_s
- strncat_s
- _strncat_s_l
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- strncat_s_l
- _mbsncat_s_l
- _tcsncat_s
- wcsncat_s
- wcsncat_s_l
- strncat_s
- _mbsncat_s
- _tcsncat_s_l
dev_langs:
- C++
helpviewer_keywords:
- concatenating strings
- _mbsncat_s function
- mbsncat_s_l function
- _tcsncat_s function
- _mbsncat_s_l function
- strncat_s function
- strings [C++], appending
- strncat_s_l function
- string concatenation [C++]
- _tcsncat_s_l function
- wcsncat_s function
- appending strings
- wcsncat_s_l function
- mbsncat_s function
ms.assetid: de77eca2-4d9c-4e66-abf2-a95fefc21e5a
caps.latest.revision: 42
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 18f40484e5af5033d8a9093dd18137a884c6d531
ms.contentlocale: de-de
ms.lasthandoff: 03/29/2017

---
# <a name="strncats-strncatsl-wcsncats-wcsncatsl-mbsncats-mbsncatsl"></a>strncat_s, _strncat_s_l, wcsncat_s, _wcsncat_s_l, _mbsncat_s, _mbsncat_s_l
Fügt einer Zeichenfolge Zeichen an. Diese Versionen von [strncat, _strncat_l, wcsncat, _wcsncat_l, _mbsncat, _mbsncat_l](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md) enthalten Sicherheitsverbesserungen, wie unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
> [!IMPORTANT]
>  `_mbsncat_s` und `_mbsncat_s_l` können nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie unter [In /ZW nicht unterstützte CRT-Funktionen](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntax  
  
```  
errno_t strncat_s(  
   char *strDest,  
   size_t numberOfElements,  
   const char *strSource,  
   size_t count  
);  
errno_t _strncat_s_l(  
   char *strDest,  
   size_t numberOfElements,  
   const char *strSource,  
   size_t count,  
   _locale_t locale  
);  
errno_t wcsncat_s(  
   wchar_t *strDest,  
   size_t numberOfElements,  
   const wchar_t *strSource,  
   size_t count   
);  
errno_t _wcsncat_s_l(  
   wchar_t *strDest,  
   size_t numberOfElements,  
   const wchar_t *strSource,  
   size_t count,  
   _locale_t locale  
);  
errno_t _mbsncat_s(  
   unsigned char *strDest,  
   size_t numberOfElements,  
   const unsigned char *strSource,  
   size_t count  
);  
errno_t _mbsncat_s_l(  
   unsigned char *strDest,  
   size_t numberOfElements,  
   const unsigned char *strSource,  
   size_t count,  
   _locale_t locale  
);  
template <size_t size>  
errno_t strncat_s(  
   char (&strDest)[size],  
   const char *strSource,  
   size_t count  
); // C++ only  
template <size_t size>  
errno_t _strncat_s_l(  
   char (&strDest)[size],  
   const char *strSource,  
   size_t count,  
   _locale_t locale  
); // C++ only  
template <size_t size>  
errno_t wcsncat_s(  
   wchar_t (&strDest)[size],  
   const wchar_t *strSource,  
   size_t count   
); // C++ only  
template <size_t size>  
errno_t _wcsncat_s_l(  
   wchar_t (&strDest)[size],  
   const wchar_t *strSource,  
   size_t count,  
   _locale_t locale  
); // C++ only  
template <size_t size>  
errno_t _mbsncat_s(  
   unsigned char (&strDest)[size],  
   const unsigned char *strSource,  
   size_t count  
); // C++ only  
template <size_t size>  
errno_t _mbsncat_s_l(  
   unsigned char (&strDest)[size],  
   const unsigned char *strSource,  
   size_t count,  
   _locale_t locale  
); // C++ only  
```  
  
#### <a name="parameters"></a>Parameter  
 [out] `strDest`  
 Auf NULL endende Zielzeichenfolge.  
  
 [in]`numberOfElements`  
 Größe des Zielpuffers.  
  
 [in]`strSource`  
 Mit NULL endende Quellzeichenfolge.  
  
 [in]`count`  
 Anzahl der anzufügenden Zeichen oder [_TRUNCATE](../../c-runtime-library/truncate.md).  
  
 [in] `locale`  
 Zu verwendendes Gebietsschema.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg 0 (null) zurück und einen Fehlercode, wenn ein Fehler auftritt.  
  
### <a name="error-conditions"></a>Fehlerbedingungen  
  
|`strDestination`|`numberOfElements`|`strSource`|Rückgabewert|Inhalt von `strDestination`|  
|----------------------|------------------------|-----------------|------------------|----------------------------------|  
|`NULL` oder nicht abgeschlossen|any|alle|`EINVAL`|nicht geändert|  
|any|alle|`NULL`|`EINVAL`|nicht geändert|  
|any|0 oder zu klein|alle|`ERANGE`|nicht geändert|  
  
## <a name="remarks"></a>Hinweise  
 Diese Funktionen versuchen, die ersten `D` Zeichen von `strSource` an das Ende von `strDest` anzufügen, wobei `D` weniger als `count` und die Länge von `strSource` ist. Wenn das Anhängen dieser `D` Zeichen in `strDest` passt (dessen Größe als `numberOfElements` angegeben ist) und dennoch Raum für einen NULL-Terminator vorhanden sein soll, werden diese Zeichen angehängt. Dabei ist der Startpunkt die ursprüngliche beendende NULL von `strDest`, und eine neue beendende NULL wird angehängt. Andernfalls wird `strDest`[0] auf das NULL-Zeichen festgelegt und der Handler für ungültige Parameter wird, wie in [Parameter Validation (Parameterüberprüfung)](../../c-runtime-library/parameter-validation.md) beschrieben, ausgelöst.  
  
 Zu der oberen Aufführung gibt es eine Ausnahme. Wenn `count` [_TRUNCATE](../../c-runtime-library/truncate.md) ist, wird so viel wie von `strSource` passt an `strDest` angehängt und weiterhin Platz zum Anhängen einer beendenden NULL gelassen.  
  
 Beispiel:  
  
 `char dst[5];`  
  
 `strncpy_s(dst, _countof(dst), "12", 2);`  
  
 `strncat_s(dst, _countof(dst), "34567", 3);`  
  
 bedeutet, dass `strncat_s` zum Anhängen von drei Zeichen an zwei Zeichen in einem fünf Zeichen langen Puffer aufgefordert wird. Dann wäre allerdings kein Platz mehr für den NULL-Terminator vorhanden. Daher weist `strncat_s` der Zeichenfolge NULL zu und ruft den Handler für ungültige Parameter auf.  
  
 Wenn ein Abschneideverhalten erforderlich ist, verwenden Sie `_TRUNCATE`, oder passen Sie den `size`-Parameter entsprechend an:  
  
 `strncat_s(dst, _countof(dst), "34567", _TRUNCATE);`  
  
 oder  
  
 `strncat_s(dst, _countof(dst), "34567", _countof(dst)-strlen(dst)-1);`  
  
 In jedem Fall wird die Ergebniszeichenfolge mit einem NULL-Zeichen beendet. Wenn der Kopiervorgang zwischen Zeichenfolgen ausgeführt wird, die sich überschneiden, ist das Verhalten nicht definiert.  
  
 Wenn `strSource` oder `strDest` `NULL` oder `numberOfElements` null ist, wird der Handler für ungültige Parameter aufgerufen, wie unter [Parameter Validation (Parameterüberprüfung)](../../c-runtime-library/parameter-validation.md) beschrieben, aufgerufen. Wenn die weitere Ausführung zugelassen wird, gibt die Funktion `EINVAL` zurück, ohne die Parameter zu ändern.  
  
 `wcsncat_s` und `_mbsncat_s` sind Breitzeichen- und Multibytezeichenversionen von `strncat_s`. Die Zeichenfolgenargumente und der Rückgabewert von `wcsncat_s` sind Zeichenfolgen mit Breitzeichen; die von `_mbsncat_s` sind Multibyte-Zeichenfolgen. Diese drei Funktionen verhalten sich andernfalls identisch.  
  
 Der Ausgabewert ist von der `LC_CTYPE`-Kategorieeinstellung des Gebietsschemas betroffen; weitere Informationen finden Sie unter [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md). Die Versionen dieser Funktionen ohne das `_l`-Suffix verwenden das aktuelle Gebietsschema für dieses vom Gebietsschema abhängige Verhalten; die Versionen mit dem `_l`-Suffix sind beinahe identisch, verwenden jedoch stattdessen den ihnen übergebenen Gebietsschemaparameter. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
 In C++ wird die Verwendung dieser Funktionen durch Vorlagenüberladungen vereinfacht; die Überladungen können automatisch Rückschlüsse auf die Pufferlänge ziehen (wodurch kein Größenargument mehr angegeben werden muss), und sie können automatisch die älteren, nicht sicheren Funktionen durch ihre neueren, sicheren Entsprechungen ersetzen. Weitere Informationen finden Sie unter [Secure Template Overloads (Sichere Vorlagenüberladungen)](../../c-runtime-library/secure-template-overloads.md).  
  
 Die Debugversionen dieser Funktionen füllen zunächst den Puffer mit "0xFD" auf. Um dieses Verhalten zu deaktivieren, verwenden Sie [_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md).  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcsncat_s`|`strncat_s`|`_mbsnbcat_s`|`wcsncat_s`|  
|`_tcsncat_s_l`|`_strncat_s_l`|`_mbsnbcat_s_l`|`_wcsncat_s_l`|  
  
 `_strncat_s_l` und `_wcsncat_s_l` sind nicht gebietsschemaabhängig. Sie werden nur für `_tcsncat_s_l` bereitgestellt.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`strncat_s`|\<string.h>|  
|`wcsncat_s`|\<string.h> oder \<wchar.h>|  
|`_mbsncat_s`, `_mbsncat_s_l`|\<mbstring.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_strncat_s.cpp  
// compile with: /MTd  
  
// These #defines enable secure template overloads  
// (see last part of Examples() below)  
#define _CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES 1   
#define _CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT 1  
  
#include <stdio.h>  
#include <stdlib.h>  
#include <string.h>  
#include <crtdbg.h>  // For _CrtSetReportMode  
#include <errno.h>  
  
// This example uses a 10-byte destination buffer.  
  
errno_t strncat_s_tester( const char * initialDest,  
                          const char * src,  
                          int count )  
{  
   char dest[10];  
   strcpy_s( dest, _countof(dest), initialDest );  
  
   printf_s( "\n" );  
  
   if ( count == _TRUNCATE )  
      printf_s( "Appending '%s' to %d-byte buffer dest with truncation semantics\n",  
               src, _countof(dest) );  
   else  
      printf_s( "Appending %d chars of '%s' to %d-byte buffer dest\n",  
              count, src, _countof(dest) );  
  
   printf_s( "    old contents of dest: '%s'\n", dest );  
  
   errno_t err = strncat_s( dest, _countof(dest), src, count );  
  
   printf_s( "    new contents of dest: '%s'\n", dest );  
  
   return err;  
}  
  
void Examples()  
{  
   strncat_s_tester( "hi ", "there", 4 );  
   strncat_s_tester( "hi ", "there", 5 );  
   strncat_s_tester( "hi ", "there", 6 );  
  
   printf_s( "\nDestination buffer too small:\n" );  
   strncat_s_tester( "hello ", "there", 4 );  
  
   printf_s( "\nTruncation examples:\n" );  
  
   errno_t err = strncat_s_tester( "hello ", "there", _TRUNCATE );  
   printf_s( "    truncation %s occur\n", err == STRUNCATE ? "did"  
                                                       : "did not" );  
  
   err = strncat_s_tester( "hello ", "!", _TRUNCATE );  
   printf_s( "    truncation %s occur\n", err == STRUNCATE ? "did"  
                                                       : "did not" );  
  
   printf_s( "\nSecure template overload example:\n" );  
  
   char dest[10] = "cats and ";  
   strncat( dest, "dachshunds", 15 );  
   // With secure template overloads enabled (see #define  
   // at top of file), the preceding line is replaced by  
   //    strncat_s( dest, _countof(dest), "dachshunds", 15 );  
   // Instead of causing a buffer overrun, strncat_s invokes  
   // the invalid parameter handler.  
   // If secure template overloads were disabled, strncat would  
   // append "dachshunds" and overrun the dest buffer.  
   printf_s( "    new contents of dest: '%s'\n", dest );  
}  
  
void myInvalidParameterHandler(  
   const wchar_t* expression,  
   const wchar_t* function,   
   const wchar_t* file,   
   unsigned int line,   
   uintptr_t pReserved)  
{  
   wprintf_s(L"Invalid parameter handler invoked: %s\n", expression);  
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
  
```Output  
Appending 4 chars of 'there' to 10-byte buffer dest  
    old contents of dest: 'hi '  
    new contents of dest: 'hi ther'  
  
Appending 5 chars of 'there' to 10-byte buffer dest  
    old contents of dest: 'hi '  
    new contents of dest: 'hi there'  
  
Appending 6 chars of 'there' to 10-byte buffer dest  
    old contents of dest: 'hi '  
    new contents of dest: 'hi there'  
  
Destination buffer too small:  
  
Appending 4 chars of 'there' to 10-byte buffer dest  
    old contents of dest: 'hello '  
Invalid parameter handler invoked: (L"Buffer is too small" && 0)  
    new contents of dest: ''  
  
Truncation examples:  
  
Appending 'there' to 10-byte buffer dest with truncation semantics  
    old contents of dest: 'hello '  
    new contents of dest: 'hello the'  
    truncation did occur  
  
Appending '!' to 10-byte buffer dest with truncation semantics  
    old contents of dest: 'hello '  
    new contents of dest: 'hello !'  
    truncation did not occur  
  
Secure template overload example:  
Invalid parameter handler invoked: (L"Buffer is too small" && 0)  
    new contents of dest: ''  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [Interpretation von Multibyte-Zeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [_mbsnbcat, _mbsnbcat_l](../../c-runtime-library/reference/mbsnbcat-mbsnbcat-l.md)   
 [strcat, wcscat, _mbscat](../../c-runtime-library/reference/strcat-wcscat-mbscat.md)   
 [strcmp, wcscmp, _mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [strcpy, wcscpy, _mbscpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)   
 [strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [strncpy, _strncpy_l, wcsncpy, _wcsncpy_l, _mbsncpy, _mbsncpy_l](../../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)   
 [_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [_strset, _strset_l, _wcsset, _wcsset_l, _mbsset, _mbsset_l](../../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)   
 [strspn, wcsspn, _mbsspn, _mbsspn_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)

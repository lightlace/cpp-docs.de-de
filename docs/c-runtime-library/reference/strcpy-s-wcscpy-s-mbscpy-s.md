---
title: "strcpy_s, wcscpy_s, _mbscpy_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "wcscpy_s"
  - "_mbscpy_s"
  - "strcpy_s"
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
  - "strcpy_s"
  - "_mbscpy_s"
  - "_tcscpy_s"
  - "wcscpy_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "strcpy_s-Funktion"
  - "_tcscpy_s-Funktion"
  - "_mbscpy_s-Funktion"
  - "Kopieren von Zeichenfolgen"
  - "Zeichenfolgen [C++], kopieren"
  - "tcscpy_s-Funktion"
  - "wcscpy_s-Funktion"
ms.assetid: 611326f3-7929-4a5d-a465-a4683af3b053
caps.latest.revision: 41
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 41
---
# strcpy_s, wcscpy_s, _mbscpy_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Kopiert eine Zeichenfolge. Diese Versionen von [strcpy, wcscpy, \_mbscpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md) wurde die Sicherheit wie unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
> [!IMPORTANT]
>  `_mbscpy_s` kann in Anwendungen nicht verwendet werden, die im [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausgeführt werden. Weitere Informationen finden Sie unter [In \/ZW nicht unterstützte CRT\-Funktionen](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
errno_t strcpy_s(  
   char *strDestination,  
   size_t numberOfElements,  
   const char *strSource   
);  
errno_t wcscpy_s(  
   wchar_t *strDestination,  
   size_t numberOfElements,  
   const wchar_t *strSource   
);  
errno_t _mbscpy_s(  
   unsigned char *strDestination,  
   size_t numberOfElements,  
   const unsigned char *strSource   
);  
template <size_t size>  
errno_t strcpy_s(  
   char (&strDestination)[size],  
   const char *strSource   
); // C++ only  
template <size_t size>  
errno_t wcscpy_s(  
   wchar_t (&strDestination)[size],  
   const wchar_t *strSource   
); // C++ only  
template <size_t size>  
errno_t _mbscpy_s(  
   unsigned char (&strDestination)[size],  
   const unsigned char *strSource   
); // C++ only  
```  
  
#### Parameter  
 `strDestination`  
 Speicherort des Zielzeichenfolgenpuffers.  
  
 `numberOfElements`  
 Größe des Zielzeichenfolgenpuffers in `char` Einheiten für schmale und Multi\-Byte\-Funktionen und `wchar_t` Einheiten für große Funktionen.  
  
 `strSource`  
 Auf NULL endender Quellzeichenfolgepuffer.  
  
## Rückgabewert  
 Null \(0\), wenn erfolgreich; andernfalls ein Fehler.  
  
### Fehlerbedingungen  
  
|`strDestination`|`numberOfElements`|`strSource`|Rückgabewert|Inhalt von `strDestination`|  
|----------------------|------------------------|-----------------|------------------|---------------------------------|  
|`NULL`|any|any|`EINVAL`|nicht geändert|  
|any|any|`NULL`|`EINVAL`|`strDestination`\[0\] auf 0 festgelegt|  
|alle|0 oder zu klein|any|`ERANGE`|`strDestination`\[0\] auf 0 festgelegt|  
  
## Hinweise  
 Die `strcpy_s`\-Funktion kopiert den Inhalt der Adresse von `strSource`, einschließlich des abschließenden NULL\-Zeichens, an den Speicherort, der von `strDestination` angegeben wird. Die Zielzeichenfolge muss groß genug sein, um die Quellzeichenfolge und ihr beendendes NULL\-Zeichen zu enthalten. Wenn sich Quell\- und Zielzeichenfolgen überlappen, ist das Verhalten von `strcpy_s` undefiniert.  
  
 `wcscpy_s` ist die Breitzeichen\-Version von `strcpy_s`, und `_mbscpy_s` ist die Mehrbytezeichen\-Version. Die Argumente und der Rückgabewert von `wcscpy_s` sind Breitzeichen\-Zeichenfolgen; die von `_mbscpy_s` sind Mehrbyte\-Zeichenfolgen. Diese drei Funktionen verhalten sich andernfalls identisch.  
  
 Wenn `strDestination` oder `strSource` ein null\-Zeiger ist oder wenn die Zielzeichenfolge zu klein ist, wird der Handler für ungültige Parameter aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die Ausführung fortgesetzt werden darf, geben diese Funktionen `EINVAL` zurück und legen `errno` auf `EINVAL` fest, wenn `strDestination` oder `strSource` ein NULL\-Zeiger ist und sie `ERANGE` zurückgeben und `errno` auf `ERANGE` festlegen, wenn die Zielzeichenfolge zu klein ist.  
  
 Nach erfolgreicher Ausführung endet die Zielzeichenfolge immer auf NULL.  
  
 In C\+\+ wird die Verwendung dieser Funktionen durch Vorlagenüberladungen vereinfacht; die Überladungen können automatisch Rückschlüsse auf die Pufferlänge ziehen, wodurch kein Größenargument mehr angegeben werden muss, und sie können automatisch die älteren, weniger sicheren Funktionen durch ihre neueren, sichereren Entsprechungen ersetzen. Weitere Informationen finden Sie unter [Sichere Vorlagenüberladungen](../../c-runtime-library/secure-template-overloads.md).  
  
 Die Debugversionen dieser Funktionen füllen zunächst den Puffer mit "0xFE" auf. Um dieses Verhalten zu deaktivieren, verwenden Sie [\_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md).  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE und \_MBCS nicht definiert.|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|-------------------------------------------|----------------------|-------------------------|  
|`_tcscpy_s`|`strcpy_s`|`_mbscpy_s`|`wcscpy_s`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`strcpy_s`|\<string.h\>|  
|`wcscpy_s`|\<string.h\> oder \<wchar.h\>|  
|`_mbscpy_s`|\<mbstring.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
  
```  
// crt_strcpy_s.cpp  
// This program uses strcpy_s and strcat_s  
// to build a phrase.  
//  
  
#include <string.h>  
#include <stdlib.h>  
#include <stdio.h>  
#include <errno.h>  
  
int main( void )  
{  
   char string[80];  
   // using template versions of strcpy_s and strcat_s:  
   strcpy_s( string, "Hello world from " );  
   strcat_s( string, "strcpy_s " );  
   strcat_s( string, "and " );  
   // of course we can supply the size explicitly if we want to:  
   strcat_s( string, _countof(string), "strcat_s!" );  
  
   printf( "String = %s\n", string );  
}  
```  
  
```Output  
Zeichenfolge = Hallo Welt von strcpy_s und strcat_s!  
```  
  
## .NET Framework-Entsprechung  
 [System::String::Copy](https://msdn.microsoft.com/en-us/library/system.string.copy.aspx)  
  
## Siehe auch  
 [Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)   
 [strcat, wcscat, \_mbscat](../../c-runtime-library/reference/strcat-wcscat-mbscat.md)   
 [strcmp, wcscmp, \_mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [strncat\_s, \_strncat\_s\_l, wcsncat\_s, \_wcsncat\_s\_l, \_mbsncat\_s, \_mbsncat\_s\_l](../../c-runtime-library/reference/strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md)   
 [strncmp, wcsncmp, \_mbsncmp, \_mbsncmp\_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [strncpy\_s, \_strncpy\_s\_l, wcsncpy\_s, \_wcsncpy\_s\_l, \_mbsncpy\_s, \_mbsncpy\_s\_l](../../c-runtime-library/reference/strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)   
 [\_strnicmp, \_wcsnicmp, \_mbsnicmp, \_strnicmp\_l, \_wcsnicmp\_l, \_mbsnicmp\_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strrchr, wcsrchr, \_mbsrchr, \_mbsrchr\_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [strspn, wcsspn, \_mbsspn, \_mbsspn\_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)
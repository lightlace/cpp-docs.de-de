---
title: "strncpy, _strncpy_l, wcsncpy, _wcsncpy_l, _mbsncpy, _mbsncpy_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "strncpy"
  - "_strncpy_l"
  - "_mbsncpy"
  - "wcsncpy"
  - "_mbsncpy_l"
  - "_wcsncpy_l"
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
  - "_fstrncpy"
  - "strncpy"
  - "_ftcsncpy"
  - "_tcsnccpy_l"
  - "_tcsnccpy"
  - "_mbsncpy"
  - "wcsncpy"
  - "_tcsncpy"
  - "_strncpy_l"
  - "_mbsncpy_l"
  - "_wcsncpy_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_fstrncpy-Funktion"
  - "_ftcsncpy-Funktion"
  - "_mbsncpy-Funktion"
  - "_mbsncpy_l-Funktion"
  - "_strncpy_l-Funktion"
  - "_tcsnccpy-Funktion"
  - "_tcsnccpy_l-Funktion"
  - "_tcsncpy-Funktion"
  - "_tcsncpy_l-Funktion"
  - "_wcsncpy_l-Funktion"
  - "Zeichen [C++], Kopieren"
  - "Kopieren von Zeichen der Zeichenfolgen"
  - "fstrncpy-Funktion"
  - "ftcsncpy-Funktion"
  - "mbsncpy-Funktion"
  - "mbsncpy_l-Funktion"
  - "Zeichenfolgen [C++], Kopieren"
  - "strncpy-Funktion"
  - "strncpy_l-Funktion"
  - "tcsnccpy-Funktion"
  - "tcsnccpy_l-Funktion"
  - "tcsncpy-Funktion"
  - "tcsncpy_l-Funktion"
  - "wcsncpy-Funktion"
  - "wcsncpy_l-Funktion"
ms.assetid: ac4345a1-a129-4f2f-bb8a-373ec58ab8b0
caps.latest.revision: 42
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 42
---
# strncpy, _strncpy_l, wcsncpy, _wcsncpy_l, _mbsncpy, _mbsncpy_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Kopieren von Zeichen aus einer Zeichenfolge in eine andere.  Es sind weitere sicherere Versionen dieser Funktionen sind verfügbar; siehe [strncpy\_s, \_strncpy\_s\_l, wcsncpy\_s, \_wcsncpy\_s\_l, \_mbsncpy\_s, \_mbsncpy\_s\_l](../../c-runtime-library/reference/strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md).  
  
> [!IMPORTANT]
>  `_mbsncpy` und `_mbsncpy_l` können in Anwendungen, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausgeführt werden, nicht verwendet werden.  Weitere Informationen finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
char *strncpy(  
   char *strDest,  
   const char *strSource,  
   size_t count   
);  
char *_strncpy_l(  
   char *strDest,  
   const char *strSource,  
   size_t count,  
   locale_t locale   
);  
wchar_t *wcsncpy(  
   wchar_t *strDest,  
   const wchar_t *strSource,  
   size_t count   
);  
wchar_t *_wcsncpy_l(  
   wchar_t *strDest,  
   const wchar_t *strSource,  
   size_t count,  
   locale_t locale   
);  
unsigned char *_mbsncpy(  
   unsigned char *strDest,  
   const unsigned char *strSource,  
   size_t count   
);  
unsigned char *_mbsncpy_l(  
   unsigned char *strDest,  
   const unsigned char *strSource,  
   size_t count,  
   _locale_t locale  
);  
template <size_t size>  
char *strncpy(  
   char (&strDest)[size],  
   const char *strSource,  
   size_t count   
); // C++ only  
template <size_t size>  
char *_strncpy_l(  
   char (&strDest)[size],  
   const char *strSource,  
   size_t count,  
   locale_t locale   
); // C++ only  
template <size_t size>  
wchar_t *wcsncpy(  
   wchar_t (&strDest)[size],  
   const wchar_t *strSource,  
   size_t count   
); // C++ only  
template <size_t size>  
wchar_t *_wcsncpy_l(  
   wchar_t (&strDest)[size],  
   const wchar_t *strSource,  
   size_t count,  
   locale_t locale   
); // C++ only  
template <size_t size>  
unsigned char *_mbsncpy(  
   unsigned char (&strDest)[size],  
   const unsigned char *strSource,  
   size_t count   
); // C++ only  
template <size_t size>  
unsigned char *_mbsncpy_l(  
   unsigned char (&strDest)[size],  
   const unsigned char *strSource,  
   size_t count,  
   _locale_t locale  
); // C++ only  
```  
  
#### Parameter  
 `strDest`  
 Zielzeichenfolge.  
  
 `strSource`  
 Quellzeichenfolge.  
  
 `count`  
 Anzahl der zu kopierenden Zeichen.  
  
 `locale`  
 Zu verwendendes Gebietsschema.  
  
## Rückgabewert  
 Gibt `strDest`zurück.  Kein Rückgabewert ist zur Fehleranzeige reserviert.  
  
## Hinweise  
 Die `strncpy` Funktion übernimmt die anfänglichen `count` Zeichen `strSource` `strDest` und gibt `strDest` zurück.  Wenn `count` kleiner oder gleich der Länge des `strSource` ist, wird ein Null\-Zeichen nicht automatisch an die kopierte Zeichenfolge angefügt.  Wenn `count` größer als die Länge von `strSource` ist, wird die Zielzeichenfolge mit Nullzeichen bis zu einer Länge von `count` aufgefüllt.  Wenn sich Quell\- und Zielzeichenfolgen überlappen, ist das Verhalten von `strncpy` undefiniert.  
  
> [!IMPORTANT]
>  `strncpy` überprüft `strDest` nicht auf genügend Speicherplatz; Daher ist dies eine mögliche Ursache von Pufferüberläufen.  Das `count`\-Argument begrenzt die Anzahl der kopierten Zeichen; es handelt sich nicht um eine Begrenzung der Größe von `strDest`.  Weitere Informationen finden Sie im folgenden Beispiel.  Weitere Informationen finden Sie unter [Vermeiden von Pufferüberläufen](security.avoiding_buffer_overruns).  
  
 Wenn `strDest` oder `strSource` ein `NULL`\-Zeiger ist oder wenn `count` kleiner oder gleich 0 ist, wird der Handler für ungültige Parameter aufgerufen, siehe Beschreibung unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md).  Wenn die weitere Ausführung zugelassen wird, geben diese Funktionen "– 1" zurück und legen `errno` auf `EINVAL` fest.  
  
 `wcsncpy` und `_mbsncpy` sind Breitzeichen\- und Multibytezeichenversionen von `strncpy`.  Die Argumente und der Rückgabewert von `wcsncpy` und `_mbsncpy`unterscheiden sich entsprechend.  Diese sechs Funktionen verhalten sich andernfalls identisch.  
  
 Die Versionen dieser Funktionen mit dem `_l`\-Suffix sind beinahe identisch, verwenden jedoch das ihnen übergebene Gebietsschema anstelle des aktuellen Gebietsschemas für ihr vom Gebietsschema abhängiges Verhalten.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
 In C\+\+ haben diese Funktionen Vorlagenüberladungen, mit denen die neueren, sicheren Entsprechungen dieser Funktionen aufgerufen werden.  Weitere Informationen finden Sie unter [Sichere Vorlagenüberladungen](../../c-runtime-library/secure-template-overloads.md).  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE und \_MBCS nicht definiert.|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|-------------------------------------------|----------------------|-------------------------|  
|`_tcsncpy`|`strncpy`|`_mbsnbcpy`|`wcsncpy`|  
|`_tcsncpy_l`|`_strncpy_l`|`_mbsnbcpy_l`|`_wcsncpy_l`|  
  
> [!NOTE]
>  `_strncpy_l` und `_wcsncpy_l` haben keine Gebietsschemaabhängigkeit, werden nur für `_tcsncpy_l` bereitgestellt und sollen nicht direkt aufgerufen werden.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`strncpy`|\<string.h\>|  
|`wcsncpy`|\<string.h\> oder \<wchar.h\>|  
|`_mbsncpy`, `_mbsncpy_l`|\<mbstring.h\>|  
  
 Weitere Informationen zur Plattformkompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung von `strncpy` und wie es missbraucht werden kann, um Fehler und Sicherheitslücken im Programm hervorzurufen.  Der Compiler generiert eine Warnung für jeden Aufruf von `strncpy`, die ungefähr wie folgt aussieht: **crt\_strncpy\_x86.c\(15\) : warning C4996: 'strncpy': This function or variable may be unsafe. Consider using strncpy\_s instead. To disable deprecation, use \_CRT\_SECURE\_NO\_WARNINGS. See online help for details.**  
  
```  
// crt_strncpy_x86.c  
// Use this command in an x86 developer command prompt to compile:   
// cl /TC /W3 crt_strncpy_x86.c  
  
#include <stdio.h>  
#include <string.h>  
  
int main() {  
   char t[20];  
   char s[20];  
   char *p = 0, *q = 0;  
  
   strcpy_s(s, sizeof(s), "AA BB CC");  
   // Note: strncpy is deprecated; consider using strncpy_s instead  
   strncpy(s, "aa", 2);     // "aa BB CC"         C4996  
   strncpy(s + 3, "bb", 2); // "aa bb CC"         C4996  
   strncpy(s, "ZZ", 3);     // "ZZ",              C4996  
                            // count greater than strSource, null added  
   printf("%s\n", s);  
  
   strcpy_s(s, sizeof(s), "AA BB CC");  
   p = strstr(s, "BB");  
   q = strstr(s, "CC");  
   strncpy(s, "aa", p - s - 1);   // "aa BB CC"   C4996  
   strncpy(p, "bb", q - p - 1);   // "aa bb CC"   C4996  
   strncpy(q, "cc",  q - s);      // "aa bb cc"   C4996  
   strncpy(q, "dd", strlen(q));   // "aa bb dd"   C4996  
   printf("%s\n", s);  
  
   // some problems with strncpy  
   strcpy_s(s, sizeof(s), "test");  
   strncpy(t, "this is a very long string", 20 ); // C4996  
   // Danger: at this point, t has no terminating null,  
   // so the printf continues until it runs into one.  
   // In this case, it will print "this is a very long test"  
   printf("%s\n", t);  
  
   strcpy_s(t, sizeof(t), "dogs like cats");  
   printf("%s\n", t);  
  
   strncpy(t + 10, "to chase cars.", 14); // C4996  
   printf("%s\n", t);  
  
   // strncpy has caused a buffer overrun and corrupted string s  
   printf("Buffer overrun: s = '%s' (should be 'test')\n", s);  
   // Since the stack grows from higher to lower addresses, buffer  
   // overruns can corrupt function return addresses on the stack,  
   // which can be exploited to run arbitrary code.  
}  
```  
  
 Ausgabe  
  
  **ZZ**  
**aa bb dd**  
**this is a very long test**  
**dogs like cats**  
**dogs like to chase cars.  Buffer overrun: s \= 'ars.' \(should be 'test'\)**  Das Layout von automatischen Variablen und die Ebene der Fehlererkennung und der Codeschutz kann durch geänderte Compilereinstellungen variieren.  Durch dieses Beispiel können sich unterschiedliche Ergebnisse ergeben, wenn es in andere Kompilierungsumgebungen oder mit anderen Compileroptionen integriert wird.  
  
## .NET Framework-Entsprechung  
 [System::String::Copy](frlrfSystemStringClassCopyTopic)  
  
## Siehe auch  
 [Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [Interpretation von Mehrbytezeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [\_mbsnbcpy, \_mbsnbcpy\_l](../../c-runtime-library/reference/mbsnbcpy-mbsnbcpy-l.md)   
 [strcat, wcscat, \_mbscat](../../c-runtime-library/reference/strcat-wcscat-mbscat.md)   
 [strcmp, wcscmp, \_mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [strcpy, wcscpy, \_mbscpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)   
 [strncat, \_strncat\_l, wcsncat, \_wcsncat\_l, \_mbsncat, \_mbsncat\_l](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)   
 [strncmp, wcsncmp, \_mbsncmp, \_mbsncmp\_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [\_strnicmp, \_wcsnicmp, \_mbsnicmp, \_strnicmp\_l, \_wcsnicmp\_l, \_mbsnicmp\_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strrchr, wcsrchr, \_mbsrchr, \_mbsrchr\_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [\_strset, \_strset\_l, \_wcsset, \_wcsset\_l, \_mbsset, \_mbsset\_l](../../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)   
 [strspn, wcsspn, \_mbsspn, \_mbsspn\_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)   
 [strncpy\_s, \_strncpy\_s\_l, wcsncpy\_s, \_wcsncpy\_s\_l, \_mbsncpy\_s, \_mbsncpy\_s\_l](../../c-runtime-library/reference/strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)   
 [strcpy\_s, wcscpy\_s, \_mbscpy\_s](../../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md)
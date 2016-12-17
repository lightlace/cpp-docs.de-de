---
title: "vsnprintf, _vsnprintf, _vsnprintf_l, _vsnwprintf, _vsnwprintf_l"
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
  - "_vsnprintf"
  - "_vsnprintf_l"
  - "_vsnwprintf"
  - "_vsnwprintf_l"
  - "_vsnprintf"
  - "_vsnprintf;"
  - "vsnprintf; _vsnprintf"
  - "_vsnwprintf;"
  - "_vsnprintf_l;"
  - "_vsnwprintf_l;"
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
apitype: "DLLExport"
f1_keywords: 
  - "_vsnprintf"
  - "_vsnwprintf"
  - "_vsntprintf"
  - "vsnprintf"
  - "stdio/vsnprintf"
  - "stdio/_vsnprintf"
  - "stdio/_vsnprintf_l"
  - "stdio/_vsnwprintf"
  - "stdio/_vsnwprintf_l"
  - "_vsnprintf_l"
  - "_vsnwprintf_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "vsntprintf-Funktion"
  - "_vsnwprintf_l-Funktion"
  - "vsnwprintf_l-Funktion"
  - "vsntprintf_l-Funktion"
  - "_vsntprintf-Funktion"
  - "_vsnprintf_l-Funktion"
  - "vsnprintf-Funktion"
  - "_vsntprintf_l-Funktion"
  - "vsnprintf_l-Funktion"
  - "_vsnwprintf-Funktion"
  - "_vsnprintf-Funktion"
  - "Formatierter Text [C++]"
  - "vsnwprintf-Funktion"
ms.assetid: a97f92df-c2f8-4ea0-9269-76920d2d566a
caps.latest.revision: 35
caps.handback.revision: "35"
ms.author: "corob"
manager: "ghogen"
---
# vsnprintf, _vsnprintf, _vsnprintf_l, _vsnwprintf, _vsnwprintf_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Schreiben von formatierter Ausgabe mithilfe eines Zeigers, der auf eine Liste von Argumenten zeigt. Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [vsnprintf\_s, \_vsnprintf\_s, \_vsnprintf\_s\_l, \_vsnwprintf\_s, \_vsnwprintf\_s\_l](../../c-runtime-library/reference/vsnprintf-s-vsnprintf-s-vsnprintf-s-l-vsnwprintf-s-vsnwprintf-s-l.md).  
  
## Syntax  
  
```  
int vsnprintf(  
   char *buffer,  
   size_t count,  
   const char *format,  
   va_list argptr   
);  
int _vsnprintf(  
   char *buffer,  
   size_t count,  
   const char *format,  
   va_list argptr   
);  
int _vsnprintf_l(  
   char *buffer,  
   size_t count,  
   const char *format,  
   locale_t locale,  
   va_list argptr   
);  
int _vsnwprintf(  
   wchar_t *buffer,  
   size_t count,  
   const wchar_t *format,  
   va_list argptr   
);  
int _vsnwprintf_l(  
   wchar_t *buffer,  
   size_t count,  
   const wchar_t *format,  
   locale_t locale,  
   va_list argptr   
);  
template <size_t size>  
int vsnprintf(  
   char (&buffer)[size],  
   size_t count,  
   const char *format,  
   va_list argptr   
); // C++ only  
template <size_t size>  
int _vsnprintf(  
   char (&buffer)[size],  
   size_t count,  
   const char *format,  
   va_list argptr   
); // C++ only  
template <size_t size>  
int _vsnprintf_l(  
   char (&buffer)[size],  
   size_t count,  
   const char *format,  
   locale_t locale,  
   va_list argptr   
); // C++ only  
template <size_t size>  
int _vsnwprintf(  
   wchar_t (&buffer)[size],  
   size_t count,  
   const wchar_t *format,  
   va_list argptr   
); // C++ only  
template <size_t size>  
int _vsnwprintf_l(  
   wchar_t (&buffer)[size],  
   size_t count,  
   const wchar_t *format,  
   locale_t locale,  
   va_list argptr   
); // C++ only  
```  
  
#### Parameter  
 `buffer`  
 Speicherort für die Ausgabe.  
  
 `count`  
 Maximale Anzahl der zu schreibenden Zeichen.  
  
 `format`  
 Formatangabe.  
  
 `argptr`  
 Zeiger zur Liste der Argumente.  
  
 `locale`  
 Das zu verwendende Gebietsschema.  
  
 Weitere Informationen finden Sie unter [Formatangaben](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).  
  
## Rückgabewert  
 Die `vsnprintf` Funktion gibt die Anzahl der geschriebenen Zeichen ohne Berücksichtigung der abschließenden Null\-Zeichens zurück. Wenn die Größe des Puffers angegeben `count` ist nicht ausreichend groß ist, um die Ausgabe von angegeben `format` und `argptr`, den Rückgabewert der `vsnprintf` ist die Anzahl der Zeichen, die keine Null\-Zeichen gezählt, wenn geschrieben werden würden, `count` groß genug sind. Ist der Rückgabewert größer als `count` \- 1, die Ausgabe abgeschnitten wurde. Der Rückgabewert „\-1“ gibt an, dass ein Codierungsfehler aufgetreten ist.  
  
 Beide `_vsnprintf` und `_vsnwprintf` Funktionen zurück, die Anzahl von Zeichen geschrieben, wenn die Anzahl der zu schreibenden Zeichen ist kleiner als oder gleich `count`; Wenn die Anzahl der zu schreibenden Zeichen größer als `count`, sind diese Funktionen geben\-1 zurück, der angibt, dass die Ausgabe abgeschnitten wurde.  
  
 Der Rückgabewert all diese Funktionen umfasst nicht das abschließende Null, ob eine geschrieben wird. Wenn `count` null ist, ist der zurückgegebene Wert ist die Anzahl der Zeichen, die die Funktionen, nicht schreiben würden alle abschließende Nullzeichen. Sie können mithilfe dieses Ergebnisses Pufferspeicher für die Zeichenfolge und dem abschließenden Null zuweisen und dann rufen Sie die Funktion erneut aus, um den Puffer zu füllen.  
  
 Wenn `format` ist `NULL`, oder wenn `buffer` NULL ist und `count` ist nicht gleich 0 \(null\) ist, rufen diese Funktionen den Handler für ungültige Parameter, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, geben diese Funktionen "– 1" zurück und legen `errno` auf `EINVAL` fest.  
  
## Hinweise  
 Jede dieser Funktionen verwendet einen Zeiger auf eine Argumentliste, formatiert die Daten und schreibt bis zu `buffer` Zeichen in den Speicher, auf den von `count` gezeigt wird. Die `vsnprintf`\-Funktion schreibt immer einen NULL\-Terminator, selbst wenn die Ausgabe abgeschnitten wird. Bei Verwendung von `_vsnprintf` und `_vsnwprintf` endet der Puffer nur dann mit NULL, wenn am Ende Platz verfügbar ist \(d. h., wenn die Anzahl der zu schreibenden Zeichen kleiner als `count` ist\).  
  
> [!IMPORTANT]
>  Um bestimmte Arten von Sicherheitsrisiken zu verhindern, sollten Sie sicherstellen, dass `format` keine benutzerdefinierte Zeichenfolge ist. Weitere Informationen finden Sie unter [Vermeiden von Pufferüberläufen](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
> [!NOTE]
>  Um sicherzustellen, dass genügend Platz für das abschließende NULL\-Zeichen vorhanden ist, wenn `_vsnprintf`, `_vsnprintf_l`, `_vsnwprintf` und `_vsnwprintf_l` aufgerufen werden, müssen Sie darauf achten, dass `count` kleiner als die Pufferlänge ist, und initialisieren Sie den Puffer vor dem Aufrufen der Funktion mit dem Wert NULL.  
>   
>  Da `vsnprintf` immer schreibt das abschließende Null\-Zeichen, die `count` möglicherweise Parameter gleich der Größe des Puffers.  
  
 Beginnend mit der UCRT in Visual Studio 2015 und Windows 10 ist `vsnprintf` nicht mehr identisch mit `_vsnprintf`. Die `vsnprintf` Funktion entspricht dem Standard C99; `_vnsprintf` zur Abwärtskompatibilität mit älteren Visual Studio\-Code beibehalten wird.  
  
 Die Versionen dieser Funktionen mit dem `_l`\-Suffix sind beinahe identisch, verwenden jedoch den ihnen übergebenen Gebietsschemaparameter anstelle des aktuellen Threadgebietsschemas.  
  
 In C\+\+ haben diese Funktionen Vorlagenüberladungen, mit denen die neueren, sicheren Entsprechungen dieser Funktionen aufgerufen werden. Weitere Informationen finden Sie unter [Sichere Vorlagenüberladungen](../../c-runtime-library/secure-template-overloads.md).  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE und \_MBCS nicht definiert.|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|-------------------------------------------|----------------------|-------------------------|  
|`_vsntprintf`|`_vsnprintf`|`_vsnprintf`|`_vsnwprintf`|  
|`_vsntprintf_l`|`_vsnprintf_l`|`_vsnprintf_l`|`_vsnwprintf_l`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header \(C\)|Erforderlicher Header \(C\+\+\)|  
|-------------|---------------------------------|-------------------------------------|  
|`vsnprintf`, `_vsnprintf`, `_vsnprintf_l`|\<stdio.h\>|\<stdio.h\> oder \<cstdio\>|  
|`_vsnwprintf`, `_vsnwprintf_l`|\<stdio.h\> oder \<wchar.h\>|\<stdio.h\>, \<wchar.h\>, \<cstdio\> oder \<cwchar\>|  
  
 Die Funktionen `_vsnprintf`, `_vsnprintf_l`, `_vsnwprintf` und `_vsnwprintf_l` sind Microsoft\-spezifisch. Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```c  
// crt_vsnwprintf.c  
// compile by using: cl /W3 crt_vsnwprintf.c  
  
// To turn off error C4996, define this symbol:  
#define _CRT_SECURE_NO_WARNINGS  
  
#include <stdio.h>  
#include <wtypes.h>  
  
#define BUFFCOUNT (10)  
  
void FormatOutput(LPCWSTR formatstring, ...)  
{  
    int nSize = 0;  
    wchar_t buff[BUFFCOUNT];  
    memset(buff, 0, sizeof(buff));  
    va_list args;  
    va_start(args, formatstring);  
    // Note: _vsnwprintf is deprecated; consider vsnwprintf_s instead  
    nSize = _vsnwprintf(buff, BUFFCOUNT - 1, formatstring, args); // C4996  
    wprintf(L"nSize: %d, buff: %ls\n", nSize, buff);  
}  
  
int main() {  
    FormatOutput(L"%ls %ls", L"Hi", L"there");  
    FormatOutput(L"%ls %ls", L"Hi", L"there!");  
    FormatOutput(L"%ls %ls", L"Hi", L"there!!");  
}  
```  
  
```Output  
nSize: 8, meine: Hallo es nSize: 9 "," Meine: Hallo vorhanden! nSize: 1, meine: Hallo vorhanden!  
```  
  
 Das Verhalten ändert sich, wenn Sie Vsnprintf zusammen mit schmaler Zeichenfolge\-Parameter verwenden. Die `count` Parameter kann die Gesamtgröße des Puffers sein, und der Rückgabewert ist die Anzahl der Zeichen, die Wenn würde geschrieben wurden `count` groß genug war:  
  
## Beispiel  
  
```c  
// crt_vsnprintf.c  
// compile by using: cl /W4 crt_vsnprintf.c  
#include <stdio.h>  
#include <stdarg.h> // for va_list, va_start  
#include <string.h> // for memset  
  
#define BUFFCOUNT (10)  
  
void FormatOutput(char* formatstring, ...)  
{  
    int nSize = 0;  
    char buff[BUFFCOUNT];  
    memset(buff, 0, sizeof(buff));  
    va_list args;  
    va_start(args, formatstring);  
    nSize = vsnprintf(buff, sizeof(buff), formatstring, args);  
    printf("nSize: %d, buff: %s\n", nSize, buff);  
}  
  
int main() {  
    FormatOutput("%s %s", "Hi", "there");   //  8 chars + null  
    FormatOutput("%s %s", "Hi", "there!");  //  9 chars + null  
    FormatOutput("%s %s", "Hi", "there!!"); // 10 chars + null  
}  
```  
  
```Output  
nSize: 8, meine: Hallo es nSize: 9 "," Meine: Hallo vorhanden! nSize: 10, meine: Hallo vorhanden!  
```  
  
## Siehe auch  
 [Stream\-E\/A](../../c-runtime-library/stream-i-o.md)   
 [vprintf\-Funktionen](../../c-runtime-library/vprintf-functions.md)   
 [Syntax der Formatangabe: printf\- und wprintf\-Funktionen](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)   
 [fprintf, \_fprintf\_l, fwprintf, \_fwprintf\_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [va\_arg, va\_copy, va\_end, va\_start](../../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)
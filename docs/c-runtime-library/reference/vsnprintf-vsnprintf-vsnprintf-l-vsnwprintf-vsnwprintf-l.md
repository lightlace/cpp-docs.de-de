---
title: vsnprintf, _vsnprintf, _vsnprintf_l, _vsnwprintf, _vsnwprintf_l | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _vsnprintf
- _vsnprintf_l
- _vsnwprintf
- _vsnwprintf_l
- _vsnprintf
- _vsnprintf;
- vsnprintf; _vsnprintf
- _vsnwprintf;
- _vsnprintf_l;
- _vsnwprintf_l;
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
- ntoskrnl.exe
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- _vsnprintf
- _vsnwprintf
- _vsntprintf
- vsnprintf
- stdio/vsnprintf
- stdio/_vsnprintf
- stdio/_vsnprintf_l
- stdio/_vsnwprintf
- stdio/_vsnwprintf_l
- _vsnprintf_l
- _vsnwprintf_l
dev_langs: C++
helpviewer_keywords:
- vsntprintf function
- _vsnwprintf_l function
- vsnwprintf_l function
- vsntprintf_l function
- _vsntprintf function
- _vsnprintf_l function
- vsnprintf function
- _vsntprintf_l function
- vsnprintf_l function
- _vsnwprintf function
- _vsnprintf function
- formatted text [C++]
- vsnwprintf function
ms.assetid: a97f92df-c2f8-4ea0-9269-76920d2d566a
caps.latest.revision: "35"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4850299b43b805c93136a59d5ee227e8bf79d2dc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="vsnprintf-vsnprintf-vsnprintfl-vsnwprintf-vsnwprintfl"></a>vsnprintf, _vsnprintf, _vsnprintf_l, _vsnwprintf, _vsnwprintf_l
Schreiben von formatierter Ausgabe mithilfe eines Zeigers, der auf eine Liste von Argumenten zeigt. Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [vsnprintf_s, _vsnprintf_s, _vsnprintf_s_l, _vsnwprintf_s, _vsnwprintf_s_l](../../c-runtime-library/reference/vsnprintf-s-vsnprintf-s-vsnprintf-s-l-vsnwprintf-s-vsnwprintf-s-l.md).  
  
## <a name="syntax"></a>Syntax  
  
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
  
#### <a name="parameters"></a>Parameter  
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
  
## <a name="return-value"></a>Rückgabewert  
 Die Funktion `vsnprintf` gibt die Anzahl der geschriebenen Zeichen zurück. Das abschließende Zeichen NULL wird dabei nicht mitgezählt. Wenn die Größe des von `count` angegebenen Puffers nicht ausreichend groß ist, um die von `format` und `argptr` festgelegte Ausgabe aufzunehmen, ist der Rückgabewert von `vsnprintf` die Anzahl der Zeichen, die geschrieben würden, wenn `count` groß genug wäre, wobei das Zeichen NULL nicht gezählt wird. Ist der Rückgabewert größer als `count` - 1, wurde die Ausgabe abgeschnitten. Der Rückgabewert „-1“ gibt an, dass ein Codierungsfehler aufgetreten ist.  
  
 Die Funktionen `_vsnprintf` und `_vsnwprintf` geben die Anzahl von Zeichen zurück, die geschrieben werden, wenn die Anzahl der zu schreibenden Zeichen kleiner als oder gleich `count` ist. Wenn die Anzahl der zu schreibenden Zeichen größer als `count` ist, geben diese Funktionen „-1“ zurück, d.h. die Ausgabe wurde abgeschnitten.  
  
 Der von allen diesen Funktionen zurückgegebene Wert enthält nicht das abschließende Zeichen NULL, unabhängig davon, ob es geschrieben wurde oder nicht. Wenn `count` null ist, ist der zurückgegebene Wert die Anzahl der Zeichen, die die Funktionen schreiben würden, ohne abschließende NULL-Zeichen. Sie können dieses Ergebnis dazu verwenden, ausreichend Pufferspeicher für die Zeichenfolge und dessen abschließendes NULL-Zeichen zuzuordnen, und die Funktion dann erneut aufrufen, um den Puffer zu füllen.  
  
 Wenn `format` `NULL` ist oder `buffer` NULL ist und `count` ungleich null ist, rufen diese Funktionen den Handler für ungültige Parameter auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, geben diese Funktionen "– 1" zurück und legen `errno` auf `EINVAL`fest.  
  
## <a name="remarks"></a>Hinweise  
 Jede dieser Funktionen verwendet einen Zeiger auf eine Argumentliste, formatiert die Daten und schreibt bis zu `count` Zeichen in den Speicher, auf den von `buffer`gezeigt wird. Die `vsnprintf` -Funktion schreibt immer einen NULL-Terminator, selbst wenn die Ausgabe abgeschnitten wird. Bei Verwendung von `_vsnprintf` und `_vsnwprintf`endet der Puffer nur dann mit NULL, wenn am Ende Platz verfügbar ist (d. h., wenn die Anzahl der zu schreibenden Zeichen kleiner als `count`ist).  
  
> [!IMPORTANT]
>  Um bestimmte Arten von Sicherheitsrisiken zu verhindern, sollten Sie sicherstellen, dass `format` keine benutzerdefinierte Zeichenfolge ist. Weitere Informationen finden Sie unter [Vermeiden von Pufferüberläufen](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
> [!NOTE]
>  Um sicherzustellen, dass genügend Platz für das abschließende NULL-Zeichen vorhanden ist, wenn `_vsnprintf`, `_vsnprintf_l`, `_vsnwprintf` und `_vsnwprintf_l`aufgerufen werden, müssen Sie darauf achten, dass `count` kleiner als die Pufferlänge ist, und initialisieren Sie den Puffer vor dem Aufrufen der Funktion mit dem Wert NULL.  
>   
>  Da `vsnprintf` immer das abschließende Null-Zeichen schreibt, ist der Parameter `count` möglicherweise gleich der Größe des Puffers.  
  
 Beginnend mit der UCRT in Visual Studio 2015 und Windows 10 ist         `vsnprintf` nicht mehr identisch mit `_vsnprintf`. Die Funktion `vsnprintf` ist mit dem Standard C99 konform; `_vnsprintf` wird aus Gründen der Abwärtskompatibilität mit älterem Visual Studio-Code beibehalten.  
  
 Die Versionen dieser Funktionen mit dem `_l` -Suffix sind beinahe identisch, verwenden jedoch den ihnen übergebenen Gebietsschemaparameter anstelle des aktuellen Threadgebietsschemas.  
  
 In C++ haben diese Funktionen Vorlagenüberladungen, mit denen die neueren, sicheren Entsprechungen dieser Funktionen aufgerufen werden. Weitere Informationen finden Sie unter [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_vsntprintf`|`_vsnprintf`|`_vsnprintf`|`_vsnwprintf`|  
|`_vsntprintf_l`|`_vsnprintf_l`|`_vsnprintf_l`|`_vsnwprintf_l`|  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header (C)|Erforderlicher Header (C++)|  
|-------------|---------------------------|-------------------------------|  
|`vsnprintf`, `_vsnprintf`, `_vsnprintf_l`|\<stdio.h>|\<stdio.h> oder \<cstdio>|  
|`_vsnwprintf`, `_vsnwprintf_l`|\<stdio.h> oder \<wchar.h>|\<stdio.h>, \<wchar.h>, \<cstdio> oder \<cwchar>|  
  
 Die Funktionen `_vsnprintf`, `_vsnprintf_l`, `_vsnwprintf` und `_vsnwprintf_l` sind Microsoft-spezifisch. Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
  
```C  
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
    va_end(args);
}  
  
int main() {  
    FormatOutput(L"%ls %ls", L"Hi", L"there");  
    FormatOutput(L"%ls %ls", L"Hi", L"there!");  
    FormatOutput(L"%ls %ls", L"Hi", L"there!!");  
}  
```  
  
```Output  
nSize: 8, buff: Hi there  
nSize: 9, buff: Hi there!  
nSize: -1, buff: Hi there!  
```  
  
 Das Verhalten ändert sich, wenn Sie stattdessen „vsnprintf“ zusammen mit Parametern mit schmaler Zeichenfolge verwenden. Der `count`-Parameter kann die gesamte Größe des Puffers sein, und der Rückgabewert ist die Anzahl der Zeichen, die geschrieben wären worden, wenn `count` groß genug wäre:  
  
## <a name="example"></a>Beispiel  
  
```C  
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
    va_end(args);  
}  
  
int main() {  
    FormatOutput("%s %s", "Hi", "there");   //  8 chars + null  
    FormatOutput("%s %s", "Hi", "there!");  //  9 chars + null  
    FormatOutput("%s %s", "Hi", "there!!"); // 10 chars + null  
}  
```  
  
```Output  
nSize: 8, buff: Hi there  
nSize: 9, buff: Hi there!  
nSize: 10, buff: Hi there!  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Stream I/O (Stream-E/A)](../../c-runtime-library/stream-i-o.md)   
 [vprintf-Funktionen](../../c-runtime-library/vprintf-functions.md)   
 [Syntax der Formatangabe: printf- und wprintf-Funktionen](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)   
 [fprintf, _fprintf_l, fwprintf, _fwprintf_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [printf, _printf_l, wprintf, _wprintf_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [va_arg, va_copy, va_end, va_start](../../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)

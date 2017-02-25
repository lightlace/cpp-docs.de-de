---
title: "vsnprintf_s, _vsnprintf_s, _vsnprintf_s_l, _vsnwprintf_s, _vsnwprintf_s_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_vsnwprintf_s"
  - "_vsnwprintf_s_l"
  - "_vsnprintf_s"
  - "vsnprintf_s"
  - "_vsnprintf_s_l"
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
  - "ntdll.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_vsnprintf_s"
  - "_vsntprintf_s"
  - "_vsnwprintf_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_vsnprintf_s-Funktion"
  - "_vsnprintf_s_l-Funktion"
  - "_vsntprintf_s-Funktion"
  - "_vsntprintf_s_l-Funktion"
  - "_vsnwprintf_s-Funktion"
  - "_vsnwprintf_s_l-Funktion"
  - "Formatierter Text [C++]"
  - "vsnprintf_s-Funktion"
  - "vsnprintf_s_l-Funktion"
  - "vsntprintf_s-Funktion"
  - "vsntprintf_s_l-Funktion"
  - "vsnwprintf_s-Funktion"
  - "vsnwprintf_s_l-Funktion"
ms.assetid: 147ccfce-58c7-4681-a726-ef54ac1c604e
caps.latest.revision: 30
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 32
---
# vsnprintf_s, _vsnprintf_s, _vsnprintf_s_l, _vsnwprintf_s, _vsnwprintf_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Schreiben von formatierter Ausgabe mithilfe eines Zeigers, der auf eine Liste von Argumenten zeigt.  Diese Versionen von [vsnprintf, \_vsnprintf, \_vsnprintf\_l, \_vsnwprintf, \_vsnwprintf\_l](../../c-runtime-library/reference/vsnprintf-vsnprintf-vsnprintf-l-vsnwprintf-vsnwprintf-l.md) enthalten Sicherheitserweiterungen wie unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
## Syntax  
  
```  
int vsnprintf_s(  
   char *buffer,  
   size_t sizeOfBuffer,  
   size_t count,  
   const char *format,  
   va_list argptr   
);  
int _vsnprintf_s(  
   char *buffer,  
   size_t sizeOfBuffer,  
   size_t count,  
   const char *format,  
   va_list argptr   
);  
int _vsnprintf_s_l(  
   char *buffer,  
   size_t sizeOfBuffer,  
   size_t count,  
   const char *format,  
   locale_t locale,  
   va_list argptr   
);  
int _vsnwprintf_s(  
   wchar_t *buffer,  
   size_t sizeOfBuffer,  
   size_t count,  
   const wchar_t *format,  
   va_list argptr   
);  
int _vsnwprintf_s_l(  
   wchar_t *buffer,  
   size_t sizeOfBuffer,  
   size_t count,  
   const wchar_t *format,  
   locale_t locale,  
   va_list argptr   
);  
template <size_t size>  
int _vsnprintf_s(  
   char (&buffer)[size],  
   size_t count,  
   const char *format,  
   va_list argptr   
); // C++ only  
template <size_t size>  
int _vsnwprintf_s(  
   wchar_t (&buffer)[size],  
   size_t count,  
   const wchar_t *format,  
   va_list argptr   
); // C++ only  
```  
  
#### Parameter  
 `buffer`  
 Speicherort für die Ausgabe.  
  
 `sizeOfBuffer`  
 Die `buffer`\-Größe für die Ausgabe als Zeichenanzahl.  
  
 `count`  
 Die maximale Anzahl von zu schreibenden Zeichen \(ohne das abschließende Nullzeichen\) oder [\_TRUNCATE](../../c-runtime-library/truncate.md).  
  
 `format`  
 Formatangabe.  
  
 `argptr`  
 Zeiger zur Liste der Argumente.  
  
 `locale`  
 Das zu verwendende Gebietsschema.  
  
 Weitere Informationen finden Sie unter [Formatangaben](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).  
  
## Rückgabewert  
 `vsnprintf_s`,`_vsnprintf_s`  und `_vsnwprintf_s`  geben die Anzahl der geschriebenen Zeichen, ohne das abschließende NULL\-Zeichen oder einem negativen Wert zurück, wenn ein Ausgabefehler auftritt.  `vsnprintf_s` ist identisch mit `_vsnprintf_s`.  `vsnprintf_s` ist zwecks Kompatibilität mit dem ANSI\-Standard enthalten.  `_vnsprintf` wird aus Gründen der Abwärtskompatibilität beibehalten.  
  
 Wenn der Speicher, der zum Speichern der Daten und eines abschließenden Nullzeichens erforderlich ist, `sizeOfBuffer` überschreitet, wird wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben der Handler für ungültige Parameter aufgerufen, sofern `count` nicht [\_TRUNCATE](../../c-runtime-library/truncate.md) entspricht. In diesem Fall wird der Anteil der Zeichenfolge geschrieben, der in `buffer` passt, und es wird "– 1" zurückgegeben.  Wenn die Ausführung nach Aufruf des Handlers für ungültige Parameter fortgesetzt wird, legen diese Funktionen `buffer` auf eine leere Zeichenfolge und `errno` auf `ERANGE` fest und geben "– 1" zurück.  
  
 Wenn `buffer` oder `format` ein `NULL`\-Zeiger ist oder wenn `count` kleiner oder gleich 0 ist, wird der Handler für ungültige Parameter aufgerufen.  Wenn die weitere Ausführung zugelassen wird, stellen diese Funktionen `errno` auf `EINVAL` ein und geben – 1 zurück.  
  
### Fehlerbedingungen  
  
|`Condition`|Return|`errno`|  
|-----------------|------------|-------------|  
|`buffer` ist  `NULL`.|\-1|`EINVAL`|  
|`format` ist  `NULL`.|\-1|`EINVAL`|  
|`count` \<\= 0|\-1|`EINVAL`|  
|`sizeOfBuffer` zu klein \(und `count` \!\= `_TRUNCATE`\)|"– 1" \(und `buffer` wird auf eine leere Zeichenfolge festgelegt\)|`ERANGE`|  
  
## Hinweise  
 Jede dieser Funktionen verwendet einen Zeiger auf eine Argumentliste und formatiert und schreibt dann bis zu `count` Zeichen der angegebenen Daten in den Arbeitsspeicher, auf den `buffer` verweist, und fügt ein abschließendes Nullzeichen an.  
  
 Wenn `count`[\_TRUNCATE](../../c-runtime-library/truncate.md) ist, schreiben diese Funktionen den Anteil der Zeichenfolge, der in `buffer` passt, wobei Platz für das abschließende Nullzeichen gelassen wird.  Wenn die gesamte Zeichenfolge \(mit dem abschließenden Nullzeichen\) in `buffer` passt, geben diese Funktionen die Anzahl der geschriebenen Zeichen zurück \(ohne das abschließende Nullzeichen\). Andernfalls geben diese Funktionen "– 1" zurück, um ein Abschneiden anzugeben.  
  
 Die Versionen dieser Funktionen mit dem `_l`\-Suffix sind beinahe identisch, verwenden jedoch den ihnen übergebenen Gebietsschemaparameter anstelle des aktuellen Threadgebietsschemas.  
  
> [!IMPORTANT]
>  Stellen Sie sicher, dass `format` keine benutzerdefinierte Zeichenfolge ist.  Weitere Informationen finden Sie unter [Vermeiden von Pufferüberläufen](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
> [!NOTE]
>  Um sicherzustellen, dass genügend Platz für das abschließende Nullzeichen vorhanden ist, achten Sie darauf, dass `count` kleiner als die Pufferlänge ist oder verwenden Sie `_TRUNCATE`.  
  
 In C\+\+ wird die Verwendung dieser Funktionen durch Vorlagenüberladungen vereinfacht; die Überladungen können automatisch Rückschlüsse auf die Pufferlänge ziehen \(wodurch kein Größenargument mehr angegeben werden muss\), und sie können automatisch die älteren, nicht sicheren Funktionen durch ihre neueren, sicheren Entsprechungen ersetzen.  Weitere Informationen finden Sie unter [Sichere Vorlagenüberladungen](../../c-runtime-library/secure-template-overloads.md).  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_vsntprintf_s`|`_vsnprintf_s`|`_vsnprintf_s`|`_vsnwprintf_s`|  
|`_vsntprintf_s_l`|`_vsnprintf_s_l`|`_vsnprintf_s_l`|`_vsnwprintf_s_l`|  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|Optionale Header|  
|-------------|---------------------------|----------------------|  
|`vsnprintf_s`|\<stdio.h\> und \<stdarg.h\>|\<varargs.h\>\*|  
|`_vsnprintf_s`, `_vsnprintf_s_l`|\<stdio.h\> und \<stdarg.h\>|\<varargs.h\>\*|  
|`_vsnwprintf_s`, `_vsnwprintf_s_l`|\<stdio.h\> oder \<wchar.h\> und \<stdarg.h\>|\<varargs.h\>\*|  
  
 \* Benötigt für die Kompatibilität mit UNIX V.  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_vsnprintf_s.cpp  
#include <stdio.h>  
#include <wtypes.h>  
  
void FormatOutput(LPCSTR formatstring, ...)   
{  
   int nSize = 0;  
   char buff[10];  
   memset(buff, 0, sizeof(buff));  
   va_list args;  
   va_start(args, formatstring);  
   nSize = vsnprintf_s( buff, _countof(buff), _TRUNCATE, formatstring, args);  
   printf("nSize: %d, buff: %s\n", nSize, buff);  
}  
  
int main() {  
   FormatOutput("%s %s", "Hi", "there");  
   FormatOutput("%s %s", "Hi", "there!");  
   FormatOutput("%s %s", "Hi", "there!!");  
}  
```  
  
  **nSize: 8, buff: Hi there**  
**nSize: 9, buff: Hi there\!**  
**nSize: \-1, buff: Hi there\!**   
## Siehe auch  
 [Stream\-E\/A](../../c-runtime-library/stream-i-o.md)   
 [vprintf\-Funktionen](../../c-runtime-library/vprintf-functions.md)   
 [fprintf, \_fprintf\_l, fwprintf, \_fwprintf\_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [va\_arg, va\_copy, va\_end, va\_start](../../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)
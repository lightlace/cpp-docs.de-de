---
title: "_malloca"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "_malloca"
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
  - "malloca"
  - "_malloca"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_malloca-Funktion"
  - "malloca-Funktion"
  - "Speicherreservierung, Stapel"
ms.assetid: 293992df-cfca-4bc9-b313-0a733a6bb936
caps.latest.revision: 27
caps.handback.revision: "27"
ms.author: "corob"
manager: "ghogen"
---
# _malloca
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Belegt Speicher für den Stapel.  Dies ist eine Version von [\_alloca](../../c-runtime-library/reference/alloca.md) mit werden, wie in [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
## Syntax  
  
```  
void *_malloca(   
   size_t size   
);  
```  
  
#### Parameter  
 `size`  
 Im Stapel zugeordnet, Bytes.  
  
## Rückgabewert  
 Die Routine `_malloca` gibt ein `void` Zeiger auf den reservierten Platz zurück, der garantiert wird, zum Speichern eines beliebigen Typs Objekt ordnungsgemäß ausgerichtet sind.  Wenn `size` 0 ist, wird `_malloca` ein Element der Länge 0 zu und gibt einen gültigen Zeiger zu diesem Element zurück.  
  
 Eine Stapelüberlaufausnahme wird generiert, wenn das Leerzeichen nicht zugeordnet werden kann.  Die Stapelüberlaufausnahme ist keine C\+\+\-Ausnahme; er ist eine strukturierte Ausnahme.  Anstatt, die C\+\+\-Ausnahmebehandlung zu verwenden, müssen Sie [Strukturierte Ausnahmebehandlung](../../cpp/structured-exception-handling-c-cpp.md) \(SEH\) verwenden.  
  
## Hinweise  
 `_malloca` ordnet `size` Bytes vom Programmstapel oder vom Heap zu, wenn die Anforderung eine bestimmte Größe in Bytes überschreitet, die von `_ALLOCA_S_THRESHOLD` angegeben werden.  Der Unterschied zwischen `_malloca` und `_alloca` ist, dass `_alloca` immer auf dem Stapel zugeordnet wird, unabhängig von der Größe.  Anders als `_alloca` der keinen Aufruf `free`, dem so zugeordneten Arbeitsspeicher freizugeben benötigt oder ermöglicht, erfordert `_malloca` die Verwendung von [\_freea](../../c-runtime-library/reference/freea.md), Arbeitsspeicher freizugeben.  Im Debugmodus belegt `_malloca` immer vom Heap Speicher.  
  
 Es gibt Einschränkungen zu `_malloca` in einem Ausnahmehandler \(EH\) explizit aufrufen.  Eh\-Routinen, die auf x86\-class Prozessoren ausgeführt werden, werden in einen eigenen Arbeitsspeicherframen: Sie führen Aufgaben im Speicherplatz aus, der nicht auf der aktuellen Position des Stapelzeigers der übergeordneten Funktion ist.  Die häufigsten Implementierungen enthalten Ausdrücke der Windows NTstrukturierten ausnahmebehandlung \(SEH\) und C\+\+\-catch\-Klausel.  Daher `_malloca` in folgenden Szenarien führt explizit aufrufen Programmausfälle während Resultsets zur aufrufenden EH\-Routine:  
  
-   Windows NT SEH Ausnahmefilterausdruck: `__except` \(`_malloca ()` \)  
  
-   Windows NT SEH endgültiger Ausnahmehandler: `__finally` } {`_malloca ()`  
  
-   Catch\-Klausel\-Ausdruck C\+\+ EH  
  
 `_malloca` kann jedoch direkt aus einer EH\-Routine oder einem von der Anwendung bereitgestellten Rückruf aufgerufen werden, der aufgerufen von einem der zuvor aufgelisteten EH\-Szenarien abruft.  
  
> [!IMPORTANT]
>  In Windows XP wenn `_malloca` innerhalb eines try\/catch\-Blocks aufgerufen wird, müssen Sie [\_resetstkoflw](../../c-runtime-library/reference/resetstkoflw.md) im catch\-Block aufrufen.  
  
 Neben den oben beschriebenen Einschränkungen wenn die Option [\/clr \(Common Language Runtime\-Kompilierung\)](../../build/reference/clr-common-language-runtime-compilation.md), `_malloca` kann nicht in Blöcken `__except` verwendet werden.  Weitere Informationen finden Sie unter [\/clr\- Einschränkungen](../../build/reference/clr-restrictions.md).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_malloca`|\<malloc.h\>|  
  
## Beispiel  
  
```  
// crt_malloca_simple.c  
#include <stdio.h>  
#include <malloc.h>  
  
void Fn()  
{  
   char * buf = (char *)_malloca( 100 );  
   // do something with buf  
   _freea( buf );  
}  
  
int main()  
{  
   Fn();  
}  
```  
  
## Beispiel  
  
```  
// crt_malloca_exception.c  
// This program demonstrates the use of  
// _malloca and trapping any exceptions  
// that may occur.  
  
#include <windows.h>  
#include <stdio.h>  
#include <malloc.h>  
  
int main()  
{  
    int     size;  
    int     numberRead = 0;  
    int     errcode = 0;  
    void    *p = NULL;  
    void    *pMarker = NULL;  
  
    while (numberRead == 0)  
    {  
        printf_s("Enter the number of bytes to allocate "  
                 "using _malloca: ");  
        numberRead = scanf_s("%d", &size);  
    }  
  
    // Do not use try/catch for _malloca,  
    // use __try/__except, since _malloca throws  
    // Structured Exceptions, not C++ exceptions.  
  
    __try  
    {  
        if (size > 0)  
        {  
            p =  _malloca( size );  
        }  
        else  
        {  
            printf_s("Size must be a positive number.");  
        }  
        _freea( p );  
    }  
  
    // Catch any exceptions that may occur.  
    __except( GetExceptionCode() == STATUS_STACK_OVERFLOW )  
    {  
        printf_s("_malloca failed!\n");  
  
        // If the stack overflows, use this function to restore.  
        errcode = _resetstkoflw();  
        if (errcode)  
        {  
            printf("Could not reset the stack!");  
            _exit(1);  
        }  
    };  
}  
```  
  
## Eingabe  
  
```  
1000  
```  
  
## Beispielausgabe  
  
```  
Enter the number of bytes to allocate using _malloca: 1000  
```  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Speicherbelegung](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [\_resetstkoflw](../../c-runtime-library/reference/resetstkoflw.md)
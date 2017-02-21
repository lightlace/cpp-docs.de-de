---
title: "_alloca | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_alloca"
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
  - "_alloca"
  - "alloca"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_alloca-Funktion"
  - "alloca-Funktion"
  - "Speicherreservierung, Stapel"
ms.assetid: 74488eb1-b71f-4515-88e1-cdd03b6f8225
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# _alloca
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Belegt Speicher für den Stapel.  Diese Funktion ist veraltet, da eine sicherere Version verfügbar ist; finden Sie unter [\_malloca](../../c-runtime-library/reference/malloca.md).  
  
## Syntax  
  
```  
void *_alloca(   
   size_t size   
);  
```  
  
#### Parameter  
 \[in\] `size`  
 Im Stapel zugeordnet, Bytes.  
  
## Rückgabewert  
 Die Routine `_alloca` gibt ein `void` Zeiger auf den reservierten Platz zurück, der garantiert wird, zum Speichern eines beliebigen Typs Objekt ordnungsgemäß ausgerichtet sind.  Wenn `size` 0 ist, wird `_alloca` ein Element der Länge 0 zu und gibt einen gültigen Zeiger zu diesem Element zurück.  
  
 Eine Stapelüberlaufausnahme wird generiert, wenn das Leerzeichen nicht zugeordnet werden kann.  Die Stapelüberlaufausnahme ist keine C\+\+\-Ausnahme; er ist eine strukturierte Ausnahme.  Anstatt, die C\+\+\-Ausnahmebehandlung zu verwenden, müssen Sie [Strukturierte Ausnahmebehandlung](../../cpp/structured-exception-handling-c-cpp.md) \(SEH\) verwenden.  
  
## Hinweise  
 `_alloca` ordnet `size` Bytes vom Programmstapel zu.  Der reservierte Platz wird automatisch freigegeben, wenn die aufrufende Funktion beendet \(nicht wenn die Zuordnung lediglich aus Bereich abgeschlossen ist\).  Daher übergeben Sie nicht den Zeigerwert, der von `_alloca` als Argument an [frei](../../c-runtime-library/reference/free.md) zurückgegeben wird.  
  
 Es gibt Einschränkungen zu `_alloca` in einem Ausnahmehandler \(EH\) explizit aufrufen.  Eh\-Routinen, die auf x86\-class Prozessoren ausgeführt werden, werden in einen eigenen Arbeitsspeicherframen: Sie führen Aufgaben im Speicherplatz aus, der nicht auf der aktuellen Position des Stapelzeigers der übergeordneten Funktion ist.  Die häufigsten Implementierungen enthalten Ausdrücke der Windows NTstrukturierten ausnahmebehandlung \(SEH\) und C\+\+\-catch\-Klausel.  Daher `_alloca` in folgenden Szenarien führt explizit aufrufen Programmausfälle während Resultsets zur aufrufenden EH\-Routine:  
  
-   Windows NT SEH Ausnahmefilterausdruck: `__except` \(`_alloca ()` \)  
  
-   Windows NT SEH endgültiger Ausnahmehandler: `__finally` } {`_alloca ()`  
  
-   Catch\-Klausel\-Ausdruck C\+\+ EH  
  
 `_alloca` kann jedoch direkt aus einer EH\-Routine oder einem von der Anwendung bereitgestellten Rückruf aufgerufen werden, der aufgerufen von einem der zuvor aufgelisteten EH\-Szenarien abruft.  
  
> [!IMPORTANT]
>  In Windows XP wenn `_alloca` innerhalb eines try\/catch\-Blocks aufgerufen wird, müssen Sie [\_resetstkoflw](../../c-runtime-library/reference/resetstkoflw.md) im catch\-Block aufrufen.  
  
 Neben den oben beschriebenen Einschränkungen wenn die Option [\/clr \(Common Language Runtime\-Kompilierung\)](../../build/reference/clr-common-language-runtime-compilation.md), `_alloca` kann nicht in Blöcken `__except` verwendet werden.  Weitere Informationen finden Sie unter [\/clr\- Einschränkungen](../../build/reference/clr-restrictions.md).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_alloca`|\<malloc.h\>|  
  
## Beispiel  
  
```  
// crt_alloca.c  
// This program demonstrates the use of  
// _alloca and trapping any exceptions  
// that may occur.  
  
#include <windows.h>  
#include <stdio.h>  
#include <malloc.h>  
  
int main()  
{  
    int     size = 1000;  
    int     errcode = 0;  
    void    *pData = NULL;  
  
    // Note: Do not use try/catch for _alloca,  
    // use __try/__except, since _alloca throws  
    // Structured Exceptions, not C++ exceptions.  
  
    __try {  
        // An unbounded _alloca can easily result in a   
        // stack overflow.  
        // Checking for a size < 1024 bytes is recommended.  
        if (size > 0 && size < 1024)  
        {  
            pData = _alloca( size );  
            printf_s( "Allocated %d bytes of stack at 0x%p",  
                      size, pData);  
        }  
        else  
        {  
            printf_s("Tried to allocate too many bytes.\n");  
        }  
    }  
  
    // If an exception occured with the _alloca function  
    __except( GetExceptionCode() == STATUS_STACK_OVERFLOW )  
    {  
        printf_s("_alloca failed!\n");  
  
        // If the stack overflows, use this function to restore.  
        errcode = _resetstkoflw();  
        if (errcode)  
        {  
            printf_s("Could not reset the stack!\n");  
            _exit(1);  
        }  
    };  
}  
```  
  
  **Zugeordnet 1000 Bytes vom Stapel an 0x0012FB50**   
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Speicherbelegung](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [\_resetstkoflw](../../c-runtime-library/reference/resetstkoflw.md)   
 [\_malloca](../../c-runtime-library/reference/malloca.md)
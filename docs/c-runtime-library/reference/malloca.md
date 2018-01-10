---
title: _malloca | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _malloca
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
apitype: DLLExport
f1_keywords:
- malloca
- _malloca
dev_langs: C++
helpviewer_keywords:
- memory allocation, stack
- malloca function
- _malloca function
ms.assetid: 293992df-cfca-4bc9-b313-0a733a6bb936
caps.latest.revision: "27"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fcdeab9e61eda17164be06498e9ce42695faf8ea
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="malloca"></a>_malloca
Belegt Speicher für den Stapel. Dies ist eine sicherere Version von [_alloca](../../c-runtime-library/reference/alloca.md), wie in [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
void *_malloca(   
   size_t size   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `size`  
 Bytes, die vom Stapel zugeordnet werden.  
  
## <a name="return-value"></a>Rückgabewert  
 Die `_malloca`-Routine gibt einen `void`-Zeiger auf den zugeordneten Speicherplatz zurück, der für die Speicherung eines beliebigen Objekttyps entsprechend ausgerichtet ist. Wenn `size` 0 ist, weist `_malloca` ein Element der Länge 0 zu und gibt einen gültigen Zeiger auf dieses Element zurück.  
  
 Eine Stapelüberlaufausnahme wird generiert, wenn der Speicherplatz nicht zugeordnet werden kann. Die Stapelüberlaufausnahme ist keine C++-Ausnahme, sondern eine strukturierte Ausnahme. Sie müssen anstelle der C++-Ausnahmebehandlung die [Strukturierte Ausnahmebehandlung](../../cpp/structured-exception-handling-c-cpp.md) (Structured Exception Handling, SEH) verwenden.  
  
## <a name="remarks"></a>Hinweise  
 `_malloca` ordnet `size`-Bytes aus dem Programmstapel oder dem Heap zu, wenn die Anforderung eine bestimmte Größe in Bytes überschreitet, die von `_ALLOCA_S_THRESHOLD` angegeben ist. Der Unterschied zwischen `_malloca` und `_alloca` ist, dass `_alloca` immer auf dem Stapel zuordnet, unabhängig von der Größe. Im Gegensatz zu `_alloca`, wobei kein Aufruf auf `free` erforderlich bzw. zulässig ist, um den zugeordneten Speicher freizugeben, erfordert `_malloca` den Gebrauch von [_freea](../../c-runtime-library/reference/freea.md), um den Speicher freizugeben. Im Debugmodus weist `_malloca` immer Speicher vom Heap zu.  
  
 Es gelten Einschränkungen beim expliziten Aufruf von `_malloca` in einem Ausnahmehandler (exception handler, EH). EH-Routinen, die auf x86-Klasse-Prozessoren ausgeführt werden, arbeiten in ihrem eigenen Speicherrahmen: Sie führen Ihre Tasks im Speicherplatz aus, der nicht auf der aktuellen Position des Stapelzeigers der einschließenden Funktion basiert. Die am häufigsten verwendeten Implementierungen umfassen die strukturierte Windows NT-Ausnahmebehandlung (SEH) und C++-Catch-Klauselausdrücke. Daher führt das explizite Aufrufen von `_malloca` in jedem der folgenden Szenarios zu einem Programmfehler während der Rückgabe auf die aufrufende EH-Routine.  
  
-   Filterausdrücke der Windows NT-SEH-Ausnahme: `__except` (`_malloca ()` )  
  
-   Endgültige Ausnahmehandler von Windows NT-SEH: `__finally` {`_malloca ()` }  
  
-   C++-EH-Catch-Klauselausdruck  
  
 Allerdings kann `_malloca` direkt innerhalb einer EH-Routine aufgerufen werden oder von einem von einer Anwendung bereitgestellten Rückruf, der von einem der zuvor aufgeführten EH-Szenarios aufgerufen wird.  
  
> [!IMPORTANT]
>  Wenn unter Windows XP `_malloca` innerhalb eines try/catch-Blocks aufgerufen wird, müssen Sie [_resetstkoflw](../../c-runtime-library/reference/resetstkoflw.md) im Catch-Block aufrufen.  
  
 Zusätzlich zu den oben genannten Einschränkungen kann bei Verwendung der Option [/clr (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md) `_malloca` nicht in `__except`-Blöcken verwendet werden. Weitere Informationen finden Sie unter [Einschränkungen für „/clr“](../../build/reference/clr-restrictions.md).  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`_malloca`|\<malloc.h>|  
  
## <a name="example"></a>Beispiel  
  
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
  
## <a name="example"></a>Beispiel  
  
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
  
## <a name="input"></a>Eingabe  
  
```  
1000  
```  
  
## <a name="sample-output"></a>Beispielausgabe  
  
```  
Enter the number of bytes to allocate using _malloca: 1000  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Speicherbelegung](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [_resetstkoflw](../../c-runtime-library/reference/resetstkoflw.md)
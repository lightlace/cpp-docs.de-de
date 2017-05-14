---
title: _alloca | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _alloca
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
- _alloca
- alloca
dev_langs:
- C++
helpviewer_keywords:
- memory allocation, stack
- alloca function
- _alloca function
ms.assetid: 74488eb1-b71f-4515-88e1-cdd03b6f8225
caps.latest.revision: 23
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
ms.openlocfilehash: 5875a26dc5758674665fba2fde5b51c2ff53420e
ms.contentlocale: de-de
ms.lasthandoff: 03/29/2017

---
# <a name="alloca"></a>_alloca
Belegt Speicher für den Stapel. Diese Funktion ist veraltet, da eine sicherere Version verfügbar ist. finden Sie unter [_malloca](../../c-runtime-library/reference/malloca.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
void *_alloca(   
   size_t size   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 [in] `size`  
 Bytes, die vom Stapel zugeordnet werden.  
  
## <a name="return-value"></a>Rückgabewert  
 Die `_alloca`-Routine gibt einen `void`-Zeiger auf den zugeordneten Speicherplatz zurück, der für die Speicherung eines beliebigen Objekttyps entsprechend ausgerichtet ist. Wenn `size` 0 ist, weist `_alloca` ein Element der Länge 0 zu und gibt einen gültigen Zeiger auf dieses Element zurück.  
  
 Eine Stapelüberlaufausnahme wird generiert, wenn der Speicherplatz nicht zugeordnet werden kann. Die Stapelüberlaufausnahme ist keine C++-Ausnahme, sondern eine strukturierte Ausnahme. Sie müssen anstelle der C++-Ausnahmebehandlung die [Strukturierte Ausnahmebehandlung](../../cpp/structured-exception-handling-c-cpp.md) (Structured Exception Handling, SEH) verwenden.  
  
## <a name="remarks"></a>Hinweise  
 `_alloca`Ordnet `size` Bytes aus dem Programmstapel. Der reservierte Platz wird automatisch freigegeben, wenn die aufrufende Funktion beendet wird (nicht, wenn die Zuordnung lediglich außerhalb des gültigen Bereichs übergibt). Übergeben Sie deshalb nicht den Wert des Zeigers zurückgegebenes `_alloca` als Argument an [freien](../../c-runtime-library/reference/free.md).  
  
 Es gelten Einschränkungen beim expliziten Aufruf von `_alloca` in einem Ausnahmehandler (exception handler, EH). EH-Routinen, die auf x86-Klasse-Prozessoren ausgeführt werden, arbeiten in ihrem eigenen Speicherrahmen: Sie führen Ihre Tasks im Speicherplatz aus, der nicht auf der aktuellen Position des Stapelzeigers der einschließenden Funktion basiert. Die am häufigsten verwendeten Implementierungen umfassen die strukturierte Windows NT-Ausnahmebehandlung (SEH) und C++-Catch-Klauselausdrücke. Daher führt das explizite Aufrufen von `_alloca` in jedem der folgenden Szenarios zu einem Programmfehler während der Rückgabe auf die aufrufende EH-Routine.  
  
-   Filterausdrücke der Windows NT-SEH-Ausnahme: `__except` (`_alloca ()` )  
  
-   Endgültige Ausnahmehandler von Windows NT-SEH: `__finally` {`_alloca ()` }  
  
-   C++-EH-Catch-Klauselausdruck  
  
 Allerdings kann `_alloca` direkt innerhalb einer EH-Routine aufgerufen werden oder von einem von einer Anwendung bereitgestellten Rückruf, der von einem der zuvor aufgeführten EH-Szenarios aufgerufen wird.  
  
> [!IMPORTANT]
>  Wenn unter Windows XP `_alloca` innerhalb eines try/catch-Blocks aufgerufen wird, müssen Sie [_resetstkoflw](../../c-runtime-library/reference/resetstkoflw.md) im Catch-Block aufrufen.  
  
 Zusätzlich zu den oben genannten Einschränkungen bei Verwendung der[/CLR (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md) Option `_alloca` kann nicht verwendet werden, `__except` blockiert. Weitere Informationen finden Sie unter [/clr Restrictions](../../build/reference/clr-restrictions.md).  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_alloca`|\<malloc.h>|  
  
## <a name="example"></a>Beispiel  
  
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
  
```Output  
Allocated 1000 bytes of stack at 0x0012FB50  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Speicherbelegung](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [_resetstkoflw](../../c-runtime-library/reference/resetstkoflw.md)   
 [_malloca](../../c-runtime-library/reference/malloca.md)

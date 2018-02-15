---
title: _CrtIsValidHeapPointer | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _CrtIsValidHeapPointer
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
- CrtlsValidHeapPointer
- _CrtIsValidHeapPointer
dev_langs:
- C++
helpviewer_keywords:
- _CrtIsValidHeapPointer function
- CrtIsValidHeapPointer function
ms.assetid: caf597ce-1b05-4764-9f37-0197a982bec5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4f888466e0b1625f93c4e1cf66fab0bb85678094
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="crtisvalidheappointer"></a>_CrtIsValidHeapPointer
Überprüft, ob sich ein angegebener Zeiger in einem Heap befindet, der durch eine C-Laufzeitbibliothek zugewiesen wurde, aber nicht notwendigerweise durch die CRT-Bibliothek des Aufrufers. In CRT-Versionen vor Visual Studio 2010 wird dadurch überprüft, ob sich der angegebene Zeiger im lokalen Heap befindet (nur Debugversion).  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      int _CrtIsValidHeapPointer(   
   const void *userData   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `userData`  
 Zeiger auf den Anfang eines belegten Speicherblocks.  
  
## <a name="return-value"></a>Rückgabewert  
 `_CrtIsValidHeapPointer` gibt TRUE zurück, wenn sich der angegebene Zeiger im Heap befindet, der von allen Instanzen der CRT-Bibliothek gemeinsam verwendet wird. In CRT-Versionen vor Visual Studio 2010 wird TRUE wiedergegeben, wenn sich der angegebene Zeiger im lokalen Heap befindet. Andernfalls gibt die Funktion FALSE zurück.  
  
## <a name="remarks"></a>Hinweise  
 Wir empfehlen nicht, diese Funktion zu verwenden. Ab der Visual Studio 2010-CRT-Bibliothek nutzen alle CRT-Bibliotheken gemeinsam einen OS-Heap, den *Prozessheap*. Die `_CrtIsValidHeapPointer`-Funktion meldet, ob der Zeiger in einem CRT-Heap zugewiesen wurde, aber nicht, dass er durch die CRT-Bibliothek des Aufrufers zugewiesen wurde. Betrachten Sie beispielsweise einen Block, der mit der Visual Studio 2010-Version der CRT-Bibliothek zugeordnet wurde. Wenn die von der Visual Studio 2012-Version der CRT-Bibliothek exportierte `_CrtIsValidHeapPointer`-Funktion den Zeiger testet, wird TRUE zurückgegeben. Dies ist kein nützlicher Test mehr. In Versionen der CRT-Bibliothek vor Visual Studio 2010 wird die Funktion verwendet, um sicherzustellen, dass sich eine bestimmte Speicheradresse im lokalen Heap befindet. Der lokale Heap verweist auf den Heap, der von einer bestimmten Instanz der C-Laufzeitbibliothek erstellt und verwaltet wird. Wenn eine Dynamic Link Library (DLL) einen statischen Link zur Laufzeitbibliothek enthält, hat sie ihre eigene Instanz des Laufzeitheaps und daher ihren eigenen Heap, unabhängig vom lokalen Heap der Anwendung. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, werden Aufrufe von `_CrtIsValidHeapPointer` während der Vorverarbeitung entfernt.  
  
 Da diese Funktion TRUE oder FALSE zurückgibt, kann sie an eine der [_ASSERT](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)-Makros übergeben werden, um einen einfachen Debug-Fehlerbehandlungsmechanismus zu erstellen. Im folgenden Beispiel wird ein Assertionsfehler ausgelöst, wenn sich die angegebene Adresse nicht im lokalen Heap befindet:  
  
```  
_ASSERTE( _CrtIsValidHeapPointer( userData ) );  
```  
  
 Weitere Informationen dazu, wie `_CrtIsValidHeapPointer` mit anderen Debugfunktionen und -makros verwendet werden kann, finden Sie unter [Makros für die Berichterstellung](/visualstudio/debugger/macros-for-reporting). Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details).  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`_CrtIsValidHeapPointer`|\<crtdbg.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="libraries"></a>Bibliotheken  
 Nur Debugversionen von [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie getestet wird, ob der Arbeitsspeicher gültig ist, wenn er mit C-Laufzeitbibliotheken vor Visual Studio 2010 verwendet wird. Dieses Beispiel wird für Benutzer von Legacycode der CRT-Bibliothek bereitgestellt.  
  
```  
// crt_isvalid.c  
/*  
 * This program allocates a block of memory using _malloc_dbg  
 * and then tests the validity of this memory by calling   
 * _CrtIsMemoryBlock,_CrtIsValidPointer, and _CrtIsValidHeapPointer.  
 */  
  
#include <stdio.h>  
#include <string.h>  
#include <malloc.h>  
#include <crtdbg.h>  
  
#define  TRUE   1  
#define  FALSE  0  
  
int main( void )  
{  
        char *my_pointer;  
  
        /*   
         * Call _malloc_dbg to include the filename and line number  
         * of our allocation request in the header information  
         */  
        my_pointer = (char *)_malloc_dbg( sizeof(char) * 10,   
        _NORMAL_BLOCK, __FILE__, __LINE__ );  
  
        // Ensure that the memory got allocated correctly  
        _CrtIsMemoryBlock((const void *)my_pointer, sizeof(char) * 10,   
        NULL, NULL, NULL );  
  
         // Test for read/write accessibility  
        if (_CrtIsValidPointer((const void *)my_pointer,   
        sizeof(char) * 10, TRUE))  
                printf("my_pointer has read and write accessibility.\n");  
        else  
                printf("my_pointer only has read access.\n");  
  
        // Make sure my_pointer is within the local heap  
        if (_CrtIsValidHeapPointer((const void *)my_pointer))  
                printf("my_pointer is within the local heap.\n");  
        else  
                printf("my_pointer is not located within the local"  
                       " heap.\n");  
  
        free(my_pointer);  
}  
```  
  
## <a name="output"></a>Ausgabe  
  
```  
my_pointer has read and write accessibility.  
my_pointer is within the local heap.  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Debugroutinen](../../c-runtime-library/debug-routines.md)
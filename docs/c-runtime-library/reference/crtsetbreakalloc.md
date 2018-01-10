---
title: _CrtSetBreakAlloc | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _CrtSetBreakAlloc
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
- CrtSetBreakAlloc
- _CrtSetBreakAlloc
dev_langs: C++
helpviewer_keywords:
- CrtSetBreakAlloc function
- _CrtSetBreakAlloc function
ms.assetid: 33bfc6af-a9ea-405b-a29f-1c2d4d9880a1
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 70262673935e67fc6ee868a400fd57358a31547a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="crtsetbreakalloc"></a>_CrtSetBreakAlloc
Legt einen Haltepunkt für eine angegebene Bestellnummer der Objektzuordnung fest (nur Debugversion).  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      long _CrtSetBreakAlloc(   
   long lBreakAlloc   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 *lBreakAlloc*  
 Zuordnungsbestellnummer, für die der Haltepunkt festzulegen ist.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt die vorherige Bestellnummer der Objektzuordnung zurück, die einen festgelegten Haltepunkt hatte.  
  
## <a name="remarks"></a>Hinweise  
 `_CrtSetBreakAlloc` ermöglicht es einer Anwendung, eine Speicherverlusterkennung durchzuführen, indem an einem bestimmten Punkt der Speicherbelegung angehalten und der Ursprung der Anforderung nachverfolgt wird. Die Funktion verwendet die sequenzielle Bestellnummer der Objektzuordnung, die dem Speicherblock zugewiesen wird, wenn sie im Heap reserviert wurde. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, werden Aufrufe von `_CrtSetBreakAlloc` während der Vorverarbeitung entfernt.  
  
 Die Bestellnummer der Objektzuordnung wird im *lRequest*-Feld der **_CrtMemBlockHeader**-Struktur gespeichert, die in „Crtdbg.h“ definiert ist. Wenn Informationen zu einem Speicherblock von einer der Debugdumpfunktionen ausgegeben werden, wird die Nummer in geschweiften Klammern angezeigt, z. B. {36}.  
  
 Weitere Informationen dazu, wie `_CrtSetBreakAlloc` mit anderen Speicherverwaltungsfunktionen verwendet werden kann, finden Sie unter [Nachverfolgen von Heapreservierungsanforderungen](/visualstudio/debugger/crt-debug-heap-details). Weitere Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details).  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`_CrtSetBreakAlloc`|\<crtdbg.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="libraries"></a>Bibliotheken  
 Nur Debugversionen von [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_setbrkal.c  
// compile with: -D_DEBUG /MTd -Od -Zi -W3 /c /link -verbose:lib -debug  
  
/*  
 * In this program, a call is made to the _CrtSetBreakAlloc routine  
 * to verify that the debugger halts program execution when it reaches  
 * a specified allocation number.  
 */  
  
#include <malloc.h>  
#include <crtdbg.h>  
  
int main( )  
{  
        long allocReqNum;  
        char *my_pointer;  
  
        /*   
         * Allocate "my_pointer" for the first  
         * time and ensure that it gets allocated correctly  
         */  
        my_pointer = malloc(10);  
        _CrtIsMemoryBlock(my_pointer, 10, &allocReqNum, NULL, NULL);  
  
        /*   
         * Set a breakpoint on the allocation request  
         * number for "my_pointer"  
         */  
        _CrtSetBreakAlloc(allocReqNum+2);  
  
        /*   
         * Alternate freeing and reallocating "my_pointer"  
         * to verify that the debugger halts program execution  
         * when it reaches the allocation request  
         */  
        free(my_pointer);  
        my_pointer = malloc(10);  
        free(my_pointer);  
        my_pointer = malloc(10);  
        free(my_pointer);  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Debugroutinen](../../c-runtime-library/debug-routines.md)
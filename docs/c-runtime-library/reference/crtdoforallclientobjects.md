---
title: _CrtDoForAllClientObjects | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _CrtDoForAllClientObjects
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
- _CrtDoForAllClientObjects
- CrtDoForAllClientObjects
- crtdbg/_CrdDoForAllClientObjects
dev_langs:
- C++
helpviewer_keywords:
- _CrtDoForAllClientObjects function
- CrtDoForAllClientObjects function
ms.assetid: d0fdb835-3cdc-45f1-9a21-54208e8df248
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 316e062f4953874ce014f8288e86094209760faf
ms.lasthandoff: 02/24/2017

---
# <a name="crtdoforallclientobjects"></a>_CrtDoForAllClientObjects
Ruft eine von der Anwendung bereitgestellte Funktion für alle `_CLIENT_BLOCK` -Typen im Heap auf (nur Debugversion).  
  
## <a name="syntax"></a>Syntax  
  
```  
void _CrtDoForAllClientObjects(   
   void ( * pfn )( void *, void * ),  
   void *context  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pfn`  
 Zeiger zu der von der Anwendung bereitgestellten Rückruffunktion. Der erste Parameter für diese Funktion zeigt auf die Daten. Der zweite Parameter ist der Kontextzeiger, der an den Aufruf von `_CrtDoForAllClientObjects` übergeben wird.  
  
 `context`  
 Zeiger zu dem von der Anwendung bereitgestellten Kontext, um die von der Anwendung bereitgestellten Funktion zu übergeben.  
  
## <a name="remarks"></a>Hinweise  
 Die `_CrtDoForAllClientObjects` -Funktion sucht die verknüpfte Liste des Heaps für Speicherblöcke im `_CLIENT_BLOCK` -Typ und ruft die von der Anwendung bereitgestellte Funktion auf, wenn ein Block dieses Typs gefunden wird. Der gefundene Block und der `context`-Parameter werden als Argumente an die von der Anwendung bereitgestellte Funktion übergeben. Während des Debuggens kann eine Anwendung eine bestimmte Zuordnungsgruppe nachverfolgen, indem sie die Debugheapfunktionen explizit zum Belegen des Speichers aufruft und angibt, dass den Blöcken der `_CLIENT_BLOCK`-Blocktyp zugewiesen wird. Diese Blöcke können dann einzeln nachverfolgt und während der Erkennung von Speicherverlusten und der Berichterstellung von Speicherzuständen unterschiedlich übermittelt werden.  
  
 Wenn das `_CRTDBG_ALLOC_MEM_DF`-Bitfeld des [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)-Flags nicht aktiviert ist, wird unmittelbar `_CrtDoForAllClientObjects` zurückgegeben. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, werden Aufrufe von `_CrtDoForAllClientObjects` während der Vorverarbeitung entfernt.  
  
 Weitere Informationen zum `_CLIENT_BLOCK`-Typ und seiner Verwendung durch andere Debugfunktionen finden Sie unter [Blocktypen auf dem Debugheap](/visualstudio/debugger/crt-debug-heap-details). Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [Details zum CRT-Debugheap](/visualstudio/debugger/crt-debug-heap-details).  
  
 Wenn `pfn``NULL` ist, wird der Handler für ungültige Parameter aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, wird [errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) auf `EINVAL` gesetzt, und die Funktion wird zurückgegeben.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_CrtDoForAllClientObjects`|\<crtdbg.h>, \<errno.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
 **Bibliotheken:** Nur Debugversionen von C-Laufzeitbibliotheken.  
  
## <a name="net-framework-equivalent"></a>Entsprechung in .NET Framework  
 Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Siehe auch  
 [Debugroutinen](../../c-runtime-library/debug-routines.md)   
 [_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md)   
 [Berichtsfunktionen für den Heapzustand](/visualstudio/debugger/crt-debug-heap-details)   
 [_CrtReportBlockType](../../c-runtime-library/reference/crtreportblocktype.md)

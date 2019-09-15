---
title: _CrtDoForAllClientObjects
ms.date: 11/04/2016
api_name:
- _CrtDoForAllClientObjects
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _CrtDoForAllClientObjects
- CrtDoForAllClientObjects
- crtdbg/_CrdDoForAllClientObjects
helpviewer_keywords:
- _CrtDoForAllClientObjects function
- CrtDoForAllClientObjects function
ms.assetid: d0fdb835-3cdc-45f1-9a21-54208e8df248
ms.openlocfilehash: 4626df0db1956efd26ee267cb8cacf8ea4a4570c
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70942529"
---
# <a name="_crtdoforallclientobjects"></a>_CrtDoForAllClientObjects

Ruft eine von der Anwendung bereitgestellte Funktion für alle **_CLIENT_BLOCK** -Typen im Heap auf (nur Debugversion).

## <a name="syntax"></a>Syntax

```C
void _CrtDoForAllClientObjects(
   void ( * pfn )( void *, void * ),
   void *context
);
```

### <a name="parameters"></a>Parameter

*pfn*<br/>
Zeiger zu der von der Anwendung bereitgestellten Rückruffunktion. Der erste Parameter für diese Funktion zeigt auf die Daten. Der zweite Parameter ist der Kontext Zeiger, der an den Aufrufen von **_CrtDoForAllClientObjects**übergeben wird.

*context*<br/>
Zeiger zu dem von der Anwendung bereitgestellten Kontext, um die von der Anwendung bereitgestellten Funktion zu übergeben.

## <a name="remarks"></a>Hinweise

Die **_CrtDoForAllClientObjects** -Funktion durchsucht die verknüpfte Liste des Heaps nach Speicherblöcken mit dem **_CLIENT_BLOCK** -Typ und ruft die von der Anwendung bereitgestellte Funktion auf, wenn ein Block dieses Typs gefunden wird. Der gefundene Block und der *Kontext* Parameter werden als Argumente an die von der Anwendung bereitgestellte Funktion übergeben. Während des Debuggens kann eine Anwendung eine bestimmte Gruppe von Zuordnungen nachverfolgen, indem Sie die Debugheapfunktionen explizit aufrufen, um den Arbeitsspeicher zuzuordnen und anzugeben, dass den Blöcken der **_CLIENT_BLOCK** -Blocktyp zugewiesen wird. Diese Blöcke können dann einzeln nachverfolgt und während der Erkennung von Speicherverlusten und der Berichterstellung von Speicherzuständen unterschiedlich übermittelt werden.

Wenn das **_CRTDBG_ALLOC_MEM_DF** -Bitfeld des [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) -Flags nicht aktiviert ist, wird **_CrtDoForAllClientObjects** sofort zurückgegeben. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, werden Aufrufe von **_CrtDoForAllClientObjects** während der Vorverarbeitung entfernt.

Weitere Informationen zum **_CLIENT_BLOCK** -Typ und zur Verwendung durch andere Debugfunktionen finden Sie unter [Blocktypen auf dem](/visualstudio/debugger/crt-debug-heap-details)Debugheap. Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details).

Wenn *PFN* **null**ist, wird der Handler für ungültige Parameter aufgerufen, wie in [Parameter Validation (Parameter](../../c-runtime-library/parameter-validation.md)Überprüfung) beschrieben. Wenn die weitere Ausführung zugelassen wird, wird [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) auf **EINVAL** festgelegt, und die Funktion gibt zurück.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_CrtDoForAllClientObjects**|\<crtdbg.h>, \<errno.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

**Bibliotheken** Nur Debugversionen von universellen C-Laufzeitbibliotheken.

## <a name="see-also"></a>Siehe auch

[Debugroutinen](../../c-runtime-library/debug-routines.md)<br/>
[_CrtSetDbgFlag](crtsetdbgflag.md)<br/>
[Berichtsfunktionen für den Heapzustand](/visualstudio/debugger/crt-debug-heap-details)<br/>
[_CrtReportBlockType](crtreportblocktype.md)<br/>

---
title: _CrtDoForAllClientObjects
ms.date: 11/04/2016
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
helpviewer_keywords:
- _CrtDoForAllClientObjects function
- CrtDoForAllClientObjects function
ms.assetid: d0fdb835-3cdc-45f1-9a21-54208e8df248
ms.openlocfilehash: 86268bd9ac49c8ea27f715404236bcb9291f5d8b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50521189"
---
# <a name="crtdoforallclientobjects"></a>_CrtDoForAllClientObjects

Ruft eine Anwendung bereitgestellte Funktion für alle **_CLIENT_BLOCK** -Typen im Heap (nur Debugversion).

## <a name="syntax"></a>Syntax

```C
void _CrtDoForAllClientObjects(
   void ( * pfn )( void *, void * ),
   void *context
);
```

### <a name="parameters"></a>Parameter

*pfn*<br/>
Zeiger zu der von der Anwendung bereitgestellten Rückruffunktion. Der erste Parameter für diese Funktion zeigt auf die Daten. Der zweite Parameter ist der Kontextzeiger, der an den Aufruf übergeben wird **_CrtDoForAllClientObjects**.

*context*<br/>
Zeiger zu dem von der Anwendung bereitgestellten Kontext, um die von der Anwendung bereitgestellten Funktion zu übergeben.

## <a name="remarks"></a>Hinweise

Die **_CrtDoForAllClientObjects** -Funktion sucht der verknüpften Heapliste für Speicherblöcke der **_CLIENT_BLOCK** -Typ und ruft die Anwendung bereitgestellte Funktion aus, wenn ein Block dieses Typs gefunden wird. Der gefundene Block und *Kontext* Parameter werden als Argumente an die Anwendung bereitgestellte Funktion übergeben. Während des Debuggens kann eine Anwendung eine bestimmte Gruppe von Zuordnungen verfolgen, indem Sie explizit das Debuggen Heapfunktionen zum Belegen des Speichers aufgerufen und gibt an, dass die Blöcke zugewiesen werden die **_CLIENT_BLOCK** Blocktyp. Diese Blöcke können dann einzeln nachverfolgt und während der Erkennung von Speicherverlusten und der Berichterstellung von Speicherzuständen unterschiedlich übermittelt werden.

Wenn die **_CRTDBG_ALLOC_MEM_DF** -Bitfeld des der [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) -Kennzeichens nicht aktiviert ist, **_CrtDoForAllClientObjects** wird sofort zurückgegeben. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, werden Aufrufe von **_CrtDoForAllClientObjects** werden während der vorverarbeitung entfernt.

Weitere Informationen zu den **_CLIENT_BLOCK** geben, und es durch andere Debugfunktionen verwendet werden kann, finden Sie unter [Blocktypen auf dem Debugheap](/visualstudio/debugger/crt-debug-heap-details). Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details).

Wenn *Pfn* ist **NULL**, Handler für ungültige Parameter aufgerufen, siehe [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, [Errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) nastaven NA hodnotu **EINVAL** und die Funktion zurück.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_CrtDoForAllClientObjects**|\<crtdbg.h>, \<errno.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

**Bibliotheken:** Nur Debugversionen von C-Laufzeitbibliotheken.

## <a name="see-also"></a>Siehe auch

[Debugroutinen](../../c-runtime-library/debug-routines.md)<br/>
[_CrtSetDbgFlag](crtsetdbgflag.md)<br/>
[Für den Heapzustand](/visualstudio/debugger/crt-debug-heap-details)<br/>
[_CrtReportBlockType](crtreportblocktype.md)<br/>

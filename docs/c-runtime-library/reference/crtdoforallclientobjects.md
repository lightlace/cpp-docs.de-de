---
title: _CrtDoForAllClientObjects | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
ms.workload:
- cplusplus
ms.openlocfilehash: 83c555899807c9236b803b0576bc8bf6884fd944
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
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

*Pfn* Zeiger auf die von der Anwendung bereitgestellten Rückruffunktion. Der erste Parameter für diese Funktion zeigt auf die Daten. Der zweite Parameter ist der Kontextzeiger, der für den Aufruf übergeben wird **_CrtDoForAllClientObjects**.

*Kontext* Zeiger zu dem von der Anwendung bereitgestellten Kontext, an der Anwendung bereitgestellte Funktion übergeben.

## <a name="remarks"></a>Hinweise

Die **_CrtDoForAllClientObjects** -Funktion sucht der verknüpften Heapliste für Speicherblöcke der **_CLIENT_BLOCK** -Typ und ruft die die Anwendung bereitgestellte Funktion aus, wenn ein Block dieses Typs gefunden wird. Der gefundene Block und der *Kontext* Parameter als Argumente an der Anwendung bereitgestellte Funktion übergeben werden. Während des Debuggens kann eine Anwendung eine bestimmte Gruppe von Zuordnungen nachverfolgen, indem explizit die Debugheapfunktionen aufruft zum Belegen des Speichers und gibt an, dass die Blöcke zugewiesen werden, die **_CLIENT_BLOCK** Blocktyp. Diese Blöcke können dann einzeln nachverfolgt und während der Erkennung von Speicherverlusten und der Berichterstellung von Speicherzuständen unterschiedlich übermittelt werden.

Wenn die **_CRTDBG_ALLOC_MEM_DF** -Bitfeld des der [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) Flag ist nicht eingeschaltet, **_CrtDoForAllClientObjects** wird sofort zurückgegeben. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, werden Aufrufe von **_CrtDoForAllClientObjects** während der vorverarbeitung entfernt.

Weitere Informationen zu den **_CLIENT_BLOCK** geben und seiner Verwendung durch andere Debugfunktionen werden kann, finden Sie unter [Blocktypen auf dem Debugheap](/visualstudio/debugger/crt-debug-heap-details). Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details).

Wenn *Pfn* ist **NULL**, den Handler für ungültige Parameter aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, [Errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) festgelegt ist, um **EINVAL** und die Funktion zurückgibt.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_CrtDoForAllClientObjects**|\<crtdbg.h>, \<errno.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

**Bibliotheken:** Nur Debugversionen von C-Laufzeitbibliotheken.

## <a name="see-also"></a>Siehe auch

[Debugroutinen](../../c-runtime-library/debug-routines.md)<br/>
[_CrtSetDbgFlag](crtsetdbgflag.md)<br/>
[Für den Heapzustand](/visualstudio/debugger/crt-debug-heap-details)<br/>
[_CrtReportBlockType](crtreportblocktype.md)<br/>

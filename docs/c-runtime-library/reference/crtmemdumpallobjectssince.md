---
title: _CrtMemDumpAllObjectsSince | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _CrtMemDumpAllObjectsSince
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
- CrtMemDumpAllObjectsSince
- _CrtMemDumpAllObjectsSince
dev_langs:
- C++
helpviewer_keywords:
- _CrtMemDumpAllObjectsSince function
- CrtMemDumpAllObjectsSince function
ms.assetid: c48a447a-e6bb-475c-9271-a3021182a0dc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 24cf01facaba326c36454ea5410da8dbb05848f2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32396868"
---
# <a name="crtmemdumpallobjectssince"></a>_CrtMemDumpAllObjectsSince

Gibt Informationen zu Objekten im Heap ab Beginn der Programmausführung oder ab einem angegebenen Heapzustand aus (nur Debugversion).

## <a name="syntax"></a>Syntax

```C
void _CrtMemDumpAllObjectsSince(
   const _CrtMemState *state
);
```

### <a name="parameters"></a>Parameter

*Status* Zeiger zum Heapzustand Dump-Sicherungen aus beginnen oder **NULL**.

## <a name="remarks"></a>Hinweise

Die **_CrtMemDumpAllObjectsSince** Funktion gibt die debugheaderinformationen von Objekten im Heap in einen Benutzer lesbaren Form zugeordnet. Die Dumpinformationen können von der Anwendung zum Nachverfolgen von Zuordnungen und zum Erkennen von Speicherproblemen verwendet werden. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, werden Aufrufe von **_CrtMemDumpAllObjectsSince** während der vorverarbeitung entfernt.

**_CrtMemDumpAllObjectsSince** verwendet den Wert der *Zustand* Parameter an, wo der dumpvorgang initiiert werden soll. Dump-Sicherungen aus einem angegebenen Heapzustand beginnen die *Status* Parameter muss ein Zeiger auf eine **_CrtMemState** -Struktur, die durch ausgefüllt [_CrtMemCheckpoint](crtmemcheckpoint.md) vor **_CrtMemDumpAllObjectsSince** aufgerufen wurde. Wenn *Status* ist **NULL**, startet die Funktion die Ausgabe ab Beginn der Ausführung des Programms.

Wenn die Installation der Anwendung einer Hookfunktion Dump durch Aufrufen [_CrtSetDumpClient](crtsetdumpclient.md), und klicken Sie dann jedes Mal, wenn **_CrtMemDumpAllObjectsSince** gibt Informationen über eine **_CLIENT_BLOCK** Typ des Blocks, der Anwendung bereitgestellte dumpfunktion ebenfalls aufgerufen. Standardmäßig sind interne C-laufzeitblöcke (**_CRT_BLOCK**) sind nicht in speicherabbildvorgängen enthalten. Die [_CrtSetDbgFlag](crtsetdbgflag.md) -Funktion kann verwendet werden, zum Aktivieren der **_CRTDBG_CHECK_CRT_DF** -Bit von **_crtDbgFlag** um diese Blöcke einzuschließen. Außerdem werden die Blöcke, die als „freigegeben“ oder „ignoriert“ markiert wurden (**_FREE_BLOCK**, **_IGNORE_BLOCK**) nicht im Speicherabbild berücksichtigt.

Weitere Informationen über heapzustandsfunktionen und die **_CrtMemState** -Struktur, finden Sie unter [den Heapzustand](/visualstudio/debugger/crt-debug-heap-details). Weitere Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_CrtMemDumpAll-ObjectsSince**|\<crtdbg.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Nur Debugversionen von [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Beispiel

Ein Beispiel zum Verwenden von **_CrtMemDumpAllObjectsSince**, finden Sie unter [crt_dbg2](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg2).

## <a name="see-also"></a>Siehe auch

[Debugroutinen](../../c-runtime-library/debug-routines.md)<br/>
[_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)<br/>

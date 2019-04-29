---
title: _CrtMemDumpAllObjectsSince
ms.date: 11/04/2016
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
helpviewer_keywords:
- _CrtMemDumpAllObjectsSince function
- CrtMemDumpAllObjectsSince function
ms.assetid: c48a447a-e6bb-475c-9271-a3021182a0dc
ms.openlocfilehash: 7de0ee9ff166af6336a8d14aa0dbd07dbd7d23fc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62347456"
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

*state*<br/>
Zeiger zum Heapzustand, ab dem die Ausgabe erfolgen soll, oder **NULL**

## <a name="remarks"></a>Hinweise

Die **_CrtMemDumpAllObjectsSince** Funktion gibt die debugheaderinformationen von Objekten im Heap in einen Benutzer lesbaren Form zugeordnet. Die Dumpinformationen können von der Anwendung zum Nachverfolgen von Zuordnungen und zum Erkennen von Speicherproblemen verwendet werden. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, werden Aufrufe von **_CrtMemDumpAllObjectsSince** werden während der vorverarbeitung entfernt.

**_CrtMemDumpAllObjectsSince** verwendet den Wert der *Zustand* Parameter, um zu bestimmen, wo der dumpvorgang initiiert. Um Ausgabe ab einem angegebenen Heapzustand zu beginnen die *Zustand* Parameter muss ein Zeiger auf eine **_CrtMemState** -Struktur, die von gefüllt wurde [_CrtMemCheckpoint](crtmemcheckpoint.md) vor **_CrtMemDumpAllObjectsSince** aufgerufen wurde. Wenn *Zustand* ist **NULL**, startet die Funktion die Ausgabe ab Beginn der programmausführung.

Wenn die Anwendung eine durch den Aufruf installiert hat [_CrtSetDumpClient](crtsetdumpclient.md), und klicken Sie dann jedes Mal, wenn **_CrtMemDumpAllObjectsSince** gibt Informationen über eine **_CLIENT_BLOCK** Typ des Blocks, der Anwendung bereitgestellte dumpfunktion ebenfalls aufgerufen. Standardmäßig sind interne C-laufzeitblöcke (**_CRT_BLOCK**) sind nicht in speicherabbildvorgängen enthalten. Die [_CrtSetDbgFlag](crtsetdbgflag.md) Funktion kann verwendet werden, zum Aktivieren der **_CRTDBG_CHECK_CRT_DF** -Bit von **_crtDbgFlag** um diese Blöcke einzuschließen. Außerdem werden die Blöcke, die als „freigegeben“ oder „ignoriert“ markiert wurden (**_FREE_BLOCK**, **_IGNORE_BLOCK**) nicht im Speicherabbild berücksichtigt.

Weitere Informationen über heapzustandsfunktionen und die **_CrtMemState** Struktur, siehe [Heap State Reporting Functions](/visualstudio/debugger/crt-debug-heap-details). Weitere Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_CrtMemDumpAll-ObjectsSince**|\<crtdbg.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Nur Debugversionen von [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Beispiel

Ein Beispiel zur Verwendung **_CrtMemDumpAllObjectsSince**, finden Sie unter [crt_dbg2](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg2).

## <a name="see-also"></a>Siehe auch

[Debugroutinen](../../c-runtime-library/debug-routines.md)<br/>
[_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)<br/>

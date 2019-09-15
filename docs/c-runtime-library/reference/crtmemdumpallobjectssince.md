---
title: _CrtMemDumpAllObjectsSince
ms.date: 11/04/2016
api_name:
- _CrtMemDumpAllObjectsSince
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
- CrtMemDumpAllObjectsSince
- _CrtMemDumpAllObjectsSince
helpviewer_keywords:
- _CrtMemDumpAllObjectsSince function
- CrtMemDumpAllObjectsSince function
ms.assetid: c48a447a-e6bb-475c-9271-a3021182a0dc
ms.openlocfilehash: 9e3793e9b88c593968b108e2801e24476417603c
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70942366"
---
# <a name="_crtmemdumpallobjectssince"></a>_CrtMemDumpAllObjectsSince

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

Die **_CrtMemDumpAllObjectsSince** -Funktion sichert die Debug-Header Informationen von Objekten, die im Heap zugeordnet sind, in einem vom Benutzer lesbaren Format. Die Dumpinformationen können von der Anwendung zum Nachverfolgen von Zuordnungen und zum Erkennen von Speicherproblemen verwendet werden. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, werden Aufrufe von **_CrtMemDumpAllObjectsSince** während der Vorverarbeitung entfernt.

**_CrtMemDumpAllObjectsSince** verwendet den Wert des *State* -Parameters, um zu bestimmen, wo der dumpvorgang initiiert werden soll. Der *State* -Parameter muss ein Zeiger auf eine **_CrtMemState** -Struktur sein, die von [_CrtMemCheckpoint](crtmemcheckpoint.md) ausgefüllt wurde, bevor **_CrtMemDumpAllObjectsSince** aufgerufen wurde, um mit dem Sichern eines angegebenen Heap Zustands zu beginnen. Wenn *State* den Wert **null**hat, beginnt die Funktion mit dem Abbild ab Beginn der Programmausführung.

Wenn die Anwendung eine dumphookfunktion durch Aufrufen von [_CrtSetDumpClient](crtsetdumpclient.md)installiert hat, wird jedes Mal, wenn **_CrtMemDumpAllObjectsSince** Informationen über einen **_CLIENT_BLOCK** -Blocktyp abruft, das von der Anwendung bereitgestellte Dumpmodul aufgerufen. auch funktionieren. Standardmäßig sind interne C-Lauf Zeitblöcke ( **_CRT_BLOCK**) nicht in Speicher Abbild Vorgängen enthalten. Die [_CrtSetDbgFlag](crtsetdbgflag.md) -Funktion kann verwendet werden, um das **_CRTDBG_CHECK_CRT_DF** -Bit von **_crtDbgFlag** zu aktivieren, um diese Blöcke einzuschließen. Außerdem werden die Blöcke, die als „freigegeben“ oder „ignoriert“ markiert wurden ( **_FREE_BLOCK**, **_IGNORE_BLOCK**) nicht im Speicherabbild berücksichtigt.

Weitere Informationen zu Heap Zustands Funktionen und der **_CrtMemState** -Struktur finden Sie unter [Heap State Reporting Functions](/visualstudio/debugger/crt-debug-heap-details). Weitere Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_CrtMemDumpAll-ObjectsSince**|\<crtdbg.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Nur Debugversionen von [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Beispiel

Ein Beispiel für die Verwendung von **_CrtMemDumpAllObjectsSince**finden Sie unter [crt_dbg2](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg2).

## <a name="see-also"></a>Siehe auch

[Debugroutinen](../../c-runtime-library/debug-routines.md)<br/>
[_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)<br/>

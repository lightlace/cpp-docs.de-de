---
title: _CrtSetDumpClient
ms.date: 11/04/2016
apiname:
- _CrtSetDumpClient
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
- _CrtSetDumpClient
- CrtSetDumpClient
helpviewer_keywords:
- _CrtSetDumpClient function
- CrtSetDumpClient function
ms.assetid: f3dd06d0-c331-4a12-b68d-25378d112033
ms.openlocfilehash: 09f319f6298dbec6b229b2923bd86fc9b50314de
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2019
ms.locfileid: "64342992"
---
# <a name="crtsetdumpclient"></a>_CrtSetDumpClient

Installiert eine anwendungsdefinierte Funktion zum Sichern **_CLIENT_BLOCK** -typspeicherblöcke (nur Debugversion).

## <a name="syntax"></a>Syntax

```C
_CRT_DUMP_CLIENT _CrtSetDumpClient( _CRT_DUMP_CLIENT dumpClient );
```

### <a name="parameters"></a>Parameter

*dumpClient*<br/>
Die neue clientdefinierte Speicherabbildfunktion, die mit dem Debug-Speicherabbildprozess der C-Laufzeit verknüpft werden soll.

## <a name="return-value"></a>Rückgabewert

Gibt die zuvor definierte Client-Blockdumpfunktion zurück.

## <a name="remarks"></a>Hinweise

Die **_CrtSetDumpClient** -Funktion ermöglicht der Anwendung eine eigene Funktion in gespeicherten für dumpobjekte verknüpfen **_CLIENT_BLOCK** Speicherblöcke in der C-Laufzeit debug-speicherabbildprozess. Daher jedes Mal eine Debugversion blockdumpfunktion wie z. B. [_CrtMemDumpAllObjectsSince](crtmemdumpallobjectssince.md) oder [_CrtDumpMemoryLeaks](crtdumpmemoryleaks.md) sichert eine **_CLIENT_BLOCK** Speicherblock, der Anwendung dumpfunktion wird auch aufgerufen werden. **_CrtSetDumpClient** bietet eine einfache Methode zum Erkennen von Speicherverlusten und validieren oder Übermitteln des Inhalts der Daten in einer Anwendung **_CLIENT_BLOCK** Blöcke. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, werden Aufrufe von **_CrtSetDumpClient** werden während der vorverarbeitung entfernt.

Die **_CrtSetDumpClient** -Funktion installiert die neue anwendungsdefinierte dumpfunktion in angegebenen *DumpClient* und gibt Sie die zuvor definierte dumpfunktion zurück. Beispiel einer Client-Blockdumpfunktion:

```C
void DumpClientFunction( void *userPortion, size_t blockSize );
```

Die *UserPortion* Argument ist ein Zeiger auf den Anfang des benutzerdatenteils des Speicherblocks und *BlockSize* gibt die Größe des belegten Speicherblocks in Bytes. Die Client-blockdumpfunktion muss zurückgeben **"void"**. Der Zeiger auf clientdumpfunktion, der an übergebene **_CrtSetDumpClient** ist vom Typ **_CRT_DUMP_CLIENT**, wie in "CRTDBG.h" definiert:

```C
typedef void (__cdecl *_CRT_DUMP_CLIENT)( void *, size_t );
```

Weitere Informationen zu Funktionen, die Vorgänge an **_CLIENT_BLOCK** -typspeicherblöcke, finden Sie unter [Clientblöcke](/visualstudio/debugger/client-block-hook-functions). Die [_CrtReportBlockType](crtreportblocktype.md)-Funktion kann zum Zurückgeben von Informationen zu Blocktypen und -untertypen verwendet werden.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_CrtSetDumpClient**|\<crtdbg.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Nur Debugversionen der [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Siehe auch

[Debugroutinen](../../c-runtime-library/debug-routines.md)<br/>
[_CrtReportBlockType](crtreportblocktype.md)<br/>
[_CrtGetDumpClient](crtgetdumpclient.md)<br/>

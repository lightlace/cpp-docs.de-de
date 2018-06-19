---
title: _CrtSetDumpClient | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- _CrtSetDumpClient function
- CrtSetDumpClient function
ms.assetid: f3dd06d0-c331-4a12-b68d-25378d112033
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8d5fecc90b4b7259f1440a0a0d86277c769c4e16
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32397222"
---
# <a name="crtsetdumpclient"></a>_CrtSetDumpClient

Installiert eine anwendungsdefinierte Funktion zum Sichern **_CLIENT_BLOCK** -typspeicherblöcken (nur Debugversion).

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

Die **_CrtSetDumpClient** -Funktion ermöglicht der Anwendung zu verbinden, eine eigene Funktion für dumpobjekte in gespeicherten **_CLIENT_BLOCK** Speicherblöcke in der C-Laufzeit debug-speicherabbildprozess. Deshalb jedes Mal eine Debug blockdumpfunktion wie z. B. [_CrtMemDumpAllObjectsSince](crtmemdumpallobjectssince.md) oder [_CrtDumpMemoryLeaks](crtdumpmemoryleaks.md) sichert eine **_CLIENT_BLOCK** Speicherblock, der Anwendungsverzeichnis dumpfunktion wird ebenfalls aufgerufen. **_CrtSetDumpClient** bietet eine einfache Methode zum Erkennen von Speicherverlusten und validieren, oder Übermitteln des Inhalts der Daten in einer Anwendung **_CLIENT_BLOCK** blockiert. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, werden Aufrufe von **_CrtSetDumpClient** während der vorverarbeitung entfernt.

Die **_CrtSetDumpClient** -Funktion installiert die neue anwendungsdefinierte dumpfunktion im angegebenen *DumpClient* und gibt die zuvor definierte dumpfunktion zurück. Beispiel einer Client-Blockdumpfunktion:

```C
void DumpClientFunction( void *userPortion, size_t blockSize );
```

Die *UserPortion* Argument ist ein Zeiger auf den Anfang des benutzerdatenteils des Speicherblocks und *BlockSize* gibt die Größe des belegten Speicherblocks in Bytes. Die Client-blockdumpfunktion muss zurückgeben **"void"**. Der Zeiger auf clientdumpfunktion, der an übergebene **_CrtSetDumpClient** ist vom Typ **_CRT_DUMP_CLIENT**, wie in "CRTDBG.h" definiert:

```C
typedef void (__cdecl *_CRT_DUMP_CLIENT)( void *, size_t );
```

Weitere Informationen zu Funktionen, die Vorgänge an **_CLIENT_BLOCK** -typspeicherblöcken, finden Sie unter [Hookfunktionen für Client-Block](/visualstudio/debugger/client-block-hook-functions). Die [_CrtReportBlockType](crtreportblocktype.md)-Funktion kann zum Zurückgeben von Informationen zu Blocktypen und -untertypen verwendet werden.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_CrtSetDumpClient**|\<crtdbg.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Nur Debugversionen der [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Siehe auch

[Debugroutinen](../../c-runtime-library/debug-routines.md)<br/>
[_CrtReportBlockType](crtreportblocktype.md)<br/>
[_CrtGetDumpClient](crtgetdumpclient.md)<br/>

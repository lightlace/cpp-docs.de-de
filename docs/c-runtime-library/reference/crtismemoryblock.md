---
title: _CrtIsMemoryBlock
ms.date: 11/04/2016
api_name:
- _CrtIsMemoryBlock
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
- CrtlsMemoryBlock
- _CrtIsMemoryBlock
helpviewer_keywords:
- _CrtIsMemoryBlock function
- CrtIsMemoryBlock function
ms.assetid: f7cbbc60-3690-4da0-a07b-68fd7f250273
ms.openlocfilehash: f29745acd06f6f5b3fa96367444e800bdc3e8e3a
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70938740"
---
# <a name="_crtismemoryblock"></a>_CrtIsMemoryBlock

Überprüft, ob sich ein angegebener Speicherblock im lokalen Heap befindet und ob er einen gültigen Debugheap-Blocktypbezeichner hat (nur Debugversion).

## <a name="syntax"></a>Syntax

```C
int _CrtIsMemoryBlock(
   const void *userData,
   unsigned int size,
   long *requestNumber,
   char **filename,
   int *linenumber
);
```

### <a name="parameters"></a>Parameter

*userData*<br/>
Zeiger auf den Anfang des zu überprüfenden Speicherblocks.

*size*<br/>
Größe des angegebenen Blocks (in Bytes).

*requestNumber*<br/>
Ein Zeiger auf die Zuordnungs Nummer des Blocks oder **null**.

*filename*<br/>
Zeiger auf den Namen der Quelldatei, die den Block angefordert hat, oder **null**.

*linenumber*<br/>
Ein Zeiger auf die Zeilennummer in der Quelldatei oder **null**.

## <a name="return-value"></a>Rückgabewert

**_CrtIsMemoryBlock** gibt **true** zurück, wenn sich der angegebene Speicherblock im lokalen Heap befindet und über einen gültigen Debugheap-Blocktyp Bezeichner verfügt. Andernfalls gibt die Funktion **false**zurück.

## <a name="remarks"></a>Hinweise

Die **_CrtIsMemoryBlock** -Funktion überprüft, ob sich ein angegebener Speicherblock im lokalen Heap der Anwendung befindet und über einen gültigen Blocktyp Bezeichner verfügt. Diese Funktion kann auch verwendet werden, um die Bestellnummer der Objektzuordnung und den Quelldateinamen/die Zeilennummer abzurufen, wo die Speicherblockbelegung ursprünglich angefordert wurde. Das übergeben von Werten ungleich**null** für die Parameter *requestNumber*, *filename*oder *LineNumber* bewirkt, dass **_CrtIsMemoryBlock** diese Parameter auf die Werte im debugheader des Speicherblocks festgelegt, wenn der Block im lokaler Heap. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, werden Aufrufe von **_CrtIsMemoryBlock** während der Vorverarbeitung entfernt.

Wenn **_CrtIsMemoryBlock** fehlschlägt, wird **false** zurückgegeben, und die Ausgabeparameter werden auf die Standardwerte initialisiert: *requestNumber* und **LineNumber** werden auf 0 festgelegt, und *filename* ist auf **null**festgelegt.

Da diese Funktion **TRUE** oder **FALSE** zurückgibt, kann sie an eine der [_ASSERT](assert-asserte-assert-expr-macros.md)-Makros übergeben werden, um einen einfachen Debug-Fehlerbehandlungsmechanismus zu erstellen. Im folgenden Beispiel wird ein Assertionsfehler ausgelöst, wenn sich die angegebene Adresse nicht im lokalen Heap befindet:

```C
_ASSERTE( _CrtIsMemoryBlock( userData, size, &requestNumber,
          &filename, &linenumber ) );
```

Weitere Informationen dazu, wie **_CrtIsMemoryBlock** mit anderen Debugfunktionen und-Makros verwendet werden kann, finden Sie unter [Makros für die Bericht](/visualstudio/debugger/macros-for-reporting)Erstellung. Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_CrtIsMemoryBlock**|\<crtdbg.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Nur Debugversionen von [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Beispiel

Weitere Informationen hierzu finden Sie im Beispiel für das Thema [_CrtIsValidHeapPointer](crtisvalidheappointer.md).

## <a name="see-also"></a>Siehe auch

[Debugroutinen](../../c-runtime-library/debug-routines.md)<br/>

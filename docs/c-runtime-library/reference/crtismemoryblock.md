---
title: _CrtIsMemoryBlock
ms.date: 11/04/2016
apiname:
- _CrtIsMemoryBlock
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
- CrtlsMemoryBlock
- _CrtIsMemoryBlock
helpviewer_keywords:
- _CrtIsMemoryBlock function
- CrtIsMemoryBlock function
ms.assetid: f7cbbc60-3690-4da0-a07b-68fd7f250273
ms.openlocfilehash: c4a85ebeb45552c6f5355853de2a45766d6bc984
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62339896"
---
# <a name="crtismemoryblock"></a>_CrtIsMemoryBlock

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
Zeiger zur Belegungsnummer des Blocks oder **NULL**.

*filename*<br/>
Zeiger auf den Namen der Quelldatei, die den Block angefordert oder **NULL**.

*linenumber*<br/>
Zeiger auf die Nummer der Zeile in der Quelldatei oder **NULL**.

## <a name="return-value"></a>Rückgabewert

**_CrtIsMemoryBlock** gibt **"true"** , wenn der angegebene Speicherblock im lokalen Heap befindet und eine gültige Debug Heap über blocktypbezeichner verfügt; andernfalls gibt die Funktion **"false"**.

## <a name="remarks"></a>Hinweise

Die **_CrtIsMemoryBlock** Funktion überprüft, ob ein angegebener Speicherblock im lokalen Heap der Anwendung befindet und sie einen gültigen blocktypbezeichner hat. Diese Funktion kann auch verwendet werden, um die Bestellnummer der Objektzuordnung und den Quelldateinamen/die Zeilennummer abzurufen, wo die Speicherblockbelegung ursprünglich angefordert wurde. Übergeben von nicht -**NULL** Werte für die *RequestNumber*, *Filename*, oder *Linenumber* Parameter bewirkt, dass **_ CrtIsMemoryBlock** für die Werte im debugheader des Speicherblocks, diese Parameter festzulegen, wenn den Block im lokalen Heap gefunden. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, werden Aufrufe von **_CrtIsMemoryBlock** werden während der vorverarbeitung entfernt.

Wenn **_CrtIsMemoryBlock** fehlschlägt, wird **"false"** und die Output-Parameter mit Standardwerten initialisiert werden: *RequestNumber* und **LineNumber**  werden auf 0 festgelegt und *Filename* nastaven NA hodnotu **NULL**.

Da diese Funktion **TRUE** oder **FALSE** zurückgibt, kann sie an eine der [_ASSERT](assert-asserte-assert-expr-macros.md)-Makros übergeben werden, um einen einfachen Debug-Fehlerbehandlungsmechanismus zu erstellen. Im folgenden Beispiel wird ein Assertionsfehler ausgelöst, wenn sich die angegebene Adresse nicht im lokalen Heap befindet:

```C
_ASSERTE( _CrtIsMemoryBlock( userData, size, &requestNumber,
          &filename, &linenumber ) );
```

Weitere Informationen dazu, wie **_CrtIsMemoryBlock** kann mit anderen Debugfunktionen und-Makros verwendet werden, finden Sie unter [Makros für die Berichterstellung](/visualstudio/debugger/macros-for-reporting). Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details).

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

---
title: _CrtIsMemoryBlock | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- _CrtIsMemoryBlock function
- CrtIsMemoryBlock function
ms.assetid: f7cbbc60-3690-4da0-a07b-68fd7f250273
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 45331186cca5aab3c7971ba404d7b6da98139130
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2018
ms.locfileid: "34450731"
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

*Benutzerdaten*<br/>
Zeiger auf den Anfang des zu überprüfenden Speicherblocks.

*size*<br/>
Größe des angegebenen Blocks (in Bytes).

*requestNumber*<br/>
Zeiger zur Belegungsnummer des Blocks oder **NULL**.

*filename*<br/>
Zeiger auf den Namen der Quelldatei, die den Block angefordert oder **NULL**.

*linenumber*<br/>
Zeiger auf die Zeilennummer in der Quelldatei oder **NULL**.

## <a name="return-value"></a>Rückgabewert

**_CrtIsMemoryBlock** gibt **"true"** , wenn der angegebene Speicherblock im lokalen Heap befindet und einen gültige Debug Heap-blocktypbezeichner hat, andernfalls gibt die Funktion **"false"**.

## <a name="remarks"></a>Hinweise

Die **_CrtIsMemoryBlock** Funktion überprüft, ob ein angegebener Speicherblock im lokalen Heap der Anwendung befindet und über einen gültigen blocktypbezeichner verfügt. Diese Funktion kann auch verwendet werden, um die Bestellnummer der Objektzuordnung und den Quelldateinamen/die Zeilennummer abzurufen, wo die Speicherblockbelegung ursprünglich angefordert wurde. Übergeben von nicht -**NULL** Werte für die *RequestNumber*, *Filename*, oder *Linenumber* Parameter Ursachen **_ CrtIsMemoryBlock** auf die Werte im debugheader des Speicherblocks, diese Parameter festlegen, wenn den Block im lokalen Heap gefunden wird. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, werden Aufrufe von **_CrtIsMemoryBlock** während der vorverarbeitung entfernt.

Wenn **_CrtIsMemoryBlock** fehlschlägt, wird **"false"** und die Ausgabeparameter werden mit Standardwerten initialisiert: *RequestNumber* und **LineNumber**  werden auf 0 festgelegt und *Filename* festgelegt ist, um **NULL**.

Da diese Funktion **TRUE** oder **FALSE** zurückgibt, kann sie an eine der [_ASSERT](assert-asserte-assert-expr-macros.md)-Makros übergeben werden, um einen einfachen Debug-Fehlerbehandlungsmechanismus zu erstellen. Im folgenden Beispiel wird ein Assertionsfehler ausgelöst, wenn sich die angegebene Adresse nicht im lokalen Heap befindet:

```C
_ASSERTE( _CrtIsMemoryBlock( userData, size, &requestNumber,
          &filename, &linenumber ) );
```

Weitere Informationen dazu, wie **_CrtIsMemoryBlock** kann mit anderen Debugfunktionen und-Makros verwendet werden, finden Sie unter [Makros für die Berichterstellung](/visualstudio/debugger/macros-for-reporting). Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_CrtIsMemoryBlock**|\<crtdbg.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Nur Debugversionen von [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Beispiel

Weitere Informationen hierzu finden Sie im Beispiel für das Thema [_CrtIsValidHeapPointer](crtisvalidheappointer.md).

## <a name="see-also"></a>Siehe auch

[Debugroutinen](../../c-runtime-library/debug-routines.md)<br/>

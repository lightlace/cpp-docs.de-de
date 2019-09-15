---
title: _CrtIsValidPointer
ms.date: 11/04/2016
api_name:
- _CrtIsValidPointer
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
- CrtlsValidPointer
- _CrtIsValidPointer
helpviewer_keywords:
- CrtIsValidPointer function
- _CrtIsValidPointer function
ms.assetid: 91c35590-ea5e-450f-a15d-ad8d62ade1fa
ms.openlocfilehash: 490d2dea097935dee2cd2a003aa28e32f1ced69d
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70938774"
---
# <a name="_crtisvalidpointer"></a>_CrtIsValidPointer

Stellt sicher, dass ein Zeiger nicht NULL ist. Überprüft in älteren Versionen der C-Laufzeitbibliothek als Visual Studio 2010, ob ein angegebener Speicherbereich für Lese- und Schreibvorgänge gültig ist (nur Debugversion).

## <a name="syntax"></a>Syntax

```C
int _CrtIsValidPointer(
   const void *address,
   unsigned int size,
   int access
);
```

### <a name="parameters"></a>Parameter

*address*<br/>
Weist auf den Anfang des Speicherbereichs zum Prüfen der Gültigkeit.

*size*<br/>
Die Größe des angegebenen Speicherbereichs (in Bytes).

*Zugriff*<br/>
Für den Speicherbereich zu bestimmende Lese/Schreib-Barrierefreiheit.

## <a name="return-value"></a>Rückgabewert

**_CrtIsValidPointer** gibt true zurück, wenn der angegebene Zeiger nicht NULL ist. Gibt in älteren CRT-Bibliotheksversionen als Visual Studio TRUE zurück, wenn der Speicherbereich für den angegebenen Vorgang bzw. die Vorgänge gültig ist. Andernfalls gibt die Funktion FALSE zurück.

## <a name="remarks"></a>Hinweise

Beginnend mit der CRT-Bibliothek in Visual Studio 2010 werden die *Größen* -und *Zugriffs* Parameter ignoriert, und **_CrtIsValidPointer** überprüft nur, ob die angegebene *Adresse* nicht NULL ist. Da sich dieser Test leicht manuell ausführen lässt, wird nicht empfohlen, diese Funktion zu verwenden. In Versionen vor Visual Studio 2010 überprüft die Funktion, ob der Speicherbereich, der bei der *Adresse* beginnt und für die *Größe* von Bytes erweitert wird, für die angegebenen Barrierefreiheits Vorgänge gültig ist. Wenn *Access* auf true festgelegt ist, wird der Speicherbereich für Lese-und Schreibvorgänge überprüft. Wenn der *Zugriff* auf false ist, wird der Speicherbereich nur für Lesevorgänge überprüft. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, werden Aufrufe von **_CrtIsValidPointer** während der Vorverarbeitung entfernt.

Da diese Funktion TRUE oder FALSE zurückgibt, kann sie an eine der [_ASSERT](assert-asserte-assert-expr-macros.md)-Makros übergeben werden, um einen einfachen Debug-Fehlerbehandlungsmechanismus zu erstellen. Im folgenden Beispiel wird eine Assertionsmeldung ausgelöst, wenn der Speicherbereich für Lese- und Schreibvorgänge ungültig ist:

```C
_ASSERTE( _CrtIsValidPointer( address, size, TRUE ) );
```

Weitere Informationen dazu, wie **_CrtIsValidPointer** mit anderen Debugfunktionen und-Makros verwendet werden kann, finden Sie unter [Makros für die Bericht](/visualstudio/debugger/macros-for-reporting)Erstellung. Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_CrtIsValidPointer**|\<crtdbg.h>|

**_CrtIsValidPointer** ist eine Microsoft-Erweiterung. Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Nur Debugversionen von [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Beispiel

Weitere Informationen hierzu finden Sie im Beispiel für das Thema [_CrtIsValidHeapPointer](crtisvalidheappointer.md).

## <a name="see-also"></a>Siehe auch

[Debugroutinen](../../c-runtime-library/debug-routines.md)<br/>

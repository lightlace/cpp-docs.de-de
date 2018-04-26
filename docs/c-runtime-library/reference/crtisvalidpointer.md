---
title: _CrtIsValidPointer | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _CrtIsValidPointer
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
- CrtlsValidPointer
- _CrtIsValidPointer
dev_langs:
- C++
helpviewer_keywords:
- CrtIsValidPointer function
- _CrtIsValidPointer function
ms.assetid: 91c35590-ea5e-450f-a15d-ad8d62ade1fa
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 70d1cf7ac6c1f5af76457608863524cba60a39d5
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="crtisvalidpointer"></a>_CrtIsValidPointer

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

**_CrtIsValidPointer** gibt "true" zurück, wenn der angegebene Zeiger nicht null ist. Gibt in älteren CRT-Bibliotheksversionen als Visual Studio TRUE zurück, wenn der Speicherbereich für den angegebenen Vorgang bzw. die Vorgänge gültig ist. Andernfalls gibt die Funktion FALSE zurück.

## <a name="remarks"></a>Hinweise

Beginnend mit der CRT-Bibliothek in Visual Studio 2010 die *Größe* und *Zugriff* Parameter werden ignoriert, und **_CrtIsValidPointer** stellt sicher, dass nur die angegebenen *Adresse* ist ungleich null. Da sich dieser Test leicht manuell ausführen lässt, wird nicht empfohlen, diese Funktion zu verwenden. In Versionen vor Visual Studio 2010, die Funktion stellt sicher, dass der Speicherbereich, wobei am *Adresse* und die Erweiterung für *Größe* Bytes für die angegebenen barrierefreiheitsvorgänge gültig ist. Wenn *Zugriff* ist auf "true" festgelegt, wird der Speicherbereich zum Lesen und Schreiben von überprüft. Wenn *Zugriff* "false", wird der Speicherbereich nur für Lesevorgänge überprüft wird. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, werden Aufrufe von **_CrtIsValidPointer** während der vorverarbeitung entfernt.

Da diese Funktion TRUE oder FALSE zurückgibt, kann sie an eine der [_ASSERT](assert-asserte-assert-expr-macros.md)-Makros übergeben werden, um einen einfachen Debug-Fehlerbehandlungsmechanismus zu erstellen. Im folgenden Beispiel wird eine Assertionsmeldung ausgelöst, wenn der Speicherbereich für Lese- und Schreibvorgänge ungültig ist:

```C
_ASSERTE( _CrtIsValidPointer( address, size, TRUE ) );
```

Weitere Informationen dazu, wie **_CrtIsValidPointer** kann mit anderen Debugfunktionen und-Makros verwendet werden, finden Sie unter [Makros für die Berichterstellung](/visualstudio/debugger/macros-for-reporting). Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_CrtIsValidPointer**|\<crtdbg.h>|

**_CrtIsValidPointer** ist eine Microsoft-Erweiterung. Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Nur Debugversionen von [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Beispiel

Weitere Informationen hierzu finden Sie im Beispiel für das Thema [_CrtIsValidHeapPointer](crtisvalidheappointer.md).

## <a name="see-also"></a>Siehe auch

[Debugroutinen](../../c-runtime-library/debug-routines.md)<br/>

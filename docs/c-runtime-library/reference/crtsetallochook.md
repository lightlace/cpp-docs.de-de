---
title: _CrtSetAllocHook | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _CrtSetAllocHook
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
- _CrtSetAllocHook
- CrtSetAllocHook
dev_langs:
- C++
helpviewer_keywords:
- _CrtSetAllocHook function
- CrtSetAllocHook function
ms.assetid: 405df37b-2fd1-42c8-83bc-90887f17f29d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8d86072ceb41b966adfca298152b6209450aace3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="crtsetallochook"></a>_CrtSetAllocHook

Installiert eine clientdefinierte Zuordnungsfunktion, indem sie mit dem C-Laufzeit-Debugspeicherbelegungsprozess verknüpft wird (nur Debugversion).

## <a name="syntax"></a>Syntax

```C
_CRT_ALLOC_HOOK _CrtSetAllocHook(
   _CRT_ALLOC_HOOK allocHook
);
```

### <a name="parameters"></a>Parameter

*allocHook*<br/>
Die neue clientdefinierte Zuordnungsfunktion, die mit dem C-Laufzeit-Debugspeicherbelegungsprozess verknüpft werden soll.

## <a name="return-value"></a>Rückgabewert

Gibt zurück, die zuvor definierte zuordnungshookfunktion oder **NULL** Wenn *AllocHook* ist **NULL**.

## <a name="remarks"></a>Hinweise

**_CrtSetAllocHook** kann eine Anwendung eine eigene Zuordnungsfunktion in den speicherbelegungsprozess der C-Laufzeit-Bibliothek zu verknüpfen. Daher löst jeder Aufruf einer Debugzuordnungsfunktion für die Belegung, erneute Belegung oder Freigabe eines Speicherblocks einen Aufruf der Hookfunktion der Anwendung aus. **_CrtSetAllocHook** -Funktion bietet einer Anwendung eine einfache Methode zum Testen, wie die Anwendung Speichermangel behandelt die Möglichkeit, Reservierungsmuster und die Möglichkeit, Informationen zur Zuordnung sich später anmelden überprüfen die Analyse. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, werden Aufrufe von **_CrtSetAllocHook** während der vorverarbeitung entfernt.

Die **_CrtSetAllocHook** -Funktion installiert die neue clientdefinierte-Funktion, die im angegebenen *AllocHook* und gibt die zuvor definierte Hookfunktion zurück. Das folgende Beispiel zeigt, wie ein Prototyp einer clientdefinierten Hookfunktion für Zuordnungen entwickelt werden soll:

```C
int YourAllocHook( int allocType, void *userData, size_t size,
                   int blockType, long requestNumber,
                   const unsigned char *filename, int lineNumber);
```

Die **AllocType** Argument gibt den Typ des Zuordnungsvorgangs (**_HOOK_ALLOC**, **_HOOK_REALLOC**, und **_HOOK_FREE**), der Aufruf Hookfunktion der Zuordnung ausgelöst hat. Wenn der Typ der auslösenden Zuordnung ist **_HOOK_FREE**, *UserData* ist ein Zeiger auf die Benutzer Datenabschnitt des freizugebenden Speicherblocks. Wenn der Typ der auslösenden Zuordnung ist jedoch **_HOOK_ALLOC** oder **_HOOK_REALLOC**, *UserData* ist **NULL** da Speicher blockieren wurde noch nicht belegt wurde.

*Größe* gibt die Größe des Speicherblocks in Bytes, *BlockType* gibt den Typ des Speicherblocks, *RequestNumber* wird die Bestellnummer der objektzuordnung des Speicherblocks, und wenn verfügbar, *Filename* und **LineNumber** geben die Quelle Quelldateinamen und die Zeile an, in dem die auslösende Zuordnung initiiert wurde.

Nachdem die Hookfunktion verarbeitet wurde, muss sie einen booleschen Wert zurückgeben, der den C-Laufzeit-Hauptzuordnungsprozess anweist, wie das Verfahren fortgesetzt werden soll. Wenn die Hookfunktion den hauptzuordnungsprozess Verfahren so fortzusetzen, als wenn die Hookfunktion nie aufgerufen wurde, sollte die Hookfunktion zurückgeben **"true"**. Dadurch wird die ursprüngliche auslösende Zuordnung ausgeführt. Mit dieser Implementierung kann die Hookfunktion Zuordnungsinformationen zur späteren Analyse erfassen und speichern, ohne das aktuelle Zuordnungsverfahren oder den Zustand des Debugheaps zu beeinträchtigen.

Wenn die Hookfunktion den hauptzuordnungsprozess Verfahren so fortzusetzen, als wenn die auslösende Zuordnungsverfahren aufgerufen wurde und fehlgeschlagen ist, sollte die Hookfunktion zurückgeben **"false"**. Mit dieser Implementierung kann die Hookfunktion eine Vielzahl von Speicherbedingungen und Debugheapzuständen simulieren, um zu testen, wie die Anwendung die jeweilige Situation behandelt.

Um die Hookfunktion zu löschen, übergeben **NULL** auf **_CrtSetAllocHook**.

Weitere Informationen dazu, wie **_CrtSetAllocHook** verwendet werden können, mit anderen Speicherverwaltungsfunktionen oder zum Schreiben eigener clientdefinierte Hookfunktion-Funktionen finden Sie unter [Schreiben von Debuggen von Hookfunktionen](/visualstudio/debugger/debug-hook-function-writing).

> [!NOTE]
> **_CrtSetAllocHook** wird nicht unterstützt, unter **/CLR: pure**. Die **/CLR: pure** und **/CLR: safe** Compileroptionen in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 entfernt werden.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_CrtSetAllocHook**|\<crtdbg.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Nur Debugversionen von [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Beispiel

Ein Beispiel zum Verwenden von **_CrtSetAllocHook**, finden Sie unter [crt_dbg2](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg2).

## <a name="see-also"></a>Siehe auch

[Debugroutinen](../../c-runtime-library/debug-routines.md)<br/>
[_CrtGetAllocHook](crtgetallochook.md)<br/>

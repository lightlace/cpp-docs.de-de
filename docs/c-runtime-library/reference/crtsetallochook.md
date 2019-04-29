---
title: _CrtSetAllocHook
ms.date: 11/04/2016
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
helpviewer_keywords:
- _CrtSetAllocHook function
- CrtSetAllocHook function
ms.assetid: 405df37b-2fd1-42c8-83bc-90887f17f29d
ms.openlocfilehash: cfa466ec4bce6034c15a627ccab4ee4bb0ef8f5b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62347401"
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

**_CrtSetAllocHook** kann eine Anwendung eine eigene Zuordnungsfunktion in speicherbelegungsprozess von C-Laufzeit-Bibliothek zu verknüpfen. Daher löst jeder Aufruf einer Debugzuordnungsfunktion für die Belegung, erneute Belegung oder Freigabe eines Speicherblocks einen Aufruf der Hookfunktion der Anwendung aus. **_CrtSetAllocHook** stellt eine Anwendung eine einfache Methode zum Testen, wie die Anwendung auf Speichermangel reagiert, behandelt die Möglichkeit, Reservierungsmuster und die Möglichkeit, Reservierungsinformationen für die Anmeldung zu überprüfen die Analyse. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, werden Aufrufe von **_CrtSetAllocHook** werden während der vorverarbeitung entfernt.

Die **_CrtSetAllocHook** -Funktion installiert die neue clientdefinierte Zuordnungsfunktion in angegebenen *AllocHook* und gibt Sie die zuvor definierte Hookfunktion zurück. Das folgende Beispiel zeigt, wie ein Prototyp einer clientdefinierten Hookfunktion für Zuordnungen entwickelt werden soll:

```C
int YourAllocHook( int allocType, void *userData, size_t size,
                   int blockType, long requestNumber,
                   const unsigned char *filename, int lineNumber);
```

Die **AllocType** Argument gibt den Typ des Zuordnungsvorgangs (**_HOOK_ALLOC**, **_HOOK_REALLOC**, und **_HOOK_FREE**), den Aufruf der Reservierungshookfunktion wird ausgelöst. Wenn der Zuordnungstyp der auslösenden ist **_HOOK_FREE**, *UserData* ist ein Zeiger auf den Abschnitt UserData des freizugebenden Speicherblocks. Wenn der Zuordnungstyp der auslösenden ist jedoch **_HOOK_ALLOC** oder **_HOOK_REALLOC**, *UserData* ist **NULL** da der Speicher blockieren wurde noch nicht belegt wurde.

*Größe* gibt die Größe des Arbeitsspeichers in Bytes Speicherblocks *BlockType* gibt den Typ des Speicherblocks, *RequestNumber* wird die Bestellnummer der objektzuordnung des Speicherblocks, und, falls verfügbar, *Filename* und **LineNumber** geben die Quelle Quelldateinamen und die Zeile an, in dem die auslösende Zuordnung initiiert wurde.

Nachdem die Hookfunktion verarbeitet wurde, muss sie einen booleschen Wert zurückgeben, der den C-Laufzeit-Hauptzuordnungsprozess anweist, wie das Verfahren fortgesetzt werden soll. Wenn die Hookfunktion den hauptzuordnungsprozess Prozess fortzusetzen, als wenn die Hookfunktion hatte nie aufgerufen wurde, sollte die Hookfunktion zurückgeben möchte **"true"**. Dadurch wird die ursprüngliche auslösende Zuordnung ausgeführt. Mit dieser Implementierung kann die Hookfunktion Zuordnungsinformationen zur späteren Analyse erfassen und speichern, ohne das aktuelle Zuordnungsverfahren oder den Zustand des Debugheaps zu beeinträchtigen.

Wenn die Hookfunktion den hauptzuordnungsprozess Prozess fortzusetzen, als ob das auslösende Zuordnungsverfahren aufgerufen wurde und fehlgeschlagen ist, dann sollte die Hookfunktion zurückgeben möchte **"false"**. Mit dieser Implementierung kann die Hookfunktion eine Vielzahl von Speicherbedingungen und Debugheapzuständen simulieren, um zu testen, wie die Anwendung die jeweilige Situation behandelt.

Um die Hookfunktion zu löschen, übergeben Sie **NULL** zu **_CrtSetAllocHook**.

Weitere Informationen dazu, wie **_CrtSetAllocHook** kann verwendet werden, mit anderen Speicherverwaltungsfunktionen oder zum Schreiben eigener Clientdefinierter Hookfunktionen finden Sie unter [Debug Hook-Funktion schreiben](/visualstudio/debugger/debug-hook-function-writing).

> [!NOTE]
> **_CrtSetAllocHook** wird nicht unterstützt, unter **/CLR: pure**. Die **/CLR: pure** und **/CLR: safe** Compileroptionen in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 entfernt werden.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_CrtSetAllocHook**|\<crtdbg.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Nur Debugversionen von [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Beispiel

Ein Beispiel zur Verwendung **_CrtSetAllocHook**, finden Sie unter [crt_dbg2](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg2).

## <a name="see-also"></a>Siehe auch

[Debugroutinen](../../c-runtime-library/debug-routines.md)<br/>
[_CrtGetAllocHook](crtgetallochook.md)<br/>

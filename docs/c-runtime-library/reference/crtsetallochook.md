---
title: _CrtSetAllocHook
ms.date: 11/04/2016
api_name:
- _CrtSetAllocHook
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
- _CrtSetAllocHook
- CrtSetAllocHook
helpviewer_keywords:
- _CrtSetAllocHook function
- CrtSetAllocHook function
ms.assetid: 405df37b-2fd1-42c8-83bc-90887f17f29d
ms.openlocfilehash: 303f682b54abc5e44cb7fdd4c89012dd9913288b
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70938485"
---
# <a name="_crtsetallochook"></a>_CrtSetAllocHook

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

Gibt die zuvor definierte Zuordnungs-Hook-Funktion oder **null** zurück, wenn *allocHook* **null**ist.

## <a name="remarks"></a>Hinweise

**_CrtSetAllocHook** ermöglicht einer Anwendung, eine eigene Zuordnungs Funktion in den Speicher Belegungs Prozess der C-Laufzeit-Debugbibliothek einzuschließen. Daher löst jeder Aufruf einer Debugzuordnungsfunktion für die Belegung, erneute Belegung oder Freigabe eines Speicherblocks einen Aufruf der Hookfunktion der Anwendung aus. **_CrtSetAllocHook** bietet einer Anwendung eine einfache Methode, um zu testen, wie die Anwendung nicht genügend Arbeitsspeicher, die Fähigkeit zum Überprüfen von Zuordnungs Mustern und die Möglichkeit zum Protokollieren von Zuordnungs Informationen zur späteren Analyse verarbeiten kann. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, werden Aufrufe von **_CrtSetAllocHook** während der Vorverarbeitung entfernt.

Die **_CrtSetAllocHook** -Funktion installiert die neue Client definierte Zuordnungs Funktion, die in *allocHook* angegeben ist, und gibt die zuvor definierte Hookfunktion zurück. Das folgende Beispiel zeigt, wie ein Prototyp einer clientdefinierten Hookfunktion für Zuordnungen entwickelt werden soll:

```C
int YourAllocHook( int allocType, void *userData, size_t size,
                   int blockType, long requestNumber,
                   const unsigned char *filename, int lineNumber);
```

Das **allocType** -Argument gibt den Typ der Zuordnungs Operation ( **_HOOK_ALLOC**, **_HOOK_REALLOC**und **_HOOK_FREE**) an, die den aufrufungs Vorgang der Hookfunktion der Zuordnung ausgelöst hat. Wenn der auslösende Zuordnungstyp " **_HOOK_FREE**" ist, ist " *UserData* " ein Zeiger auf den Abschnitt "Benutzerdaten" des Speicherblocks, der freigegeben wird. Wenn der auslösende Zuordnungstyp jedoch " **_HOOK_ALLOC** " oder " **_HOOK_REALLOC**" ist, ist " *UserData* " **null** , da der Speicherblock noch nicht zugeordnet wurde.

*size* gibt die Größe des Speicherblocks in Bytes an. *blockType* gibt den Typ des Speicherblocks an, *requestNumber* ist die Bestellnummer der Objekt Zuordnung des Speicherblocks und, falls verfügbar, *Dateiname* und **LineNumber.** geben Sie den Quell Dateinamen und die Zeilennummer an, in der die auslösende Zuordnung initiiert wurde.

Nachdem die Hookfunktion verarbeitet wurde, muss sie einen booleschen Wert zurückgeben, der den C-Laufzeit-Hauptzuordnungsprozess anweist, wie das Verfahren fortgesetzt werden soll. Wenn die Hookfunktion den Haupt Zuordnungs Prozess so fortsetzen soll, als ob die Hook-Funktion nie aufgerufen wurde, sollte die Hook-Funktion **true**zurückgeben. Dadurch wird die ursprüngliche auslösende Zuordnung ausgeführt. Mit dieser Implementierung kann die Hookfunktion Zuordnungsinformationen zur späteren Analyse erfassen und speichern, ohne das aktuelle Zuordnungsverfahren oder den Zustand des Debugheaps zu beeinträchtigen.

Wenn die Hookfunktion den Haupt Zuordnungs Prozess fortsetzt, als wenn die auslösende Zuordnungs Operation aufgerufen wurde und Sie fehlgeschlagen ist, sollte die Hook-Funktion **false**zurückgeben. Mit dieser Implementierung kann die Hookfunktion eine Vielzahl von Speicherbedingungen und Debugheapzuständen simulieren, um zu testen, wie die Anwendung die jeweilige Situation behandelt.

Übergeben Sie **null** an **_CrtSetAllocHook**, um die Hook-Funktion zu löschen.

Weitere Informationen dazu, wie **_CrtSetAllocHook** mit anderen Speicherverwaltungsfunktionen verwendet werden kann oder wie eigene Client definierte Hookfunktionen geschrieben werden, finden Sie unter [Debuggen der Hookfunktion](/visualstudio/debugger/debug-hook-function-writing).

> [!NOTE]
> **_CrtSetAllocHook** wird nicht unter **/clr: pure**unterstützt. Die Compileroptionen **/clr: pure** und **/clr: Safe** sind in Visual Studio 2015 veraltet und wurden in Visual Studio 2017 entfernt.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_CrtSetAllocHook**|\<crtdbg.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Nur Debugversionen von [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Beispiel

Ein Beispiel für die Verwendung von **_CrtSetAllocHook**finden Sie unter [crt_dbg2](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg2).

## <a name="see-also"></a>Siehe auch

[Debugroutinen](../../c-runtime-library/debug-routines.md)<br/>
[_CrtGetAllocHook](crtgetallochook.md)<br/>

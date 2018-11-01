---
title: set_unexpected (CRT)
ms.date: 11/04/2016
apiname:
- set_unexpected
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
- set_unexpected
helpviewer_keywords:
- set_unexpected function
- unexpected function
- exception handling, termination
ms.assetid: ebcef032-4771-48e5-88aa-2a1ab8750aa6
ms.openlocfilehash: 6c38421e447ca7b3f263148f51f0ade5c59e2804
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50484226"
---
# <a name="setunexpected-crt"></a>set_unexpected (CRT)

Installiert Ihre eigene Beendigungsfunktion, die von **unexpected** aufgerufen werden soll.

## <a name="syntax"></a>Syntax

```cpp
unexpected_function set_unexpected( unexpected_function unexpFunction );
```

### <a name="parameters"></a>Parameter

*unexpFunction*<br/>
Zeiger auf eine Funktion, die Sie schreiben, um das Ersetzen der **unerwartete** Funktion.

## <a name="return-value"></a>Rückgabewert

Gibt ein Zeiger auf die vorherige Beendigungsfunktion registriert **_set_unexpected** , damit die vorherige Funktion später wiederhergestellt werden kann. Wenn keine vorherige Funktion festgelegt wurde, kann der Rückgabewert verwendet werden, um das Standardverhalten wiederherzustellen; Dieser Wert möglicherweise **NULL**.

## <a name="remarks"></a>Hinweise

Die **Set_unexpected** -Funktion installiert *UnexpFunction* wie die Funktion wird aufgerufen, indem **unerwartete**. **Unerwarteter** wird in der aktuellen C++-ausnahmebehandlungsimplementierung nicht verwendet. Die **Unexpected_function** Typ in der EH definiert ist. H als Zeiger auf eine benutzerdefinierte unerwartete Funktion, *UnexpFunction* zurückgibt **"void"**. Die benutzerdefinierte *UnexpFunction* Funktion sollte nicht an den Aufrufer zurückgeben.

```cpp
typedef void ( *unexpected_function )( );
```

In der Standardeinstellung **unerwartete** Aufrufe **beenden**. Sie können dieses Standardverhalten ändern, indem Sie Ihre eigene Beendigungsfunktion schreiben und Aufrufen **Set_unexpected** mit dem Namen Ihrer Funktion als Argument. **Unerwarteter** Ruft die letzte Funktion, die als Argument an **Set_unexpected**.

Im Gegensatz zu die benutzerdefinierte Funktion, die durch einen Aufruf von installiert **Set_terminate**, eine Ausnahme können aus *UnexpFunction*.

In einer Multithreadumgebung werden unerwartete Funktionen für jeden Thread separat verwaltet. Jeder neue Thread muss eine eigene unerwartete Funktion installieren. Daher ist jeder Thread für die eigene unerwartete Behandlung verantwortlich.

In der aktuellen Microsoft-Implementierung der C++-Ausnahmebehandlung **unerwartete** Aufrufe **beenden** standardmäßig und nie von der Laufzeitbibliothek für die Ausnahmebehandlung aufgerufen wird. Es gibt keinen besonderen Vorteil Aufrufen **unerwartete** statt **beenden**.

Es gibt einen einzigen **Set_unexpected** Handler für alle dynamisch verknüpften DLLs oder EXEs; auch wenn Sie aufgerufen **Set_unexpected** Ihr Handler möglicherweise durch einen anderen ersetzt, oder, die Sie ersetzen einen Handler, die festlegen, indem einer anderen DLL oder EXE-Datei.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**set_unexpected**|\<eh.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Ausnahmebehandlungsroutinen](../../c-runtime-library/exception-handling-routines.md)<br/>
[abort](abort.md)<br/>
[_get_unexpected](get-unexpected.md)<br/>
[set_terminate](set-terminate-crt.md)<br/>
[terminate](terminate-crt.md)<br/>
[unexpected](unexpected-crt.md)<br/>

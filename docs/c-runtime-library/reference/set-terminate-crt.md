---
title: set_terminate (CRT)
ms.date: 11/04/2016
apiname:
- set_terminate
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- set_terminate
helpviewer_keywords:
- set_terminate function
- terminate function
- exception handling, termination
ms.assetid: 3ff1456a-7898-44bc-9266-a328a80b6006
ms.openlocfilehash: 7be81dec7fba80a273d635cbd30b96b09928bc66
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50493911"
---
# <a name="setterminate-crt"></a>set_terminate (CRT)

Installiert Ihre eigene beendigungsroutine, die aufgerufen werden, indem **beenden**.

## <a name="syntax"></a>Syntax

```cpp
terminate_function set_terminate( terminate_function termFunction );
```

### <a name="parameters"></a>Parameter

*termFunction*<br/>
Zeiger auf eine Funktion zum Beenden, die Sie schreiben.

## <a name="return-value"></a>Rückgabewert

Gibt einen Zeiger auf die vorherige Funktion registriert **Set_terminate** , damit die vorherige Funktion später wiederhergestellt werden kann. Wenn keine vorherige Funktion festgelegt wurde, kann der Rückgabewert verwendet werden, um das Standardverhalten wiederherzustellen; Dieser Wert möglicherweise **NULL**.

## <a name="remarks"></a>Hinweise

Die **Set_terminate** -Funktion installiert *TermFunction* wie die Funktion wird aufgerufen, indem **beenden**. **Set_terminate** mit C++-Ausnahmebehandlung verwendet wird, und kann zu einem beliebigen Zeitpunkt im Programm aufgerufen werden, bevor die Ausnahme ausgelöst wird. **Beenden Sie** Aufrufe [Abbrechen](abort.md) standardmäßig. Sie können diese Standardeinstellung ändern, indem Sie Ihre eigene Beendigungsfunktion schreiben und Aufrufen **Set_terminate** mit dem Namen Ihrer Funktion als Argument. **Beenden Sie** Ruft die letzte Funktion, die als Argument an **Set_terminate**. Nach Ausführung aller Bereinigungsaufgaben gewünschten *TermFunction* sollte das Programm zu beenden. Wenn es nicht beendet wird (Wenn sie sich an den Aufrufer zurückgibt), [Abbrechen](abort.md) aufgerufen wird.

In einer Multithreadumgebung werden die Beendigungsfunktionen für jeden Thread separat verwaltet. Jeder neue Thread muss eine eigene Beendigungsfunktion installieren. Daher ist jeder Thread für die eigene Beendigungsbehandlung verantwortlich.

Die **Terminate_function** Typ in der EH definiert ist. H als Zeiger auf eine benutzerdefinierte Beendigungsfunktion *TermFunction* zurückgibt **"void"**. Die benutzerdefinierte Funktion *TermFunction* kann keine Argumente annehmen und sollte nicht an den Aufrufer zurückgeben. Wenn dies der Fall, [Abbrechen](abort.md) aufgerufen wird. Eine Ausnahme kann nicht innerhalb von *TermFunction*.

```cpp
typedef void ( *terminate_function )( );
```

> [!NOTE]
> Die **Set_terminate** Funktion kann nur außerhalb des Debuggers.

Es gibt einen einzigen **Set_terminate** Handler für alle dynamisch verknüpften DLLs oder EXEs; auch wenn Sie aufgerufen **Set_terminate** Ihr Handler möglicherweise durch einen anderen ersetzt, oder Sie ersetzen einen Handler durch einen anderen festgelegt DLL oder EXE-Datei.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**set_terminate**|\<eh.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Eine Abbildung finden Sie im Beispiel für [terminate](terminate-crt.md).

## <a name="see-also"></a>Siehe auch

[Ausnahmebehandlungsroutinen](../../c-runtime-library/exception-handling-routines.md)<br/>
[abort](abort.md)<br/>
[_get_terminate](get-terminate.md)<br/>
[set_unexpected](set-unexpected-crt.md)<br/>
[terminate](terminate-crt.md)<br/>
[unexpected](unexpected-crt.md)<br/>

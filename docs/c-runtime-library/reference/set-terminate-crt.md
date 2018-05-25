---
title: set_terminate (CRT) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- set_terminate function
- terminate function
- exception handling, termination
ms.assetid: 3ff1456a-7898-44bc-9266-a328a80b6006
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7e62dc1e4f99a1d2707c6e7b86c79e0ffc8aa027
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2018
---
# <a name="setterminate-crt"></a>set_terminate (CRT)

Installiert eine eigene Abbruchroutine aufgerufen werden, indem Sie **beenden**.

## <a name="syntax"></a>Syntax

```cpp
terminate_function set_terminate( terminate_function termFunction );
```

### <a name="parameters"></a>Parameter

*termFunction*<br/>
Zeiger auf eine Funktion zum Beenden, die Sie schreiben.

## <a name="return-value"></a>Rückgabewert

Gibt einen Zeiger auf die vorherige Funktion registriert, indem Sie **Set_terminate** , damit die vorherige Funktion später wiederhergestellt werden kann. Wenn keine previous-Funktion festgelegt wurde, kann der Rückgabewert verwendet werden, um das Standardverhalten wiederherstellen; Dieser Wert möglicherweise **NULL**.

## <a name="remarks"></a>Hinweise

Die **Set_terminate** -Funktion installiert *TermFunction* wie die Funktion wird aufgerufen, indem **beenden**. **Set_terminate** mit C++-Ausnahmebehandlung verwendet wird und an einem beliebigen Punkt im Programm aufgerufen werden kann, bevor die Ausnahme ausgelöst wird. **Beenden** Aufrufe [abort](abort.md) standardmäßig. Sie können diese Standardeinstellung ändern, indem Sie eine eigene Beendigungsfunktion schreiben und Aufrufen **Set_terminate** mit dem Namen Ihrer Funktion als Argument. **Beenden** Ruft die letzte Funktion als Argument an **Set_terminate**. Nach dem Ausführen einer Bereinigungsaufgaben gewünscht *TermFunction* sollte das Programm zu beenden. Wenn er nicht beendet wird (wenn es an den Aufrufer zurückgibt), [abort](abort.md) aufgerufen wird.

In einer Multithreadumgebung werden die Beendigungsfunktionen für jeden Thread separat verwaltet. Jeder neue Thread muss eine eigene Beendigungsfunktion installieren. Daher ist jeder Thread für die eigene Beendigungsbehandlung verantwortlich.

Die **Terminate_function** Typ in der EH definiert ist. H als Zeiger auf eine benutzerdefinierte Beendigungsfunktion *TermFunction* zurückgibt **"void"**. Die benutzerdefinierte Funktion *TermFunction* können akzeptieren keine Argumente und sollte nicht an den Aufrufer zurückgeben. Wenn dies der Fall, [abort](abort.md) aufgerufen wird. Eine Ausnahme kann nicht innerhalb von *TermFunction*.

```cpp
typedef void ( *terminate_function )( );
```

> [!NOTE]
> Die **Set_terminate** Funktion funktioniert nur außerhalb des Debuggers.

Es gibt einen einzigen **Set_terminate** Handler für alle dynamisch verknüpften DLLs oder EXE-Dateien, selbst wenn Sie aufrufen **Set_terminate** Ihr Handler möglicherweise durch eine andere ersetzt werden, oder Sie ersetzen einen Handler, die durch eine andere festlegen DLL oder EXE-Datei.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
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

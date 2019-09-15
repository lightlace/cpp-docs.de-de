---
title: set_terminate (CRT)
ms.date: 11/04/2016
api_name:
- set_terminate
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
- api-ms-win-crt-runtime-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- set_terminate
helpviewer_keywords:
- set_terminate function
- terminate function
- exception handling, termination
ms.assetid: 3ff1456a-7898-44bc-9266-a328a80b6006
ms.openlocfilehash: 860789a3f2fda5ef13cadffa2a00dba4fbd2090a
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70948356"
---
# <a name="set_terminate-crt"></a>set_terminate (CRT)

Installiert ihre eigene Beendigungs Routine, um durch **Beenden**aufgerufen zu werden.

## <a name="syntax"></a>Syntax

```cpp
terminate_function set_terminate( terminate_function termFunction );
```

### <a name="parameters"></a>Parameter

*termFunction*<br/>
Zeiger auf eine Funktion zum Beenden, die Sie schreiben.

## <a name="return-value"></a>Rückgabewert

Gibt einen Zeiger auf die vorherige Funktion zurück, die von **Set_terminate** registriert wurde, sodass die vorherige Funktion später wieder hergestellt werden kann. Wenn keine vorherige Funktion festgelegt wurde, kann der Rückgabewert verwendet werden, um das Standardverhalten wiederherzustellen. Dieser Wert kann **null**sein.

## <a name="remarks"></a>Hinweise

Die **Set_terminate** -Funktion installiert *termfunction* als die Funktion, die durch **Beenden**aufgerufen wird. **Set_terminate** wird mit C++ Ausnahmebehandlung verwendet und kann an einem beliebigen Punkt im Programm aufgerufen werden, bevor die Ausnahme ausgelöst wird. **Beendigungs Aufrufe werden** standardmäßig [abgebrochen](abort.md) . Sie können diesen Standardwert ändern, indem Sie eine eigene Beendigungs Funktion schreiben und **Set_terminate** mit dem Namen ihrer Funktion als Argument aufrufen. **Beenden** Ruft die letzte Funktion auf, die als Argument für **Set_terminate**angegeben wurde. Nach dem Ausführen gewünschter Bereinigungs Tasks sollte *termfunction* das Programm beenden. Wenn Sie nicht beendet wird (wenn Sie zu Ihrem Aufrufer zurückkehrt), wird [Abbruch](abort.md) aufgerufen.

In einer Multithreadumgebung werden die Beendigungsfunktionen für jeden Thread separat verwaltet. Jeder neue Thread muss eine eigene Beendigungsfunktion installieren. Daher ist jeder Thread für die eigene Beendigungsbehandlung verantwortlich.

Der **terminate_function** -Typ ist in eh definiert. H als Zeiger auf eine benutzerdefinierte Beendigungs Funktion, *termfunction* , die **void**zurückgibt. Die benutzerdefinierte Funktion *termfunction* kann keine Argumente annehmen und sollte nicht an ihren Aufrufer zurückgegeben werden. Wenn dies der Fall ist, wird [Abbruch](abort.md) aufgerufen. Eine Ausnahme kann nicht innerhalb von *termfunction*ausgelöst werden.

```cpp
typedef void ( *terminate_function )( );
```

> [!NOTE]
> Die **Set_terminate** -Funktion funktioniert nur außerhalb des Debuggers.

Es gibt einen einzelnen **Set_terminate** -Handler für alle dynamisch verknüpften DLLs oder EXEs. auch wenn Sie **Set_terminate** aufzurufen, wird der Handler möglicherweise durch einen anderen ersetzt, oder Sie ersetzen einen Handler, der von einer anderen DLL oder exe festgelegt wurde.

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

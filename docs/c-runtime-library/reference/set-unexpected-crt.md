---
title: set_unexpected (CRT)
ms.date: 11/04/2016
api_name:
- set_unexpected
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
- set_unexpected
helpviewer_keywords:
- set_unexpected function
- unexpected function
- exception handling, termination
ms.assetid: ebcef032-4771-48e5-88aa-2a1ab8750aa6
ms.openlocfilehash: 77c8f0ae8c64423a656a2ebbe1fe3ef6dbe1b794
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70948301"
---
# <a name="set_unexpected-crt"></a>set_unexpected (CRT)

Installiert Ihre eigene Beendigungsfunktion, die von **unexpected** aufgerufen werden soll.

## <a name="syntax"></a>Syntax

```cpp
unexpected_function set_unexpected( unexpected_function unexpFunction );
```

### <a name="parameters"></a>Parameter

*unexpFunction*<br/>
Zeiger auf eine Funktion, die Sie schreiben, um die **unerwartete** Funktion zu ersetzen.

## <a name="return-value"></a>Rückgabewert

Gibt einen Zeiger auf die vorherige Beendigungs Funktion zurück, die von **_set_unexpected** registriert wurde, sodass die vorherige Funktion später wieder hergestellt werden kann. Wenn keine vorherige Funktion festgelegt wurde, kann der Rückgabewert verwendet werden, um das Standardverhalten wiederherzustellen. Dieser Wert kann **null**sein.

## <a name="remarks"></a>Hinweise

Die **Set_unexpected** -Funktion installiert *unexpFunction* als die Funktion, die von **unerwartetem**aufgerufen wurde. **unerwartetes** wird in der aktuellen C++ Ausnahme Behandlungs Implementierung nicht verwendet. Der **unexpected_function** -Typ ist in eh definiert. H als Zeiger auf eine benutzerdefinierte unerwartete Funktion, *unexpFunction* , die **void**zurückgibt. Die benutzerdefinierte *unexpFunction* -Funktion sollte nicht an ihren Aufrufer zurückgegeben werden.

```cpp
typedef void ( *unexpected_function )( );
```

Standardmäßig werden **unerwartete** Aufrufe **beendet**. Sie können dieses Standardverhalten ändern, indem Sie eine eigene Beendigungs Funktion schreiben und **Set_unexpected** mit dem Namen ihrer Funktion als Argument aufrufen. **unerwartete** Aufrufe der letzten Funktion, die als Argument für **Set_unexpected**angegeben wurde.

Anders als die benutzerdefinierte Beendigungs Funktion, die durch einen **Set_terminate**-Aufrufe installiert wird, kann eine Ausnahme von innerhalb von *unexpFunction*ausgelöst werden.

In einer Multithreadumgebung werden unerwartete Funktionen für jeden Thread separat verwaltet. Jeder neue Thread muss eine eigene unerwartete Funktion installieren. Daher ist jeder Thread für die eigene unerwartete Behandlung verantwortlich.

In der aktuellen Microsoft-Implementierung C++ der Ausnahmebehandlung werden **unerwartete** Aufrufe standardmäßig **beendet** und nie von der Ausnahme Behandlungs Lauf Zeit Bibliothek aufgerufen. Es gibt keinen besonderen Vorteil beim Aufrufen eines **unerwarteten** anstelle von " **Beenden**".

Es gibt einen einzelnen **Set_unexpected** -Handler für alle dynamisch verknüpften DLLs oder EXEs. auch wenn Sie **Set_unexpected** aufzurufen, wird der Handler möglicherweise durch einen anderen ersetzt, oder Sie ersetzen einen Handler, der von einer anderen DLL oder exe festgelegt wurde.

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

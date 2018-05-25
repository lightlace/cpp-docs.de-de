---
title: set_unexpected (CRT) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- set_unexpected function
- unexpected function
- exception handling, termination
ms.assetid: ebcef032-4771-48e5-88aa-2a1ab8750aa6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7af5cce0b17747beb8c136f75489025d741f864a
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2018
---
# <a name="setunexpected-crt"></a>set_unexpected (CRT)

Installiert Ihre eigene Beendigungsfunktion, die von **unexpected** aufgerufen werden soll.

## <a name="syntax"></a>Syntax

```cpp
unexpected_function set_unexpected( unexpected_function unexpFunction );
```

### <a name="parameters"></a>Parameter

*unexpFunction*<br/>
Zeiger auf eine Funktion, die Sie schreiben, um das Ersetzen der **unerwarteter** Funktion.

## <a name="return-value"></a>Rückgabewert

Gibt ein Zeiger auf den vorherigen Beendigungsfunktion, indem Sie registriert **_set_unexpected** , damit die vorherige Funktion später wiederhergestellt werden kann. Wenn keine previous-Funktion festgelegt wurde, kann der Rückgabewert verwendet werden, um das Standardverhalten wiederherstellen; Dieser Wert möglicherweise **NULL**.

## <a name="remarks"></a>Hinweise

Die **Set_unexpected** -Funktion installiert *UnexpFunction* wie die Funktion wird aufgerufen, indem **unerwarteter**. **Unerwarteter** nicht in die aktuelle Implementierung der C++-Ausnahmebehandlung verwendet wird. Die **Unexpected_function** Typ in der EH definiert ist. H als Zeiger auf eine benutzerdefinierte Unerwarteter Funktionstyp *UnexpFunction* zurückgibt **"void"**. Die benutzerdefinierte *UnexpFunction* Funktion sollten nicht an den Aufrufer zurück.

```cpp
typedef void ( *unexpected_function )( );
```

Standardmäßig **unerwarteter** Aufrufe **beenden**. Sie können dieses Standardverhalten ändern, indem Sie eine eigene Beendigungsfunktion schreiben und Aufrufen **Set_unexpected** mit dem Namen Ihrer Funktion als Argument. **Unerwarteter** Ruft die letzte Funktion als Argument an **Set_unexpected**.

Im Gegensatz zu den benutzerdefinierten Beendigungsfunktion installiert durch einen Aufruf von **Set_terminate**, eine Ausnahme ausgelöst werden kann, innerhalb von *UnexpFunction*.

In einer Multithreadumgebung werden unerwartete Funktionen für jeden Thread separat verwaltet. Jeder neue Thread muss eine eigene unerwartete Funktion installieren. Daher ist jeder Thread für die eigene unerwartete Behandlung verantwortlich.

In der aktuellen Microsoft-Implementierung der C++-Ausnahmebehandlung **unerwarteter** Aufrufe **beenden** standardmäßig und nie von der Laufzeitbibliothek Ausnahmebehandlung aufgerufen wird. Es gibt keine besonderen Vorteil Aufrufen **unerwarteter** statt **beenden**.

Es gibt einen einzigen **Set_unexpected** Handler für alle dynamisch verknüpften DLLs oder EXE-Dateien, selbst wenn Sie rufen **Set_unexpected** Ihr Handler möglicherweise durch eine andere ersetzt wird, oder, die Sie ersetzen einen Handler, die festlegen, indem einer anderen DLL oder EXE-Datei.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
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

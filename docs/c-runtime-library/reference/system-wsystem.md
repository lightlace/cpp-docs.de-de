---
title: system, _wsystem | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- system
- _wsystem
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
- _tsystem
- _wsystem
dev_langs:
- C++
helpviewer_keywords:
- _wsystem function
- wsystem function
- tsystem function
- _tsystem function
- system function
- commands, executing
- command interpreter
ms.assetid: 7d3df2b6-f742-49ce-bf52-012b0aee3df5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ca44648ed378d4484b8e4c32a38a6780b3eddd53
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32414701"
---
# <a name="system-wsystem"></a>system, _wsystem

Führt einen Befehl aus.

> [!IMPORTANT]
> Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
int system(
   const char *command
);
int _wsystem(
   const wchar_t *command
);
```

### <a name="parameters"></a>Parameter

*command*<br/>
Der Befehl, der ausgeführt werden soll.

## <a name="return-value"></a>Rückgabewert

Wenn *Befehl* ist **NULL** und der Befehlsinterpreter gefunden wird, gibt einen Wert ungleich NULL zurück. Wenn der Befehlsinterpreter gefunden wird, gibt 0 zurück und legt **Errno** auf **ENOENT**. Wenn *Befehl* nicht **NULL**, **System** gibt den Wert, der vom Befehlsinterpreter zurückgegeben wird. Gibt den Wert 0 nur zurück, wenn der Befehlsinterpreter den Wert 0 zurückgibt. Ein Rückgabewert von – 1 zeigt einen Fehler, und **Errno** auf einen der folgenden Werte festgelegt:

|||
|-|-|
**E2BIG**|Die Argumentliste (systemabhängig) ist zu groß.
**ENOENT**|Der Befehlsinterpreter kann nicht gefunden werden.
**ENOEXEC**|Die Befehlsinterpreterdatei kann nicht ausgeführt werden, da das Format ungültig ist.
**ENOMEM**|Es ist nicht genügend Arbeitsspeicher verfügbar, um den Befehl auszuführen; der verfügbare Arbeitsspeicher ist beschädigt; oder es ist ein ungültiger Block vorhanden, was darauf hinweist, dass der aufrufende Prozess nicht ordnungsgemäß zugeordnet wurde.

Weitere Informationen zu diesen Rückgabecodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die **System** -Funktion übergibt *Befehl* an den Befehlsinterpreter, der die Zeichenfolge als ein Betriebssystembefehl ausgeführt. **System** verwendet die **COMSPEC** und **Pfad** Umgebungsvariablen zum Suchen des Befehlsinterpreters Datei CMD.exe. Wenn *Befehl* ist **NULL**, überprüft die Funktion lediglich, ob der Befehlsinterpreter vorhanden ist.

Sie müssen explizit leeren, mithilfe von [Fflush](fflush.md) oder [_flushall](flushall.md), oder schließen Sie vor dem Aufruf ein Streams **System**.

**_wsystem** ist eine Breitzeichen-Version von **System**; das *Befehl* Argument **_wsystem** ist eine Breitzeichen-Zeichenfolge. Anderenfalls verhalten sich diese Funktionen identisch.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tsystem**|**system**|**system**|**_wsystem**|

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**system**|\<process.h> oder\<stdlib.h>|
|**_wsystem**|\<process.h> oder \<stdlib.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Dieses Beispiel verwendet **System** zum Eingeben einer Textdatei.

```C
// crt_system.c

#include <process.h>

int main( void )
{
   system( "type crt_system.txt" );
}
```

### <a name="input-crtsystemtxt"></a>Input: crt_system.txt

```Input
Line one.
Line two.
```

### <a name="output"></a>Ausgabe

```Output
Line one.
Line two.
```

## <a name="see-also"></a>Siehe auch

[Prozess- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)<br/>
[_exec- und _wexec-Funktionen](../../c-runtime-library/exec-wexec-functions.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[_flushall](flushall.md)<br/>
[_spawn-, _wspawn-Funktionen](../../c-runtime-library/spawn-wspawn-functions.md)<br/>

---
title: system, _wsystem
ms.date: 11/04/2016
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
helpviewer_keywords:
- _wsystem function
- wsystem function
- tsystem function
- _tsystem function
- system function
- commands, executing
- command interpreter
ms.assetid: 7d3df2b6-f742-49ce-bf52-012b0aee3df5
ms.openlocfilehash: 46c4949fcc8cfbe4a3477e66b57d8fc6fc97ed73
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62259091"
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

Wenn *Befehl* ist **NULL** und der Befehlsinterpreter gefunden wird, gibt einen Wert ungleich NULL zurück. Wenn nicht der Befehlsinterpreter gefunden wird, gibt 0 zurück und legt **Errno** zu **ENOENT**. Wenn *Befehl* nicht **NULL**, **System** gibt den Wert zurück, die von den Befehlsinterpreter zurückgegeben wird. Gibt den Wert 0 nur zurück, wenn der Befehlsinterpreter den Wert 0 zurückgibt. Ein Rückgabewert von – 1 gibt einen Fehler, und **Errno** auf einen der folgenden Werte festgelegt:

|||
|-|-|
| **E2BIG** | Die Argumentliste (systemabhängig) ist zu groß. |
| **ENOENT** | Der Befehlsinterpreter kann nicht gefunden werden. |
| **ENOEXEC** | Die Befehlsinterpreterdatei kann nicht ausgeführt werden, da das Format ungültig ist. |
| **ENOMEM** | Es ist nicht genügend Arbeitsspeicher verfügbar, um den Befehl auszuführen; der verfügbare Arbeitsspeicher ist beschädigt; oder es ist ein ungültiger Block vorhanden, was darauf hinweist, dass der aufrufende Prozess nicht ordnungsgemäß zugeordnet wurde. |

Weitere Informationen zu diesen Rückgabecodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die **System** -Funktion übergibt *Befehl* an den Befehlsinterpreter, der die Zeichenfolge als Betriebssystem-Befehl ausgeführt wird. **System** verwendet die **COMSPEC** und **Pfad** Umgebungsvariablen zum Suchen des Befehlsinterpreters befehlsinterpreterdatei CMD.exe zu suchen. Wenn *Befehl* ist **NULL**, überprüft die Funktion lediglich, ob der Befehlsinterpreter vorhanden ist.

Sie müssen explizit leeren, mithilfe von [Fflush](fflush.md) oder [_flushall](flushall.md), oder schließen ein Streams, vor dem Aufruf **System**.

**_wsystem** ist eine Breitzeichen-Version von **System**; die *Befehl* Argument **_wsystem** ist eine Breitzeichen-Zeichenfolge. Anderenfalls verhalten sich diese Funktionen identisch.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tsystem**|**system**|**system**|**_wsystem**|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
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

### <a name="output"></a>Output

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

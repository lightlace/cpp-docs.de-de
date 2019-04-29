---
title: _spawnlp, _wspawnlp
ms.date: 11/04/2016
apiname:
- _wspawnlp
- _spawnlp
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
- api-ms-win-crt-process-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _wspawnlp
- wspawnlp
- _spawnlp
helpviewer_keywords:
- wspawnlp function
- _spawnlp function
- processes, creating
- processes, executing new
- _wspawnlp function
- process creation
- spawnlp function
ms.assetid: 74fc6e7a-4f24-4103-9387-7177875875e6
ms.openlocfilehash: 44137aefcec8f6658a90117288a47696f4d31903
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62355236"
---
# <a name="spawnlp-wspawnlp"></a>_spawnlp, _wspawnlp

Erstellt einen neuen Prozess und führt ihn aus.

> [!IMPORTANT]
> Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
intptr_t _spawnlp(
   int mode,
   const char *cmdname,
   const char *arg0,
   const char *arg1,
   ... const char *argn,
   NULL
);
intptr_t _wspawnlp(
   int mode,
   const wchar_t *cmdname,
   const wchar_t *arg0,
   const wchar_t *arg1,
   ... const wchar_t *argn,
   NULL
);
```

### <a name="parameters"></a>Parameter

*mode*<br/>
Ausführungsmodus für den aufrufenden Prozess.

*cmdname*<br/>
Pfad der auszuführenden Datei.

*arg0*, *arg1*, ... *argn*<br/>
Liste von Zeigern zu Argumenten. Die *arg0* -Argument ist gewöhnlich ein Zeiger auf *Cmdname*. Die Argumente *arg1* über *Argn* sind Zeiger auf die Zeichenfolgen, die die neue Argumentliste bilden. Folgende *Argn*, ist eine **NULL** Zeiger auf das Ende der Argumentliste zu markieren.

## <a name="return-value"></a>Rückgabewert

Der Rückgabewert eines synchronen **_spawnlp** oder **_wspawnlp** (**_P_WAIT** für *Modus*) ist der Beendigungsstatus des neuen Prozesses . Der Rückgabewert eines asynchronen **_spawnlp** oder **_wspawnlp** (**_P_NOWAIT** oder **_P_NOWAITO** für  *Modus*) ist das Prozesshandle. Der Beendigungsstatus ist 0, wenn der Prozess ordnungsgemäß beendet wurde. Sie können den Beendigungsstatus auf einen Wert ungleich Null festlegen, wenn der gestartete Prozess speziell aufruft der **beenden** Routine mit einem Argument ungleich. Wenn der neue Prozess nicht explizit einen positiven Beendigungsstatus eingestellt hat, weist ein positiver Beendigungsstatus auf eine abnormale Beendigung mit einem Abbruch oder einer Unterbrechung hin. Der Rückgabewert-1 gibt an, ein Fehler (der neue Prozess wird nicht gestartet). In diesem Fall **Errno** auf einen der folgenden Werte festgelegt ist.

|||
|-|-|
| **E2BIG** | Argumentliste umfasst mehr als 1024 Byte. |
| **EINVAL** | *Modus* Argument ist ungültig. |
| **ENOENT** | Datei oder Pfad nicht gefunden. |
| **ENOEXEC** | Die angegebene Datei ist nicht ausführbar oder hat ein ungültiges Format für eine ausführbare Datei. |
| **ENOMEM** | Es ist nicht genügend Arbeitsspeicher verfügbar, um den neuen Prozess auszuführen. |

Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Jede dieser Funktionen erstellt, und führt einen neuen Prozess, übergibt jedes Befehlszeilenargument als separaten Parameter und Verwenden der **Pfad** -Umgebungsvariable zum Ermitteln der auszuführenden Datei.

Diese Funktionen überprüfen ihre Parameter. Wenn entweder *Cmdname* oder *arg0* ist eine leere Zeichenfolge oder ein null-Zeiger wie in beschrieben, generieren diese Funktionen eine Ausnahme für ungültige Parameter, wegen [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, legen diese Funktionen **Errno** zu **EINVAL**, und geben-1 zurück. Es wird kein neuer Prozess erzeugt.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_spawnlp**|\<process.h>|
|**_wspawnlp**|\<stdio.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Siehe das Beispiel in [_spawn, _wspawn Functions](../../c-runtime-library/spawn-wspawn-functions.md).

## <a name="see-also"></a>Siehe auch

[Prozess- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)<br/>
[_spawn-, _wspawn-Funktionen](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[abort](abort.md)<br/>
[atexit](atexit.md)<br/>
[_exec- und _wexec-Funktionen](../../c-runtime-library/exec-wexec-functions.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[_flushall](flushall.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_onexit, _onexit_m](onexit-onexit-m.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>

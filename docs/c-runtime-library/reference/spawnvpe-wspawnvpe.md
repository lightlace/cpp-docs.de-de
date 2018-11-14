---
title: _spawnvpe, _wspawnvpe
ms.date: 11/04/2016
apiname:
- _spawnvpe
- _wspawnvpe
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
- _spawnvpe
- wspawnvpe
- spawnvpe
- _wspawnvpe
helpviewer_keywords:
- _wspawnvpe function
- processes, creating
- _spawnvpe function
- processes, executing new
- wspawnvpe function
- process creation
- spawnvpe function
ms.assetid: 3db6394e-a955-4837-97a1-fab1db1e6092
ms.openlocfilehash: a98cc3c441261a92876b94e1231e66bb71e9d3d9
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/09/2018
ms.locfileid: "51326601"
---
# <a name="spawnvpe-wspawnvpe"></a>_spawnvpe, _wspawnvpe

Erstellt einen neuen Prozess und führt ihn aus.

> [!IMPORTANT]
> Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
intptr_t _spawnvpe(
   int mode,
   const char *cmdname,
   const char *const *argv,
   const char *const *envp
);
intptr_t _wspawnvpe(
   int mode,
   const wchar_t *cmdname,
   const wchar_t *const *argv,
   const wchar_t *const *envp
);
```

### <a name="parameters"></a>Parameter

*mode*<br/>
Ausführungsmodus für einen aufrufenden Prozess

*CmdName*<br/>
Pfad der auszuführenden Datei

*argv*<br/>
Array von Zeigern zu Argumenten. Das Argument *Argv*[0] ist normalerweise ein Zeiger auf einen Pfad im Echtzeitmodus oder auf den Programmnamen im geschützten Modus und *Argv*[1] bis *Argv*[**n**] sind Zeiger auf die Zeichenfolgen, die die neue Argumentliste bilden. Das Argument *Argv*[**n** + 1] muss eine **NULL** Zeiger auf das Ende der Argumentliste zu markieren.

*envp*<br/>
Array von Zeigern zu Umgebungseinstellungen

## <a name="return-value"></a>Rückgabewert

Der Rückgabewert eines synchronen **_spawnvpe** oder **_wspawnvpe** (**_P_WAIT** für *Modus*) ist der Beendigungsstatus des neuen der Prozess. Der Rückgabewert eines asynchronen **_spawnvpe** oder **_wspawnvpe** (**_P_NOWAIT** oder **_P_NOWAITO** für  *Modus*) ist das Prozesshandle. Der Beendigungsstatus ist 0, wenn der Prozess ordnungsgemäß beendet wurde. Sie können den Beendigungsstatus auf einen Wert ungleich Null festlegen, wenn der gestartete Prozess speziell aufruft der **beenden** Routine mit einem Argument ungleich. Wenn der neue Prozess nicht explizit einen positiven Beendigungsstatus eingestellt hat, weist ein positiver Beendigungsstatus auf eine abnormale Beendigung mit einem Abbruch oder einer Unterbrechung hin. Der Rückgabewert-1 gibt an, ein Fehler (der neue Prozess wird nicht gestartet). In diesem Fall **Errno** auf einen der folgenden Werte festgelegt:

|||
|-|-|
| **E2BIG** | Argumentliste umfasst mehr als 1024 Byte. |
| **EINVAL** | *Modus* Argument ist ungültig. |
| **ENOENT** | Datei oder Pfad nicht gefunden. |
| **ENOEXEC** | Die angegebene Datei ist nicht ausführbar oder hat ein ungültiges Format für eine ausführbare Datei. |
| **ENOMEM** | Es ist nicht genügend Arbeitsspeicher verfügbar, um den neuen Prozess auszuführen. |

Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Jede dieser Funktionen erstellt einen neuen Prozess, führt diesen aus und übergibt ein Array von Zeigern auf Befehlszeilenargumente und ein Array von Zeigern auf die Umgebungseinstellungen. Diese Funktionen verwenden die **Pfad** -Umgebungsvariable zum Ermitteln der auszuführenden Datei.

Diese Funktionen überprüfen ihre Parameter. Wenn entweder *Cmdname* oder *Argv* ein null-Zeiger ist oder wenn *Argv* null-Zeiger zeigt oder *Argv*[0] ist eine leere Zeichenfolge, die ungültig parameterhandler wird aufgerufen, siehe [Parametervalidierung](../../c-runtime-library/parameter-validation.md) . Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, legen diese Funktionen **Errno** zu **EINVAL**, und geben-1 zurück. Es wird kein neuer Prozess erzeugt.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_spawnvpe**|\<stdio.h> oder \<process.h>|
|**_wspawnvpe**|\<stdio.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Siehe das Beispiel in [_spawn, _wspawn Functions](../../c-runtime-library/spawn-wspawn-functions.md).

## <a name="see-also"></a>Siehe auch

[abort](abort.md)<br/>
[atexit](atexit.md)<br/>
[_exec- und _wexec-Funktionen](../../c-runtime-library/exec-wexec-functions.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[_flushall](flushall.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_onexit, _onexit_m](onexit-onexit-m.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>

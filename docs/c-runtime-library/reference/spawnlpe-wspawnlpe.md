---
title: _spawnlpe, _wspawnlpe | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _spawnlpe
- _wspawnlpe
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
- spawnlpe
- _wspawnlpe
- _spawnlpe
- wspawnlpe
dev_langs:
- C++
helpviewer_keywords:
- _wspawnlpe function
- wspawnlpe function
- processes, creating
- spawnlpe function
- _spawnlpe function
- processes, executing new
- process creation
ms.assetid: e171ebfa-70e7-4c44-8331-2a291fc17bd6
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f72dc4f3611b74ac0e7b94743a7f1910a74cef29
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="spawnlpe-wspawnlpe"></a>_spawnlpe, _wspawnlpe

Erstellt einen neuen Prozess und führt ihn aus.

> [!IMPORTANT]
> Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
intptr_t _spawnlpe(
   int mode,
   const char *cmdname,
   const char *arg0,
   const char *arg1,
   ... const char *argn,
   NULL,
   const char *const *envp
);
intptr_t _wspawnlpe(
   int mode,
   const wchar_t *cmdname,
   const wchar_t *arg0,
   const wchar_t *arg1,
   ... const wchar_t *argn,
   NULL,
   const wchar_t *const *envp
);
```

### <a name="parameters"></a>Parameter

*mode*<br/>
Ausführungsmodus für den aufrufenden Prozess.

*CmdName*<br/>
Pfad der auszuführenden Datei.

*arg0*, *arg1*,... *Argn*<br/>
Liste von Zeigern zu Argumenten. Die *arg0* -Argument ist normalerweise ein Zeiger auf *Cmdname*. Die Argumente *arg1* über *Argn* sind Zeiger auf die Zeichenfolgen, die die neue Argumentliste bilden. Folgende *Argn*, es muss ein **NULL** Zeiger auf das Ende der Argumentliste zu markieren.

*envp*<br/>
Array von Zeigern zu Umgebungseinstellungen.

## <a name="return-value"></a>Rückgabewert

Der Rückgabewert eines synchronen **_spawnlpe** oder **_wspawnlpe** (**_P_WAIT** angegeben für *Modus*) ist der Beendigungsstatus des neuen Prozess. Der Rückgabewert eines asynchronen **_spawnlpe** oder **_wspawnlpe** (**_P_NOWAIT** oder **_P_NOWAITO** angegeben für  *Modus*) ist das Prozesshandle. Der Beendigungsstatus ist 0, wenn der Prozess ordnungsgemäß beendet wurde. Sie können den Beendigungsstatus auf einen Wert ungleich Null festlegen, wenn der gestartete Prozess speziell einem Argument ungleich verwendet wird, rufen Sie die **beenden** Routine. Wenn der neue Prozess nicht explizit einen positiven Beendigungsstatus eingestellt hat, weist ein positiver Beendigungsstatus auf eine abnormale Beendigung aufgrund eines Abbruchs oder einer Unterbrechung hin. Ein Rückgabewert "-1" gibt einen Fehler (der neue Prozess wird nicht gestartet) an. In diesem Fall **Errno** auf einen der folgenden Werte festgelegt.

|||
|-|-|
**E2BIG**|Argumentliste umfasst mehr als 1024 Byte.
**EINVAL**|*Modus* Argument ist ungültig.
**ENOENT**|Datei oder Pfad nicht gefunden.
**ENOEXEC**|Die angegebene Datei ist nicht ausführbar oder hat ein ungültiges Format für eine ausführbare Datei.
**ENOMEM**|Es ist nicht genügend Arbeitsspeicher verfügbar, um den neuen Prozess auszuführen.

Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Jede dieser Funktionen erstellt einen neuen Prozess und führt diesen aus, übergibt jedes Befehlszeilenargument als separaten Parameter und übergibt außerdem ein Array von Zeigern auf die Umgebungseinstellungen. Verwenden Sie diese Funktionen die **Pfad** -Umgebungsvariable zum Ermitteln der auszuführenden Datei.

Diese Funktionen überprüfen ihre Parameter. Wenn entweder *Cmdname* oder *arg0* ist eine leere Zeichenfolge oder ein null-Zeiger, der Handler für ungültige Parameter aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, legen diese Funktionen **Errno** auf **EINVAL**, und geben-1 zurück. Es wird kein neuer Prozess erzeugt.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_spawnlpe**|\<process.h>|
|**_wspawnlpe**|\<stdio.h> oder \<wchar.h>|

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

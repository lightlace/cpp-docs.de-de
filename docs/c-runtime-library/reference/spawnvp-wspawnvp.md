---
title: _spawnvp, _wspawnvp | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _wspawnvp
- _spawnvp
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
- _wspawnvp
- _spawnvp
- wspawnvp
dev_langs:
- C++
helpviewer_keywords:
- wspawnvp function
- processes, creating
- _wspawnvp function
- processes, executing new
- spawnvp function
- process creation
- _spawnvp function
ms.assetid: 8d8774ec-6ad4-4680-a5aa-440cde1e0249
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0234591166f2f041de12d91f55ec07f96698f172
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="spawnvp-wspawnvp"></a>_spawnvp, _wspawnvp

Erstellt einen Prozess und führt ihn aus.

> [!IMPORTANT]
> Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
intptr_t _spawnvp(
   int mode,
   const char *cmdname,
   const char *const *argv
);
intptr_t _wspawnvp(
   int mode,
   const wchar_t *cmdname,
   const wchar_t *const *argv
);
```

### <a name="parameters"></a>Parameter

*mode*<br/>
Ausführungsmodus für den aufrufenden Prozess

*CmdName*<br/>
Pfad der auszuführenden Datei.

*argv*<br/>
Array von Zeigern zu Argumenten. Das Argument *Argv*[0] ist gewöhnlich ein Zeiger auf einen Pfad im Echtzeitmodus oder auf den Programmnamen im geschützten Modus und *Argv*[1] bis *Argv*[**n**] sind Zeiger auf die Zeichenfolgen, die die neue Argumentliste bilden. Das Argument *Argv*[**n** + 1] muss ein **NULL** Zeiger auf das Ende der Argumentliste zu markieren.

## <a name="return-value"></a>Rückgabewert

Der Rückgabewert eines synchronen **_spawnvp** oder **_wspawnvp** (**_P_WAIT** angegeben für *Modus*) ist der Beendigungsstatus des neuen Prozesses . Der Rückgabewert eines asynchronen **_spawnvp** oder **_wspawnvp** (**_P_NOWAIT** oder **_P_NOWAITO** angegeben für  *Modus*) ist das Prozesshandle. Der Beendigungsstatus ist 0, wenn der Prozess ordnungsgemäß beendet wurde. Sie können den Beendigungsstatus auf einen Wert ungleich Null festlegen, wenn der gestartete Prozess speziell einem Argument ungleich verwendet wird, rufen Sie die **beenden** Routine. Wenn der neue Prozess nicht explizit einen positiven Beendigungsstatus eingestellt hat, weist ein positiver Beendigungsstatus auf eine abnormale Beendigung mit einem Abbruch oder einer Unterbrechung hin. Ein Rückgabewert "-1" gibt einen Fehler (der neue Prozess wird nicht gestartet) an. In diesem Fall **Errno** auf einen der folgenden Werte festgelegt:

|||
|-|-|
**E2BIG**|Argumentliste umfasst mehr als 1024 Byte.
**EINVAL**|*Modus* Argument ist ungültig.
**ENOENT**|Datei oder Pfad nicht gefunden.
**ENOEXEC**|Die angegebene Datei ist nicht ausführbar oder hat ein ungültiges Format für eine ausführbare Datei.
**ENOMEM**|Es ist nicht genügend Arbeitsspeicher verfügbar, um den neuen Prozess auszuführen.

Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Jede dieser Funktionen erstellt einen neuen Prozess und führt sie aus, und übergibt ein Array von Zeigern auf Befehlszeilenargumente und verwendet die **Pfad** -Umgebungsvariable zum Ermitteln der auszuführenden Datei.

Diese Funktionen überprüfen ihre Parameter. Wenn entweder *Cmdname* oder *Argv* ein null-Zeiger ist oder wenn *Argv* null-Zeiger zeigt oder *Argv*[0] ist eine leere Zeichenfolge, die ungültige parameterhandler aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, legen diese Funktionen **Errno** auf **EINVAL**, und geben-1 zurück. Es wird kein neuer Prozess erzeugt.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_spawnvp**|\<stdio.h> oder \<process.h>|
|**_wspawnvp**|\<stdio.h> oder \<wchar.h>|

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

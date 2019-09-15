---
title: _execl, _wexecl
ms.date: 11/04/2016
api_name:
- _execl
- _wexecl
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
- api-ms-win-crt-process-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _execl
- _wexecl
- wexecl
helpviewer_keywords:
- _execl function
- wexecl function
- _wexecl function
- execl function
ms.assetid: 81fefb8a-0a06-4221-b2bc-be18e38e89f4
ms.openlocfilehash: 714ef80c4909e92100c4fa869b7544239f8edeb7
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70941942"
---
# <a name="_execl-_wexecl"></a>_execl, _wexecl

Lädt neue untergeordnete Prozesse und führt sie aus.

> [!IMPORTANT]
> Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
intptr_t _execl(
   const char *cmdname,
   const char *arg0,
   ... const char *argn,
   NULL
);
intptr_t _wexecl(
   const wchar_t *cmdname,
   const wchar_t *arg0,
   ... const wchar_t *argn,
   NULL
);
```

### <a name="parameters"></a>Parameter

*cmdname*<br/>
Pfad der auszuführenden Datei.

*arg0*,... *argN*<br/>
Liste von Zeigern zu den Parametern.

## <a name="return-value"></a>Rückgabewert

Bei Erfolg kehren diese Funktionen nicht zum aufrufenden Prozess zurück. Der Rückgabewert-1 gibt einen Fehler an. in diesem Fall ist die globale Variable **errno** festgelegt.

|errno-Wert|Beschreibung|
|-----------------|-----------------|
|**E2BIG**|Für die Argumente und die Umgebungseinstellungen werden mehr als 32 KB Speicherplatz benötigt.|
|**EACCES**|Für die angegebene Datei ist eine Sperr- oder Freigabeverletzung aufgetreten.|
|**EINVAL**|Ungültiger Parameter (mindestens ein Parameter ist ein NULL-Zeiger oder eine leere Zeichenfolge).|
|**EMFILE**|Zu viele Dateien geöffnet (die angegebene Datei muss geöffnet werden, damit festgestellt werden kann, ob sie ausführbar ist).|
|**ENOENT**|Die Datei oder der Pfad wurde nicht gefunden.|
|**ENOEXEC**|Die angegebene Datei ist nicht ausführbar oder hat ein ungültiges Format für eine ausführbare Datei.|
|**ENOMEM**|Es ist nicht genügend Arbeitsspeicher, um den neuen Prozess auszuführen; der verfügbare Arbeitsspeicher ist beschädigt; oder es ist ein ungültiger Block vorhanden, was darauf hinweist, dass der aufrufende Prozess nicht ordnungsgemäß zugeordnet wurde.|

## <a name="remarks"></a>Hinweise

Jede dieser Funktionen lädt einen neuen Prozess und führt ihn aus. Jedes Befehlszeilenargument wird dabei als separater Parameter übergeben. Das erste Argument ist der Name des Befehls oder der ausführbaren Datei. Das zweite Argument muss das gleiche wie das erste sein. Es wird im ausgeführten Prozess zu `argv[0]`. Das dritte Argument `argv[1]` ist das erste Argument des ausgeführten Prozesses.

Die **_execl** -Funktionen überprüfen Ihre Parameter. Wenn entweder *cmdname* oder *arg0* ein NULL-Zeiger oder eine leere Zeichenfolge ist, rufen diese Funktionen den Handler für ungültige Parameter auf, wie unter [Parameter Validierung](../../c-runtime-library/parameter-validation.md) beschrieben, wenn die weitere Ausführung zugelassen wird. diese Funktionen legen **errno** auf **fest. EINVAL** und Rückgabe-1. Es wird kein neuer Prozess ausgeführt.

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|Optionaler Header|
|--------------|---------------------|---------------------|
|**_execl**|\<process.h>|\<errno.h>|
|**_wexecl**|\<process.h> oder \<wchar.h>|\<errno.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Siehe das Beispiel in [_exec-, _wexec-Funktionen](../../c-runtime-library/exec-wexec-functions.md).

## <a name="see-also"></a>Siehe auch

[Prozess- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)<br/>
[_exec- und _wexec-Funktionen](../../c-runtime-library/exec-wexec-functions.md)<br/>
[abort](abort.md)<br/>
[atexit](atexit.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[_onexit, _onexit_m](onexit-onexit-m.md)<br/>
[_spawn-, _wspawn-Funktionen](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>

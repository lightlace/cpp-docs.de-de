---
title: abort | Microsoft-Dokumentation
ms.custom: ''
ms.date: 1/02/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- abort
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
- Abort
dev_langs:
- C++
helpviewer_keywords:
- aborting current process
- abort function
- processes, aborting
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 943faab6b13f3d07b2ca19d78c555973149aa4b0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32392613"
---
# <a name="abort"></a>abort

Bricht den aktuellen Prozess ab und gibt einen Fehlercode zurück.

> [!NOTE]
> Verwenden Sie diese Methode nicht, eine Microsoft Store-app oder universelle Windows-Plattform (UWP)-app, mit Ausnahme von Herunterfahren in Test- oder Debugszenarien. Programmgesteuerte oder UI-Methoden zum Schließen einer Store-app sind nicht zulässig, gemäß der [Microsoft Store-Richtlinien](/legal/windows/agreements/store-policies). Weitere Informationen finden Sie unter [uwp-app-Lebenszyklus](/windows/uwp/launch-resume/app-lifecycle).

## <a name="syntax"></a>Syntax

```c
void abort( void );
```

## <a name="return-value"></a>Rückgabewert

**Abort** gibt nicht die Steuerung an den aufrufenden Prozess zurück. Standardmäßig überprüft, ob ein abbruchsignalhandler und löst **SIGABRT** Wenn diese festgelegt ist. Klicken Sie dann **abort** beendet den aktuellen Prozess und gibt einen Exitcode an den übergeordneten Prozess zurück.

## <a name="remarks"></a>Hinweise

**Microsoft-spezifisch**

In der Standardeinstellung, wenn eine app mit der debuglaufzeitbibliothek erstellt wird die **Abbrechen** Routine zeigt eine Fehlermeldung vor **SIGABRT** ausgelöst wird. Bei Konsolen-apps, die im Konsolenmodus ausgeführt, die Nachricht gesendet wird, um **"stderr"**. Bei Windows-Desktop-Apps und Konsolen-Apps, die im Fenstermodus ausgeführt werden, wird die Meldung in einem Meldungsfeld angezeigt. Verwenden Sie zum Unterdrücken der Meldung [_set_abort_behavior](set-abort-behavior.md) zum Deaktivieren der **_WRITE_ABORT_MSG** Flag. Die Meldung, die angezeigt wird, hängt von der Version der verwendeten Laufzeitumgebung ab. Für Anwendungen, die mit den neuesten Versionen von Visual C++ erstellt haben sieht die Nachricht folgendermaßen aus:

> R6010 - abort() aufgerufen

In früheren Versionen der C-Laufzeitbibliothek wurde diese Meldung angezeigt:

> Diese Anwendung hat ein nicht ordnungsgemäßes Beenden der Runtime angefordert. Weitere Informationen erhalten Sie von dem für die Anwendung zuständigen Supportteam.

Wenn das Programm im Debugmodus kompiliert wird, zeigt das Meldungsfeld Optionen zum **Abbrechen**, **Wiederholen** oder **Ignorieren** an. Wenn der Benutzer **Abbrechen** auswählt, wird das Programm sofort beendet und gibt einen Exitcode von 3 zurück. Wenn der Benutzer **Wiederholen** auswählt, wird ein Debugger für Just-In-Time-Debuggen aufgerufen, falls verfügbar. Wenn der Benutzer wählt **ignorieren**, **abort** setzt die normale Verarbeitung fort.

In Verkaufsversionen und Builds **abort** dann überprüft, ob ein abbruchsignalhandler festgelegt ist. Wenn ein nicht standardmäßiger Signalhandler festgelegt ist, **abort** Aufrufe `raise(SIGABRT)`. Verwenden der [Signal](signal.md) Funktion, um eine abbruchsignalhandler-Funktion mit Zuordnen der **SIGABRT** Signal. Sie können benutzerdefinierte Aktionen wie das Bereinigen von Logressourcen oder Loginformationen ausführen und die App mit Ihrem eigenen Fehlercode in der Handlerfunktion beenden. Wenn kein benutzerdefinierter Signalhandler definiert ist, **abort** löst die **SIGABRT** Signal.

In nicht-Debugbuilds von Desktop- oder Konsolen-apps standardmäßig **abort** ruft dann die Windows Error Reporting Service-Mechanismus (früher als Dr bezeichnet. Watson) auf, um fehlgeschlagene Operationen an Microsoft zu melden. Dieses Verhalten kann aktiviert oder deaktiviert durch Aufrufen von **_set_abort_behavior** und festlegt oder maskiert der **_CALL_REPORTFAULT** Flag. Wenn das Flag festgelegt ist, zeigt Windows ein Meldungsfeld mit einem Text an, der in etwa wie folgt lautet: Ein Problem hat dazu geführt, dass das Programm gestoppt wurde oder nicht mehr ordnungsgemäß ausgeführt wird. Der Benutzer kann dann entweder einen Debugger über die Schaltfläche **Debuggen** aufrufen oder die Schaltfläche **Programm** schließen auswählen, um die App mit einem vom Betriebssystem definierten Fehlercode beenden.

Wenn die Windows-Fehlerberichterstattung-Handler nicht, klicken Sie dann aufgerufen wird **abort** Aufrufe [_exit](exit-exit-exit.md) den Prozess mit Exit Code 3 und übergibt die Steuerung an den übergeordneten Prozess oder dem Betriebssystem beendet. **_exit** keine Streampuffer geleert oder **Atexit**/**_onexit** verarbeiten.

Weitere Informationen zum CRT-Debugging (C Runtime Library) finden Sie unter [CRT-Debugverfahren](/visualstudio/debugger/crt-debugging-techniques).

**Ende Microsoft-spezifisch**

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**abort**|\<process.h> oder\<stdlib.h>|

## <a name="example"></a>Beispiel

Das folgende Programm versucht, eine Datei zu öffnen und bricht den Vorgang ab, wenn der Versuch fehlschlägt.

```C
// crt_abort.c
// compile with: /TC
// This program demonstrates the use of
// the abort function by attempting to open a file
// and aborts if the attempt fails.

#include  <stdio.h>
#include  <stdlib.h>

int main( void )
{
    FILE    *stream = NULL;
    errno_t err = 0;

    err = fopen_s(&stream, "NOSUCHF.ILE", "r" );
    if ((err != 0) || (stream == NULL))
    {
        perror( "File could not be opened" );
        abort();
    }
    else
    {
        fclose( stream );
    }
}
```

```Output
File could not be opened: No such file or directory
```

## <a name="see-also"></a>Siehe auch

[Verwenden von „abort“](../../cpp/using-abort.md)<br/>
[abort-Funktion](../../c-language/abort-function-c.md)<br/>
[Prozess- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)<br/>
[_exec- und _wexec-Funktionen](../../c-runtime-library/exec-wexec-functions.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[raise](raise.md)<br/>
[signal](signal.md)<br/>
[_spawn-, _wspawn-Funktionen](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[_DEBUG](../../c-runtime-library/debug.md)<br/>
[_set_abort_behavior](set-abort-behavior.md)<br/>

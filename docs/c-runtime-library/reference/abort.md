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
ms.openlocfilehash: bc7aefdac322ca8b34bccd2e377534ed1eca47e8
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2018
ms.locfileid: "39402711"
---
# <a name="abort"></a>abort

Bricht den aktuellen Prozess ab und gibt einen Fehlercode zurück.

> [!NOTE]
> Verwenden Sie diese Methode nicht, eine Microsoft Store-app oder app für universelle Windows-Plattform (UWP), mit Ausnahme von Herunterfahren in Test- oder Debugszenarien. Programmgesteuerte oder UI-Methoden zum Schließen einer Store-app sind nicht zulässig, gemäß der [Microsoft Store Richtlinien](/legal/windows/agreements/store-policies). Weitere Informationen finden Sie unter [UWP-app-Lebenszyklus](/windows/uwp/launch-resume/app-lifecycle).

## <a name="syntax"></a>Syntax

```C
void abort( void );
```

## <a name="return-value"></a>Rückgabewert

**Abbrechen** gibt nicht die Steuerung an den aufrufenden Prozess zurück. Standardmäßig sucht es nach einem Abbruchsignalhandler und löst `SIGABRT` aus, sofern vorhanden. Klicken Sie dann **Abbrechen** beendet den aktuellen Prozess und gibt einen Exitcode für den übergeordneten Prozess zurück.

## <a name="remarks"></a>Hinweise

**Microsoft-spezifisch**

Wenn eine app mit der debuglaufzeitbibliothek erstellt wird, wird standardmäßig die **Abbrechen** Routine zeigt eine Fehlermeldung vor `SIGABRT` ausgelöst wird. Bei Konsolen-Apps, die im Konsolenmodus ausgeführt werden, wird die Meldung an `STDERR` gesendet. Bei Windows-Desktop-Apps und Konsolen-Apps, die im Fenstermodus ausgeführt werden, wird die Meldung in einem Meldungsfeld angezeigt. Zum Unterdrücken der Meldung verwenden Sie [_set_abort_behavior](set-abort-behavior.md), um das `_WRITE_ABORT_MSG`-Flag zu löschen. Die Meldung, die angezeigt wird, hängt von der Version der verwendeten Laufzeitumgebung ab. Für Anwendungen, die mit den neuesten Versionen von Visual C++ erstellt haben sieht die Nachricht folgendermaßen aus:

> R6010 - wurde abort() aufgerufen

In früheren Versionen der C-Laufzeitbibliothek wurde diese Meldung angezeigt:

> Diese Anwendung hat ein nicht ordnungsgemäßes Beenden der Runtime angefordert. Weitere Informationen erhalten Sie von dem für die Anwendung zuständigen Supportteam.

Wenn das Programm im Debugmodus kompiliert wird, zeigt das Meldungsfeld Optionen zum **Abbrechen**, **Wiederholen** oder **Ignorieren** an. Wenn der Benutzer **Abbrechen** auswählt, wird das Programm sofort beendet und gibt einen Exitcode von 3 zurück. Wenn der Benutzer **Wiederholen** auswählt, wird ein Debugger für Just-In-Time-Debuggen aufgerufen, falls verfügbar. Wenn der Benutzer wählt **ignorieren**, **Abbrechen** setzt die normale Verarbeitung fort.

In Verkaufsversionen und Debugbuilds Builds **Abbrechen** dann überprüft, ob ein abbruchsignalhandler festgelegt ist. Wenn ein nicht standardmäßiger Signalhandler festgelegt ist, **Abbrechen** Aufrufe `raise(SIGABRT)`. Verwenden Sie die Funktion [Signal](signal.md), um eine Abbruchsignalhandler-Funktion zum `SIGABRT`-Signal zuzuordnen. Sie können benutzerdefinierte Aktionen wie das Bereinigen von Logressourcen oder Loginformationen ausführen und die App mit Ihrem eigenen Fehlercode in der Handlerfunktion beenden. Wenn kein benutzerdefinierter Signalhandler definiert ist, **Abbrechen** löst nicht die `SIGABRT` Signal.

Standardmäßig wird in nicht Debugbuilds von Desktop- oder Konsolen-apps **Abbrechen** ruft dann die Windows Error Reporting Service-Mechanismus (ehemals Notfallwiederherstellung. Watson) auf, um fehlgeschlagene Operationen an Microsoft zu melden. Dieses Verhalten kann aktiviert oder deaktiviert werden, indem `_set_abort_behavior` aufgerufen und das `_CALL_REPORTFAULT`-Flag festlegt oder maskiert wird. Wenn das Flag festgelegt ist, zeigt Windows ein Meldungsfeld mit einem Text an, der in etwa wie folgt lautet: Ein Problem hat dazu geführt, dass das Programm gestoppt wurde oder nicht mehr ordnungsgemäß ausgeführt wird. Der Benutzer kann dann entweder einen Debugger über die Schaltfläche **Debuggen** aufrufen oder die Schaltfläche **Programm** schließen auswählen, um die App mit einem vom Betriebssystem definierten Fehlercode beenden.

Wenn die Windows-Fehlerberichterstattung-Handler nicht, klicken Sie dann aufgerufen wird **Abbrechen** Aufrufe [_exit](exit-exit-exit.md) zum Beenden des Prozesses mit Exit Code 3 und übergibt die Steuerung an den übergeordneten Prozess oder das Betriebssystem. Von `_exit` werden weder Streampuffer geleert noch eine `atexit`/`_onexit`-Verarbeitung ausgeführt.

Weitere Informationen zum CRT-Debugging finden Sie unter [CRT-Debugverfahren](/visualstudio/debugger/crt-debugging-techniques).

**Ende Microsoft-spezifisch**

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
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

[Verwenden von „abort“](../../cpp/using-abort.md)  
[abort-Funktion](../../c-language/abort-function-c.md)  
[Prozess- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)  
[_exec- und _wexec-Funktionen](../../c-runtime-library/exec-wexec-functions.md)  
[exit, _Exit, _exit](exit-exit-exit.md)  
[raise](raise.md)  
[signal](signal.md)  
[_spawn-, _wspawn-Funktionen](../../c-runtime-library/spawn-wspawn-functions.md)  
[_DEBUG](../../c-runtime-library/debug.md)  
[_set_abort_behavior](set-abort-behavior.md)  
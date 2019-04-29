---
title: signal
ms.date: 04/12/2018
apiname:
- signal
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
- signal
helpviewer_keywords:
- signal function
ms.openlocfilehash: 351bdbe1d787fc5e5d741460adfe415df7fda756
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62356289"
---
# <a name="signal"></a>signal

Legt die Verarbeitung des Unterbrechungssignals fest.

> [!IMPORTANT]
> Verwenden Sie diese Methode nicht, eine Microsoft Store-app, mit Ausnahme von Herunterfahren in Test- oder Debugszenarien. Programmgesteuerte oder UI-Methoden zum Schließen einer Store-app sind nicht zulässig, gemäß der [Microsoft Store Richtlinien](/legal/windows/agreements/store-policies). Weitere Informationen finden Sie unter [UWP-app-Lebenszyklus](/windows/uwp/launch-resume/app-lifecycle).

## <a name="syntax"></a>Syntax

```C
void __cdecl *signal(int sig, int (*func)(int, int));
```

### <a name="parameters"></a>Parameter

*sig*<br/>
Signalwert.

*func*<br/>
Der zweite Parameter ist ein Zeiger auf die Funktion, die ausgeführt werden. Der erste Parameter ist ein Signalwert und der zweite Parameter ist ein Untercode, der verwendet werden kann, wenn der erste Parameter SIGFPE lautet.

## <a name="return-value"></a>Rückgabewert

**Signal** gibt zurück, den vorherigen Wert der Funktion, die dem angegebenen Signal zugeordnet ist. Z. B. wenn der vorherige Wert der *Func* wurde **SIG_IGN**, der Rückgabewert ist ebenfalls **SIG_IGN**. Der Rückgabewert **SIG_ERR** gibt einen Fehler an; in diesem Fall **Errno** nastaven NA hodnotu **EINVAL**.

Weitere Informationen zu Rückgabecodes finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die **Signal** -Funktion ermöglicht, einen Vorgang aus, um eine von mehreren Möglichkeiten zum Behandeln eines Unterbrechungssignals vom Betriebssystem auszuwählen. Die *Sig* Argument ist die Unterbrechung, auf die **Signal** reagiert; es muss eine der folgenden Manifestkonstanten, die im SIGNAL definiert sind. H.

|*SIG* Wert|Beschreibung|
|-----------------|-----------------|
|**SIGABRT**|Nicht ordnungsgemäße Beendigung|
|**SIGFPE**|Gleitkommafehler|
|**SIGILL**|Ungültige Anweisung|
|**SIGINT**|STRG+C-Signal|
|**SIGSEGV**|Ungültiger Speicherzugriff|
|**SIGTERM**|Beendigungsanforderung|

Wenn *Sig* ist keiner der oben genannten Werte an, den Handler für ungültige Parameter aufgerufen wird, der gemäß [Parametervalidierung](../../c-runtime-library/parameter-validation.md) . Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, setzt diese Funktion **Errno** zu **EINVAL** und gibt **SIG_ERR**.

In der Standardeinstellung **Signal** beendet das aufrufende Programm mit Exitcode 3, unabhängig vom Wert der *Sig*.

> [!NOTE]
> **SIGINT** wird für jede Win32-Anwendung nicht unterstützt. Wenn es zu einer STRG+C-Unterbrechung kommt, generieren Win32-Betriebssysteme einen neuen Thread, um speziell diese Unterbrechung zu verarbeiten. Dies kann dazu führen, dass eine Singlethreadanwendung, z. B. eine Anwendung in UNIX, zu einer Multithreadanwendung wird und ein unerwartetes Verhalten verursacht.

Die *Func* Argument ist eine Adresse eines signalhandlers ausgeführt, die Sie schreiben oder eine der vordefinierten Konstanten **SIG_DFL** oder **SIG_IGN**, die auch im SIGNAL definiert werden. H. Wenn *Func* ist eine Funktion, er wird als Signalhandler für das angegebene Signal installiert. Prototyp des signalhandlers erfordert ein formales Argument, *Sig*, des Typs **Int**. Das Betriebssystem bietet das tatsächliche Argument über *Sig* , wenn eine Unterbrechung auftritt; das Argument ist das Signal, das die Unterbrechung generiert hat. Daher können Sie die sechs (in der vorangehenden Tabelle aufgeführten) Manifestkonstanten in Ihrem Signalhandler verwenden, um zu bestimmen, welche Unterbrechung aufgetreten ist, und entsprechende Maßnahmen ergreifen. Sie können z. B. Aufrufen **Signal** zweimal auf zwei unterschiedlichen Signalen den gleichen Handler zuweisen, und Testen Sie dann die *Sig* -Argument im Handler, unterschiedliche Aktionen auf Grundlage des empfangenen Signals.

Wenn Sie für Gleitkommaausnahmen testen (**SIGFPE**), *Func* verweist auf eine Funktion, die einem optionalen zweiten Argument, das akzeptiert ist eine von mehreren Manifestkonstanten, die in "float" definiert. H, der das Formular **FPE_xxx**. Wenn eine **SIGFPE** -Signal auftritt, können Sie testen, den Wert des zweiten Arguments für die Art der Gleitkommaausnahme zu bestimmen und dann entsprechende Maßnahmen ergreifen. Dieses Argument und seine möglichen Werte sind Microsoft-Erweiterungen.

Für Gleitkommaausnahmen wird der Wert des *Func* nicht zurückgesetzt, wenn das Signal empfangen wird. Zur Behandlung von Gleitkommaausnahmen verwenden Sie try/except-Klauseln, um die Gleitkommaoperationen zu umschließen. Sie können die Ausnahmen auch beheben, indem Sie [setjmp](setjmp.md) mit [longjmp](longjmp.md) verwenden. In beiden Fällen setzt der aufrufende Prozess die Ausführung fort und lässt den Gleitkommazustand des Prozesses undefiniert.

Wenn der Signalhandler zurückgibt, setzt der aufrufende Prozess die Ausführung sofort fort, und zwar von dem Punkt aus, an dem das Unterbrechungssignal empfangen wurde. Dies gilt unabhängig von der Art des Signals oder des Betriebsmodus.

Bevor die angegebene Funktion ausgeführt wird, den Wert der *Func* nastaven NA hodnotu **SIG_DFL**. Das nächste Unterbrechungssignal wird behandelt, wie beschrieben für **SIG_DFL**, es sei denn, die zum Aufrufen einer dazwischen liegenden **Signal** angibt. Sie können diese Funktion verwenden, um Signale in der aufgerufenen Funktion zurückzusetzen.

Da Signalhandlerroutinen im Fall einer Unterbrechung normalerweise asynchron aufgerufen werden, kann Ihre Signalhandlerfunktion möglicherweise die Kontrolle übernehmen, wenn ein Laufzeitvorgang unvollständig ist und einen unbekannten Status aufweist. In der folgenden Liste sind die Einschränkungen zusammengefasst, die bestimmen, welche Funktionen Sie in der Signalhandlerroutine verwenden können.

- Führen Sie keine Routinen auf niedriger Ebene oder STDIO. H e/a-Routinen (z. B. **Printf** oder **Fread**).

- Rufen Sie nicht heaproutinen oder Routinen auf, die die heaproutinen verwenden (z. B. **Malloc**, **_strdup**, oder **_putenv**). Weitere Informationen finden Sie unter [malloc](malloc.md).

- Verwenden Sie keine Funktionen, die einen Systemaufruf generieren (z. B. **_getcwd** oder **Zeit**).

- Verwenden Sie keine **Longjmp** , wenn die Unterbrechung durch eine Gleitkommaausnahme verursacht wird (d. h. *Sig* ist **SIGFPE**). In diesem Fall zunächst initialisieren das gleitkommapaket, indem Sie über einen Aufruf an **_fpreset**.

- Verwenden Sie keine Overlayroutinen.

Ein Programm muss gleitkommacode enthalten, falls sie zum Abfangen der **SIGFPE** Ausnahme mithilfe der Funktion. Wenn Ihr Programm keinen Gleitkommacode enthält und den Signalverarbeitungscode der Laufzeitbibliothek erfordert, deklarieren Sie einfach ein flüchtiges Double und initialisieren Sie es mit Null:

```C
volatile double d = 0.0f;
```

Die **SIGILL** und **SIGTERM** Signale werden unter Windows nicht generiert. Sie sind zur Gewährleistung der ANSI-Kompatibilität enthalten. Sie können daher Signalhandler für diese Signale festlegen, mit **Signal**, und Sie können diese Signale explizit generieren, durch den Aufruf [auslösen](raise.md).

In gestarteten Prozessen, die durch Aufrufe erstellt werden werden signaleinstellungen nicht beibehalten [_exec](../../c-runtime-library/exec-wexec-functions.md) oder [_spawn](../../c-runtime-library/spawn-wspawn-functions.md) Funktionen. Die Signaleinstellungen werden im neuen Prozess auf die Standardwerte zurückgesetzt.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**signal**|\<signal.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, wie Sie mit **Signal** ein benutzerdefiniertes Verhalten hinzufügen der **SIGABRT** Signal. Weitere Informationen zum Abbruchverhalten finden Sie unter [_set_abort_behavior](set-abort-behavior.md).

```C
// crt_signal.c
// compile with: /EHsc /W4
// Use signal to attach a signal handler to the abort routine
#include <stdlib.h>
#include <signal.h>
#include <tchar.h>

void SignalHandler(int signal)
{
    if (signal == SIGABRT) {
        // abort signal handler code
    } else {
        // ...
    }
}

int main()
{
    typedef void (*SignalHandlerPointer)(int);

    SignalHandlerPointer previousHandler;
    previousHandler = signal(SIGABRT, SignalHandler);

    abort();
}
```

```Output
This application has requested the Runtime to terminate it in an unusual way.
Please contact the application's support team for more information.
```

## <a name="see-also"></a>Siehe auch

[Prozess- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)<br/>
[abort](abort.md)<br/>
[_exec- und _wexec-Funktionen](../../c-runtime-library/exec-wexec-functions.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[_fpreset](fpreset.md)<br/>
[_spawn-, _wspawn-Funktionen](../../c-runtime-library/spawn-wspawn-functions.md)<br/>

---
title: signal | Microsoft-Dokumentation
ms.custom: 
ms.date: 1/02/2018
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: signal
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
f1_keywords: signal
dev_langs: C++
helpviewer_keywords: signal function
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 337bc5e222ee7fcb313d0b7ea0722dbb5cacea75
ms.sourcegitcommit: a5d8f5b92cb5e984d5d6c9d67fe8a1241f3fe184
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/05/2018
---
# <a name="signal"></a>signal

Legt die Verarbeitung des Unterbrechungssignals fest.

> [!IMPORTANT]
> Verwenden Sie diese Methode nicht, eine Microsoft Store-app mit Ausnahme von Herunterfahren in Test- oder Debugszenarien. Programmgesteuerte oder UI-Methoden zum Schließen einer Store-app sind nicht zulässig, gemäß der [Microsoft Store-Richtlinien](http://go.microsoft.com/fwlink/?LinkId=865936). Weitere Informationen finden Sie unter [uwp-app-Lebenszyklus](http://go.microsoft.com/fwlink/p/?LinkId=865934).

## <a name="syntax"></a>Syntax

```C
void (__cdecl *signal(
   int sig,
   void (__cdecl *func ) (int [, int ] )))(int);
```

### <a name="parameters"></a>Parameter
_sig_  
Signalwert.

_Func_  
Auszuführende Funktion. Der erste Parameter ist ein Signalwert und der zweite Parameter ist ein Untercode, der verwendet werden kann, wenn der erste Parameter SIGFPE lautet.

## <a name="return-value"></a>Rückgabewert

`signal`Gibt den vorherigen Wert der _Func_ , die dem angegebenen Signal zugeordnet wurde. Beispielsweise, wenn der vorherige Wert der _Func_ wurde `SIG_IGN`, der Rückgabewert ist ebenfalls `SIG_IGN`. Der Rückgabewert `SIG_ERR` gibt einen Fehler an. In diesem Fall wird `errno` auf `EINVAL` festgelegt.

Weitere Informationen zu Rückgabecodes finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die `signal`-Funktion ermöglicht einem Prozess, eine von mehreren Methoden zur Verarbeitung eines Unterbrechungssignals vom Betriebssystem auszuwählen. Die _Sig_ Argument ist die Unterbrechung, auf die `signal` antwortet; muss es sich um eine der folgenden Manifestkonstanten besteht, die im SIGNAL definiert sind. H.

|_SIG_ Wert|Beschreibung|
|-----------------|-----------------|
|`SIGABRT`|Nicht ordnungsgemäße Beendigung|
|`SIGFPE`|Gleitkommafehler|
|`SIGILL`|Ungültige Anweisung|
|`SIGINT`|STRG+C-Signal|
|`SIGSEGV`|Ungültiger Speicherzugriff|
|`SIGTERM`|Beendigungsanforderung|

Wenn _Sig_ ist keiner der oben genannten Werte Handler für ungültige Parameter aufgerufen wird, der gemäß [Parametervalidierung](../../c-runtime-library/parameter-validation.md) . Wenn die weitere Ausführung zugelassen wird, legt diese Funktion `errno` auf `EINVAL` fest und gibt `SIG_ERR` zurück.

Standardmäßig `signal` beendet das aufrufende Programm mit Exitcode 3, unabhängig vom Wert der _Sig_.

> [!NOTE]
> `SIGINT` wird nicht für jede Win32-Anwendung unterstützt. Wenn es zu einer STRG+C-Unterbrechung kommt, generieren Win32-Betriebssysteme einen neuen Thread, um speziell diese Unterbrechung zu verarbeiten. Dies kann dazu führen, dass eine Singlethreadanwendung, z. B. eine Anwendung in UNIX, zu einer Multithreadanwendung wird und ein unerwartetes Verhalten verursacht.

Die _Func_ -Argument ist eine Adresse ein, den Sie schreiben, oder auf eine der vordefinierten Konstanten `SIG_DFL` oder `SIG_IGN`, die auch in SIGNAL definiert werden. H. Wenn _Func_ eine Funktion ist, wird sie als Signalhandler für das angegebene Signal installiert. Prototyp des signalhandlers erfordert ein formales Argument, _Sig_, vom Typ `int`. Das Betriebssystem stellt das tatsächliche Argument über _Sig_ , wenn eine Unterbrechung auftritt; das Argument ist das Signal, das die Unterbrechung generiert hat. Daher können Sie die sechs (in der vorangehenden Tabelle aufgeführten) Manifestkonstanten in Ihrem Signalhandler verwenden, um zu bestimmen, welche Unterbrechung aufgetreten ist, und entsprechende Maßnahmen ergreifen. Sie können z. B. Aufrufen `signal` zweimal auf zwei unterschiedlichen Signalen den gleichen Handler zuzuweisen, und klicken Sie dann Testen der _Sig_ -Argument im Handler, die verschiedene Aktionen auf Grundlage des empfangenen Signals.

Wenn Sie auf Gleitkommaausnahmen testen (`SIGFPE`), _Func_ zeigt auf eine Funktion, die ein optionales zweites Argument akzeptiert, der mehrere Manifestkonstanten – in "float" definiert. H – des Formulars `FPE_xxx`. Wenn ein `SIGFPE`-Signal auftritt, können Sie den Wert des zweiten Arguments testen, um die Art der Gleitkommaausnahme zu bestimmen. Anschließend können Sie entsprechende Maßnahmen ergreifen. Dieses Argument und seine möglichen Werte sind Microsoft-Erweiterungen.

Für Gleitkommaausnahmen wird der Wert der _Func_ nicht zurückgesetzt, wenn das Signal empfangen wird. Zur Behandlung von Gleitkommaausnahmen verwenden Sie try/except-Klauseln, um die Gleitkommaoperationen zu umschließen. Sie können die Ausnahmen auch beheben, indem Sie [setjmp](../../c-runtime-library/reference/setjmp.md) mit [longjmp](../../c-runtime-library/reference/longjmp.md) verwenden. In beiden Fällen setzt der aufrufende Prozess die Ausführung fort und lässt den Gleitkommazustand des Prozesses undefiniert.

Wenn der Signalhandler zurückgibt, setzt der aufrufende Prozess die Ausführung sofort fort, und zwar von dem Punkt aus, an dem das Unterbrechungssignal empfangen wurde. Dies gilt unabhängig von der Art des Signals oder des Betriebsmodus.

Bevor die angegebene Funktion ausgeführt wird, den Wert der _Func_ festgelegt ist, um `SIG_DFL`. Das nächste Unterbrechungssignal wird wie für `SIG_DFL` beschrieben behandelt, sofern ein zwischenzeitlicher Aufruf von `signal` nichts anderes vorsieht. Sie können diese Funktion verwenden, um Signale in der aufgerufenen Funktion zurückzusetzen.

Da Signalhandlerroutinen im Fall einer Unterbrechung normalerweise asynchron aufgerufen werden, kann Ihre Signalhandlerfunktion möglicherweise die Kontrolle übernehmen, wenn ein Laufzeitvorgang unvollständig ist und einen unbekannten Status aufweist. In der folgenden Liste sind die Einschränkungen zusammengefasst, die bestimmen, welche Funktionen Sie in der Signalhandlerroutine verwenden können.

- Geben Sie keine Routinen auf niedriger Ebene oder STDIO.H-E/A-Routinen aus (z. B. `printf` oder `fread`).

- Rufen Sie keine Heaproutinen oder Routinen auf, die die Heaproutinen verwenden (z. B. `malloc`, `_strdup` oder `_putenv`). Weitere Informationen finden Sie unter [malloc](../../c-runtime-library/reference/malloc.md).

- Verwenden Sie keine Funktionen, die einen Systemaufruf generieren (z. B. `_getcwd` oder `time`).

- Verwenden Sie keine `longjmp` , wenn die Unterbrechung durch eine Gleitkommaausnahme verursacht wird (d. h. _Sig_ ist `SIGFPE`). Initialisieren Sie in diesem Fall mithilfe eines Aufrufs von `_fpreset` zuerst das Gleitkommapaket neu.

- Verwenden Sie keine Overlayroutinen.

Ein Programm muss Gleitkommacode enthalten, wenn er die `SIGFPE`-Ausnahme mithilfe der Funktion abfangen soll. Wenn Ihr Programm keinen Gleitkommacode enthält und den Signalverarbeitungscode der Laufzeitbibliothek erfordert, deklarieren Sie einfach ein flüchtiges Double und initialisieren Sie es mit Null:

`volatile double d = 0.0f;`

Die Signale `SIGILL` und `SIGTERM` werden unter Windows nicht generiert. Sie sind zur Gewährleistung der ANSI-Kompatibilität enthalten. Daher können Sie mithilfe von `signal` Signalhandler für diese Signale festlegen, und Sie können diese Signale explizit generieren, indem Sie [raise](../../c-runtime-library/reference/raise.md) aufrufen.

In gestarteten Prozessen, die durch Aufrufe der Funktion `_exec` oder `_spawn` erstellt werden, werden Signaleinstellungen nicht beibehalten. Die Signaleinstellungen werden im neuen Prozess auf die Standardwerte zurückgesetzt.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|`signal`|\<signal.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, wie `signal` verwendet wird, um dem `SIGABRT`-Signal ein benutzerdefiniertes Verhalten hinzuzufügen. Weitere Informationen zum Abbruchverhalten finden Sie unter [_set_abort_behavior](../../c-runtime-library/reference/set-abort-behavior.md).

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

[Prozess- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)  
[abort](../../c-runtime-library/reference/abort.md)  
[_exec- und _wexec-Funktionen](../../c-runtime-library/exec-wexec-functions.md)  
[exit, _Exit, _exit](../../c-runtime-library/reference/exit-exit-exit.md)  
[_fpreset](../../c-runtime-library/reference/fpreset.md)  
[_spawn-, _wspawn-Funktionen](../../c-runtime-library/spawn-wspawn-functions.md)  

---
title: "signal | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "signal"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "signal"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "signal-Funktion"
ms.assetid: 094118de-d789-4063-b4f4-cffcc80bf29d
caps.latest.revision: 26
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 26
---
# signal
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Legt die Verarbeitung des Unterbrechungssignals fest.  
  
> [!IMPORTANT]
>  Verwenden Sie diese Methode nicht, um eine [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-App zu schließen, außer bei Tests oder in Debugszenarios.  Programmgesteuerte oder UI\-Methoden zum Schließen einer [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-App sind gemäß Abschnitt 3.6 der [Zertifizierungsanforderungen für Windows 8\-Apps](http://go.microsoft.com/fwlink/?LinkId=262889) nicht zulässig.  Weitere Informationen finden Sie unter [Anwendungslebenszyklus \(Windows Store\-Apps\)](http://go.microsoft.com/fwlink/?LinkId=262853).  
  
## Syntax  
  
```  
void (__cdecl *signal(  
   int sig,   
   void (__cdecl *func ) (int [, int ] )))   
   (int);  
```  
  
#### Parameter  
 `sig`  
 Signalwert.  
  
 `func`  
 Auszuführende Funktion.  Der erste Parameter ist ein Signalwert und der zweite Parameter ist ein Untercode, der verwendet werden kann, wenn der erste Parameter SIGFPE lautet.  
  
## Rückgabewert  
 `signal` gibt den vorherigen Wert von `func` zurück, der dem angegebenen Signal zugeordnet ist.  Wenn der vorherige Wert von `func` beispielsweise `SIG_IGN` lautete, lautet auch der Rückgabewert `SIG_IGN`.  Der Rückgabewert `SIG_ERR` gibt einen Fehler an. In diesem Fall wird `errno` auf `EINVAL` festgelegt.  
  
 Weitere Informationen zu Rückgabecodes finden Sie unter [errno, \_doserrno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 Die `signal`\-Funktion ermöglicht einem Prozess, eine von mehreren Methoden zur Verarbeitung eines Unterbrechungssignals vom Betriebssystem auszuwählen.  Das `sig`\-Argument ist die Unterbrechung, auf die `signal` reagiert. Es muss sich um eine der folgenden Manifestkonstanten handeln, die in SIGNAL.H. definiert sind.  
  
|`sig`\-Wert|**Beschreibung**|  
|-----------------|----------------------|  
|`SIGABRT`|Nicht ordnungsgemäße Beendigung|  
|`SIGFPE`|Gleitkommafehler|  
|`SIGILL`|Ungültige Anweisung|  
|`SIGINT`|STRG\+C\-Signal|  
|`SIGSEGV`|Ungültiger Speicherzugriff|  
|`SIGTERM`|Beendigungsanforderung|  
  
 Wenn `sig` keinem der oben genannten Werte entspricht, wird der Handler für ungültige Parameter aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) definiert.  Wenn die weitere Ausführung zugelassen wird, legt diese Funktion `errno` auf `EINVAL` fest und gibt `SIG_ERR` zurück.  
  
 Standardmäßig beendet `signal` das aufrufende Programm mit Exitcode 3, unabhängig vom Wert von `sig`.  
  
> [!NOTE]
>  `SIGINT` wird nicht für jede Win32\-Anwendung unterstützt.  Wenn es zu einer STRG\+C\-Unterbrechung kommt, generieren Win32\-Betriebssysteme einen neuen Thread, um speziell diese Unterbrechung zu verarbeiten.  Dies kann dazu führen, dass eine Singlethreadanwendung, z. B. eine Anwendung in UNIX, zu einer Multithreadanwendung wird und ein unerwartetes Verhalten verursacht.  
  
 Das `func`\-Argument ist eine Adresse eines von Ihnen geschriebenen Signalhandlers oder einer der vordefinierten Konstanten `SIG_DFL` oder `SIG_IGN`, die auch in SIGNAL.H. definiert sind.  Wenn `func` eine Funktion ist, wird sie als Signalhandler für das angegebene Signal installiert.  Der Prototyp des Signalhandlers erfordert ein formales Argument, `sig`, vom Typ `int`.  Das Betriebssystem stellt das tatsächliche Argument über `sig` bereit, wenn eine Unterbrechung auftritt. Das Argument ist das Signal, das die Unterbrechung generiert hat.  Daher können Sie die sechs \(in der vorangehenden Tabelle aufgeführten\) Manifestkonstanten in Ihrem Signalhandler verwenden, um zu bestimmen, welche Unterbrechung aufgetreten ist, und entsprechende Maßnahmen ergreifen.  Beispielsweise können Sie `signal` zweimal aufrufen, um zwei unterschiedlichen Signalen den gleichen Handler zuzuweisen, und dann das `sig`\-Argument im Handler testen, um verschiedene Aktionen auf Grundlage des empfangenen Signals zu ergreifen.  
  
 Wenn Sie auf Gleitkommaausnahmen \(`SIGFPE`\) testen, zeigt `func` auf eine Funktion, die ein optionales zweites Argument akzeptiert, bei dem es sich um eine von mehreren \(in FLOAT.H definierten\) Manifestkonstanten im Format `FPE_xxx` handelt.  Wenn ein `SIGFPE`\-Signal auftritt, können Sie den Wert des zweiten Arguments testen, um die Art der Gleitkommaausnahme zu bestimmen. Anschließend können Sie entsprechende Maßnahmen ergreifen.  Dieses Argument und seine möglichen Werte sind Microsoft\-Erweiterungen.  
  
 Für Gleitkommaausnahmen wird der Wert von `func` nicht zurückgesetzt, wenn das Signal empfangen wird.  Zur Behandlung von Gleitkommaausnahmen verwenden Sie try\/except\-Klauseln, um die Gleitkommaoperationen zu umschließen.  Sie können die Ausnahmen auch beheben, indem Sie [setjmp](../../c-runtime-library/reference/setjmp.md) mit [longjmp](../../c-runtime-library/reference/longjmp.md) verwenden.  In beiden Fällen setzt der aufrufende Prozess die Ausführung fort und lässt den Gleitkommazustand des Prozesses undefiniert.  
  
 Wenn der Signalhandler zurückgibt, setzt der aufrufende Prozess die Ausführung sofort fort, und zwar von dem Punkt aus, an dem das Unterbrechungssignal empfangen wurde.  Dies gilt unabhängig von der Art des Signals oder des Betriebsmodus.  
  
 Bevor die angegebene Funktion ausgeführt wird, wird der Wert von `func` auf `SIG_DFL` festgelegt.  Das nächste Unterbrechungssignal wird wie für `SIG_DFL` beschrieben behandelt, sofern ein zwischenzeitlicher Aufruf von `signal` nichts anderes vorsieht.  Sie können diese Funktion verwenden, um Signale in der aufgerufenen Funktion zurückzusetzen.  
  
 Da Signalhandlerroutinen im Fall einer Unterbrechung normalerweise asynchron aufgerufen werden, kann Ihre Signalhandlerfunktion möglicherweise die Kontrolle übernehmen, wenn ein Laufzeitvorgang unvollständig ist und einen unbekannten Status aufweist.  In der folgenden Liste sind die Einschränkungen zusammengefasst, die bestimmen, welche Funktionen Sie in der Signalhandlerroutine verwenden können.  
  
-   Geben Sie keine Routinen auf niedriger Ebene oder STDIO.H\-E\/A\-Routinen aus \(z. B. `printf` oder `fread`\).  
  
-   Rufen Sie keine Heaproutinen oder Routinen auf, die die Heaproutinen verwenden \(z. B. `malloc`, `_strdup` oder `_putenv`\).  Weitere Informationen finden Sie unter [malloc](../../c-runtime-library/reference/malloc.md).  
  
-   Verwenden Sie keine Funktionen, die einen Systemaufruf generieren \(z. B. `_getcwd` oder `time`\).  
  
-   Verwenden Sie `longjmp` nicht, es sei denn, die Unterbrechung wurde durch eine Gleitkommaausnahme verursacht \(d. h. `sig` entspricht `SIGFPE`\).  Initialisieren Sie in diesem Fall mithilfe eines Aufrufs von `_fpreset` zuerst das Gleitkommapaket neu.  
  
-   Verwenden Sie keine Overlayroutinen.  
  
 Ein Programm muss Gleitkommacode enthalten, wenn er die `SIGFPE`\-Ausnahme mithilfe der Funktion abfangen soll.  Wenn Ihr Programm keinen Gleitkommacode enthält und den Signalverarbeitungscode der Laufzeitbibliothek erfordert, deklarieren Sie einfach ein flüchtiges Double und initialisieren Sie es mit Null:  
  
```  
volatile double d = 0.0f;   
```  
  
 Die Signale `SIGILL` und `SIGTERM` werden unter Windows nicht generiert.  Sie sind zur Gewährleistung der ANSI\-Kompatibilität enthalten.  Daher können Sie mithilfe von `signal` Signalhandler für diese Signale festlegen, und Sie können diese Signale explizit generieren, indem Sie [raise](../../c-runtime-library/reference/raise.md) aufrufen.  
  
 In gestarteten Prozessen, die durch Aufrufe der Funktion `_exec` oder `_spawn` erstellt werden, werden Signaleinstellungen nicht beibehalten.  Die Signaleinstellungen werden im neuen Prozess auf die Standardwerte zurückgesetzt.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`signal`|\<signal.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie `signal` verwendet wird, um dem `SIGABRT`\-Signal ein benutzerdefiniertes Verhalten hinzuzufügen.  Weitere Informationen über Abbruchverhalten finden Sie unter [\_set\_abort\_behavior](../../c-runtime-library/reference/set-abort-behavior.md).  
  
```cpp  
// crt_signal.c  
// compile with: /EHsc /W4  
// Use signal to attach a signal handler to the abort routine  
#include <stdlib.h>  
#include <signal.h>  
#include <tchar.h>  
  
void SignalHandler(int signal)  
{  
    if (signal == SIGABRT) {  
        // abort signal handler code  
    } else {  
        // ...  
    }  
}  
  
int main()  
{  
    typedef void (*SignalHandlerPointer)(int);  
  
    SignalHandlerPointer previousHandler;  
    previousHandler = signal(SIGABRT, SignalHandler);  
  
    abort();  
}  
  
```  
  
  **Diese Anwendung hat ein nicht ordnungsgemäßes Beenden der Runtime angefordert.**  
**Weitere Informationen erhalten Sie von dem für die Anwendung zuständigen Supportteam.**   
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Prozess\- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [\_exec\- und \_wexec\-Funktionen](../../c-runtime-library/exec-wexec-functions.md)   
 [exit, \_Exit, \_exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [\_fpreset](../../c-runtime-library/reference/fpreset.md)   
 [\_spawn\- und \_wspawn\-Funktionen](../../c-runtime-library/spawn-wspawn-functions.md)
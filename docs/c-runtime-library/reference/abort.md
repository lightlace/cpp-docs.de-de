---
title: abort | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
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
ms.assetid: a797783b-40ed-4bdb-a2cd-14ffede39e8a
caps.latest.revision: 24
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 18a683e6581f979c0383c76a3ada2a8e80316255
ms.contentlocale: de-de
ms.lasthandoff: 03/29/2017

---
# <a name="abort"></a>abort
Bricht den aktuellen Prozess ab und gibt einen Fehlercode zurück.  
  
> [!NOTE]
>  Verwenden Sie diese Methode nicht, um eine [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]-App zu schließen, außer bei Tests oder in Debugszenarios. Programmgesteuerte oder UI-Methoden zum Schließen einer [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]-App sind gemäß den [Zertifizierungsanforderungen für Windows 8-Apps](http://go.microsoft.com/fwlink/?LinkId=262889) nicht zulässig. Weitere Informationen finden Sie unter [Anwendungslebenszyklus (Windows Store-Apps)](http://go.microsoft.com/fwlink/?LinkId=262853).  
  
## <a name="syntax"></a>Syntax  
  
```  
void abort( void );  
```  
  
## <a name="return-value"></a>Rückgabewert  
 `abort`gibt an den aufrufenden Prozess keine Steuerung zurück. Standardmäßig sucht es nach einem Abbruchsignalhandler und löst `SIGABRT` aus, sofern vorhanden. Anschließend beendet `abort` den aktuellen Prozess und gibt den Exitcode an den übergeordneten Prozess zurück.  
  
## <a name="remarks"></a>Hinweise  
 **Microsoft-spezifisch**  
  
 Standardmäßig zeigt die `abort`-Routine eine Fehlermeldung an, bevor `SIGABRT` ausgelöst wird, wenn eine App mit der Debuglaufzeitbibliothek erstellt wird. Bei Konsolen-Apps, die im Konsolenmodus ausgeführt werden, wird die Meldung an `STDERR` gesendet. Bei Windows-Desktop-Apps und Konsolen-Apps, die im Fenstermodus ausgeführt werden, wird die Meldung in einem Meldungsfeld angezeigt. Zum Unterdrücken der Meldung verwenden Sie [_set_abort_behavior](../../c-runtime-library/reference/set-abort-behavior.md), um das `_WRITE_ABORT_MSG`-Flag zu löschen. Die Meldung, die angezeigt wird, hängt von der Version der verwendeten Laufzeitumgebung ab. Bei Anwendungen, die mit der neuesten Version von Visual C++ erstellt wurden, sieht die Meldung wie folgt aus:  
  
 `R6010`  
  
 `- abort() has been called`  
  
 In früheren Versionen der C-Laufzeitbibliothek wurde diese Meldung angezeigt:  
  
 "`This application has requested the Runtime to terminate it in an unusual way. Please contact the application's support team for more information.`"  
  
 Wenn das Programm im Debugmodus kompiliert wird, zeigt das Meldungsfeld Optionen zum **Abbrechen**, **Wiederholen** oder **Ignorieren** an. Wenn der Benutzer **Abbrechen** auswählt, wird das Programm sofort beendet und gibt einen Exitcode von 3 zurück. Wenn der Benutzer **Wiederholen** auswählt, wird ein Debugger für Just-In-Time-Debuggen aufgerufen, falls verfügbar. Wenn der Benutzer **Ignorieren** auswählt, fährt `abort` mit der normalen Verarbeitung fort.  
  
 In Verkaufsversionen und Debugbuilds überprüft `abort` dann, ob ein Abbruchsignalhandler festgelegt ist. Wenn ein nicht standardmäßiger Signalhandler festgelegt ist, ruft `abort` `raise(SIGABRT)` auf. Verwenden Sie die Funktion [Signal](../../c-runtime-library/reference/signal.md), um eine Abbruchsignalhandler-Funktion zum `SIGABRT`-Signal zuzuordnen. Sie können benutzerdefinierte Aktionen wie das Bereinigen von Logressourcen oder Loginformationen ausführen und die App mit Ihrem eigenen Fehlercode in der Handlerfunktion beenden. Wenn kein benutzerdefinierter Signalhandler definiert ist, löst `abort` nicht das `SIGABRT`-Signal aus.  
  
 In nicht Debugbuilds von Desktop- oder Konsolen-Apps ruft `abort` dann standardmäßig den Windows-Fehlerbericht (Dr. Watson) auf, um fehlgeschlagene Operationen an Microsoft zu melden. Dieses Verhalten kann aktiviert oder deaktiviert werden, indem `_set_abort_behavior` aufgerufen und das `_CALL_REPORTFAULT`-Flag festlegt oder maskiert wird. Wenn das Flag festgelegt ist, zeigt Windows ein Meldungsfeld mit einem Text an, der in etwa wie folgt lautet: Ein Problem hat dazu geführt, dass das Programm gestoppt wurde oder nicht mehr ordnungsgemäß ausgeführt wird. Der Benutzer kann dann entweder einen Debugger über die Schaltfläche **Debuggen** aufrufen oder die Schaltfläche **Programm** schließen auswählen, um die App mit einem vom Betriebssystem definierten Fehlercode beenden.  
  
 Wenn der Windows-Fehlerberichtshandler nicht aufgerufen wird, ruft `abort` [_exit](../../c-runtime-library/reference/exit-exit-exit.md) auf, um den Prozess mit Exitcode 3 zu beenden. Darüber hinaus wird die Steuerung an den übergeordneten Prozess oder das Betriebssystem zurückgegeben. Von `_exit` werden weder Streampuffer geleert noch eine `atexit`/`_onexit`-Verarbeitung ausgeführt.  
  
 Weitere Informationen zum CRT-Debugging finden Sie unter [CRT-Debugverfahren](/visualstudio/debugger/crt-debugging-techniques).  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`abort`|\<process.h> oder\<stdlib.h>|  
  
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
 [abort-Funktion (C)](../../c-language/abort-function-c.md)   
 [Prozess- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)   
 [_exec-, _wexec-Funktionen](../../c-runtime-library/exec-wexec-functions.md)   
 [exit, _Exit, _exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [__raise](../../c-runtime-library/reference/raise.md)   
 [signal](../../c-runtime-library/reference/signal.md)   
 [_spawn-, _wspawn-Funktionen](../../c-runtime-library/spawn-wspawn-functions.md)   
 [_DEBUG](../../c-runtime-library/debug.md)   
 [_set_abort_behavior](../../c-runtime-library/reference/set-abort-behavior.md)

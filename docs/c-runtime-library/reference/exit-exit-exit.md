---
title: exit, _Exit, _exit | Microsoft-Dokumentation
ms.custom: ''
ms.date: 1/02/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _exit
- exit
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
- Exit
- _exit
- process/exit
- process/_Exit
- stdlib/exit
- stdlib/_Exit
dev_langs:
- C++
helpviewer_keywords:
- exit function
- _exit function
- processes, terminating
- function calls, terminating
- process termination, calling
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cb62c18f7508a21e24fb5628e8ac01162db1405e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32402711"
---
# <a name="exit-exit-exit"></a>exit, _Exit, _exit

Beendet den aufrufenden Prozess. Die **beenden** Funktion beendet ihn nach der Bereinigung; **_exit** und **_Exit** beenden ihn sofort.

> [!NOTE]
> Verwenden Sie diese Methode nicht, um eine app (Universelle Windows Plattform) mit Ausnahme von schließen in Test- oder Debugszenarien. Programmgesteuerte oder UI-Methoden zum Schließen einer Store-app sind nicht zulässig, gemäß der [Microsoft Store-Richtlinien](/legal/windows/agreements/store-policies). Weitere Informationen finden Sie unter [uwp-App-Lebenszyklus](/windows/uwp/launch-resume/app-lifecycle). Weitere Informationen zu Windows 10-Apps finden Sie unter [Anleitungen für Windows 10-Apps](http://go.microsoft.com/fwlink/p/?linkid=619133).

## <a name="syntax"></a>Syntax

```C
void exit(
   int const status
);
void _Exit(
   int const status
);
void _exit(
   int const status
);
```

### <a name="parameters"></a>Parameter

*Status* Beendigungsstatuscode.

## <a name="remarks"></a>Hinweise

Die **beenden**, **_Exit** und **_exit** Funktionen beenden den aufrufenden Prozess. Die **beenden** -Funktionsaufrufe Destruktoren für threadlokale Objekte, und ruft dann – Last in First Out (LIFO) nacheinander – die Funktionen, die von registrierten **Atexit** und **_onexit**, und klicken Sie dann alle Puffer geleert, bevor der Prozess beendet wird. Die **_Exit** und **_exit** Funktionen der Prozess beendet, ohne threadlokale Objekte zu zerstören oder Verarbeitung **Atexit** oder **_onexit**Funktionen, und ohne die Datenstrompuffer.

Obwohl die **beenden**, **_Exit** und **_exit** Aufrufe geben einen Wert, der Wert in nicht zurück *Status* hostumgebung zur Verfügung gestellt wird oder aufrufende Prozess warten, wenn eine vorhanden ist, nachdem der Prozess beendet wird. In der Regel der Aufrufer legt den *Status* Wert zur kennzeichnen einer normalen Beendigung auf 0 oder auf einen anderen Wert einen Fehler an. Die *Status* -Wert steht dem Betriebssystem-Batchbefehl **ERRORLEVEL** und wird durch eine der beiden Konstanten repräsentiert: **EXIT_SUCCESS**, die einen Wert darstellt 0 (null) oder **EXIT_FAILURE**, die einen Wert von 1 darstellt.

Die **beenden**, **_Exit**, **_exit**, **Quick_exit**, **_cexit**, und **_c_exit** Funktionen verhalten sich wie folgt.

|Funktion|Beschreibung|
|--------------|-----------------|
|**exit**|Führt vollständige C-Bibliotheksbeendigungsprozeduren aus, beendet den Prozess und übergibt den angegebenen Statuscode der Hostumgebung.|
|**_Exit**|Führt minimale C-Bibliotheksbeendigungsprozeduren aus, beendet den Prozess und übergibt den angegebenen Statuscode der Hostumgebung.|
|**_exit**|Führt minimale C-Bibliotheksbeendigungsprozeduren aus, beendet den Prozess und übergibt den angegebenen Statuscode der Hostumgebung.|
|**quick_exit**|Führt schnelle C-Bibliotheksbeendigungsprozeduren aus, beendet den Prozess und übergibt den angegebenen Statuscode der Hostumgebung.|
|**_cexit**|Führt vollständige C-Bibliotheksbeendigungsprozeduren aus und kehrt zum Aufrufer zurück. Der Prozess wird nicht beendet.|
|**_c_exit**|Führt minimale C-Bibliotheksbeendigungsprozeduren aus und kehrt zum Aufrufer zurück. Der Prozess wird nicht beendet.|

Beim Aufrufen der **beenden**, **_Exit** oder **_exit** -Funktion, die Destruktoren für alle temporären oder automatischen Objekte, die zum Zeitpunkt des Aufrufs vorhanden sind, werden nicht aufgerufen. Ein automatisches Objekt wird ein nicht statisches lokales Objekt in einer Funktion definiert. Ein temporäres Objekt ist ein Objekt, das durch den Compiler, z. B. einen durch einen Funktionsaufruf zurückgegebenen Wert erstellt wird. Um ein automatisches Objekt zu zerstören, bevor Sie rufen **beenden**, **_Exit**, oder **_exit**explizit den Destruktor für das Objekt aufrufen, wie hier gezeigt:

```cpp
void last_fn() {}
    struct SomeClass {} myInstance{};
    // ...
    myInstance.~SomeClass(); // explicit destructor call
    exit(0);
}
```

Verwenden Sie keine **DLL_PROCESS_ATTACH** Aufrufen **beenden** aus **DllMain**. Zum Beenden der **DLLMain** funktionieren, zurückgeben **"false"** aus **DLL_PROCESS_ATTACH**.

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|
|--------------|---------------------|
|**Beenden Sie**, **_Exit**, **_exit**|\<process.h> oder\<stdlib.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_exit.c
// This program returns an exit code of 1. The
// error code could be tested in a batch file.

#include <stdlib.h>

int main( void )
{
   exit( 1 );
}
```

## <a name="see-also"></a>Siehe auch

[Prozess- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)<br/>
[abort](abort.md)<br/>
[atexit](atexit.md)<br/>
[_cexit, _c_exit](cexit-c-exit.md)<br/>
[_exec- und _wexec-Funktionen](../../c-runtime-library/exec-wexec-functions.md)<br/>
[_onexit, _onexit_m](onexit-onexit-m.md)<br/>
[quick_exit](quick-exit1.md)<br/>
[_spawn-, _wspawn-Funktionen](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>

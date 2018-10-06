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
ms.openlocfilehash: eb5bd1ef619c899a6b0faab33104a579fdb9f1d0
ms.sourcegitcommit: a738519aa491a493a8f213971354356c0e6a5f3a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/05/2018
ms.locfileid: "48821273"
---
# <a name="exit-exit-exit"></a>exit, _Exit, _exit

Beendet den aufrufenden Prozess. Die **beenden** Funktion beendet ihn nach der Bereinigung; **_exit** und **_Exit** beenden ihn sofort.

> [!NOTE]
> Verwenden Sie diese Methode nicht, eine app (Universelle Windows Plattform) mit Ausnahme von Herunterfahren in Test- oder Debugszenarien. Programmgesteuerte oder UI-Methoden zum Schließen einer Store-app sind nicht zulässig, gemäß der [Microsoft Store Richtlinien](/legal/windows/agreements/store-policies). Weitere Informationen finden Sie unter [UWP-App-Lebenszyklus](/windows/uwp/launch-resume/app-lifecycle). Weitere Informationen zu Windows 10-Apps finden Sie unter [Anleitungen für Windows 10-Apps](https://developer.microsoft.com/windows/apps).

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

*status*<br/>
Beendigungsstatuscode.

## <a name="remarks"></a>Hinweise

Die **beenden**, **_Exit** und **_exit** Funktionen beenden den aufrufenden Prozess. Die **beenden** Funktionsaufrufe Destruktoren für threadlokale Objekte und ruft dann – in der Reihenfolge von Last-in-First-Out (LIFO) – die Funktionen, die von registriert werden **von "atexit"** und **_onexit**, und klicken Sie dann alle Dateipuffer geleert, bevor der Prozess beendet wird. Die **_Exit** und **_exit** Funktionen wird der Prozess beendet, ohne threadlokale Objekte zu zerstören oder Verarbeitung **von "atexit"** oder **_onexit**-Funktionen und ohne den Streampuffer.

Obwohl die **beenden**, **_Exit** und **_exit** Aufrufe geben einen Wert, der Wert in nicht zurück *Status* an die hostumgebung zur Verfügung gestellt wird oder aufrufende Prozess wartet, wenn nach des Prozesses beenden vorhanden. In der Regel der Aufrufer legt den *Status* Wert auf 0 zum Kennzeichnen einer normalen Beendigung oder auf einen anderen Wert einen Fehler an. Die *Status* -Wert steht dem Betriebssystem-Batchbefehl **ERRORLEVEL** und wird durch eine der beiden Konstanten repräsentiert: **EXIT_SUCCESS**, der einen Wert darstellt von 0 (null) oder **EXIT_FAILURE**, der einen Wert von 1 darstellt.

Die **beenden**, **_Exit**, **_exit**, **Quick_exit**, **_cexit**, und **_c_exit** Funktionen verhalten sich wie folgt.

|Funktion|Beschreibung|
|--------------|-----------------|
|**exit**|Führt vollständige C-Bibliotheksbeendigungsprozeduren aus, beendet den Prozess und übergibt den angegebenen Statuscode der Hostumgebung.|
|**_Exit**|Führt minimale C-Bibliotheksbeendigungsprozeduren aus, beendet den Prozess und übergibt den angegebenen Statuscode der Hostumgebung.|
|**_exit**|Führt minimale C-Bibliotheksbeendigungsprozeduren aus, beendet den Prozess und übergibt den angegebenen Statuscode der Hostumgebung.|
|**quick_exit**|Führt schnelle C-Bibliotheksbeendigungsprozeduren aus, beendet den Prozess und übergibt den angegebenen Statuscode der Hostumgebung.|
|**_cexit**|Führt vollständige C-Bibliotheksbeendigungsprozeduren aus und kehrt zum Aufrufer zurück. Der Prozess wird nicht beendet.|
|**_c_exit**|Führt minimale C-Bibliotheksbeendigungsprozeduren aus und kehrt zum Aufrufer zurück. Der Prozess wird nicht beendet.|

Beim Aufrufen der **beenden**, **_Exit** oder **_exit** -Funktion, die Destruktoren für jedes zum Zeitpunkt des Aufrufs vorhandene temporäre oder automatische Objekt nicht aufgerufen. Ein automatisches Objekt ist ein lokales nichtstatischen-Objekt in einer Funktion definiert. Ein temporäres Objekt ist ein Objekt, das durch den Compiler an, wie z. B. einen durch einen Funktionsaufruf zurückgegebenen Wert erstellt wird. Zum Zerstören eines automatischen Objekts vor dem Aufruf **beenden**, **_Exit**, oder **_exit**explizit rufen Sie den Destruktor für das Objekt an, wie hier gezeigt:

```cpp
void last_fn() {}
    struct SomeClass {} myInstance{};
    // ...
    myInstance.~SomeClass(); // explicit destructor call
    exit(0);
}
```

Verwenden Sie keine **DLL_PROCESS_ATTACH** aufzurufende **beenden** aus **DllMain**. Zum Beenden der **DLLMain** funktionieren, zurückgeben **"false"** aus **DLL_PROCESS_ATTACH**.

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

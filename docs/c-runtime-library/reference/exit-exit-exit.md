---
title: exit, _Exit, _exit | Microsoft-Dokumentation
ms.custom: 
ms.date: 1/02/2018
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
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
dev_langs: C++
helpviewer_keywords:
- exit function
- _exit function
- processes, terminating
- function calls, terminating
- process termination, calling
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: dbb54b756363da2069bbc4bface4e971fcab91e4
ms.sourcegitcommit: a5d8f5b92cb5e984d5d6c9d67fe8a1241f3fe184
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/05/2018
---
# <a name="exit-exit-exit"></a>exit, _Exit, _exit

Beendet den aufrufenden Prozess. Die Funktion `exit` beendet ihn nach der Bereinigung; `_exit` und `_Exit` beenden ihn sofort.

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

_status_  
Beendigungsstatuscode.

## <a name="remarks"></a>Hinweise

Die Funktionen `exit`, `_Exit` und `_exit` beenden den aufrufenden Prozess. Die Funktion `exit` ruft Destruktoren für threadlokale Objekte und anschließend – in LIFO-Reihenfolge (Last In First Out) – die Funktionen auf, die von `atexit` und `_onexit`registriert wurden; schließlich werden alle Puffer geleert, bevor der Prozess beendet wird. Die Funktionen `_Exit` und `_exit` beenden den Prozess, ohne threadlokale Objekte zu zerstören oder die Funktionen `atexit` oder `_onexit` zu verarbeiten, und ohne die Datenstrompuffer zu leeren.

Obwohl die `exit`, `_Exit` und `_exit` Aufrufe geben einen Wert, der Wert in nicht zurück _Status_ zur Verfügung gestellt wird der hostumgebung oder wartenden aufrufenden Prozess, falls vorhanden, nachdem der Prozess beendet wird,. In der Regel der Aufrufer legt den _Status_ Wert zur kennzeichnen einer normalen Beendigung auf 0 oder auf einen anderen Wert einen Fehler an. Die _Status_ -Wert steht dem Betriebssystem-Batchbefehl `ERRORLEVEL` und wird durch eine der beiden Konstanten repräsentiert: `EXIT_SUCCESS`, die einen Wert von 0 (null) darstellt oder `EXIT_FAILURE`, die einen Wert von 1 darstellt.

Die Funktionen `exit`, `_Exit`, `_exit`, `quick_exit`, `_cexit`und `_c_exit` verhalten sich wie folgt.

|Funktion|Beschreibung|
|--------------|-----------------|
|`exit`|Führt vollständige C-Bibliotheksbeendigungsprozeduren aus, beendet den Prozess und übergibt den angegebenen Statuscode der Hostumgebung.|
|`_Exit`|Führt minimale C-Bibliotheksbeendigungsprozeduren aus, beendet den Prozess und übergibt den angegebenen Statuscode der Hostumgebung.|
|`_exit`|Führt minimale C-Bibliotheksbeendigungsprozeduren aus, beendet den Prozess und übergibt den angegebenen Statuscode der Hostumgebung.|
|`quick_exit`|Führt schnelle C-Bibliotheksbeendigungsprozeduren aus, beendet den Prozess und übergibt den angegebenen Statuscode der Hostumgebung.|
|`_cexit`|Führt vollständige C-Bibliotheksbeendigungsprozeduren aus und kehrt zum Aufrufer zurück. Der Prozess wird nicht beendet.|
|`_c_exit`|Führt minimale C-Bibliotheksbeendigungsprozeduren aus und kehrt zum Aufrufer zurück. Der Prozess wird nicht beendet.|

Beim Aufruf der Funktion `exit`,  `_Exit` oder `_exit` werden die Destruktoren für jedes zum Zeitpunkt des Aufrufs vorhandene temporäre oder automatische Objekt nicht aufgerufen. Ein automatisches Objekt wird ein nicht statisches lokales Objekt in einer Funktion definiert. Ein temporäres Objekt ist ein Objekt, das durch den Compiler, z. B. einen durch einen Funktionsaufruf zurückgegebenen Wert erstellt wird. Um ein automatisches Objekt zu zerstören, bevor Sie rufen `exit`, `_Exit`, oder `_exit`explizit den Destruktor für das Objekt aufrufen, wie hier gezeigt:

```cpp
void last_fn() {}
    struct SomeClass {} myInstance{};
    // ...
    myInstance.~SomeClass(); // explicit destructor call
    exit(0);
}
```

Verwenden Sie nicht `DLL_PROCESS_ATTACH` , um `exit` aus `DllMain`aufzurufen. Zum Beenden der `DLLMain` funktionieren, zurückgeben `FALSE` aus `DLL_PROCESS_ATTACH`.

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|
|--------------|---------------------|
|`exit`, `_Exit`, `_exit`|\<process.h> oder \<stdlib.h>|

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

[Prozess- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)  
[abort](../../c-runtime-library/reference/abort.md)  
[atexit](../../c-runtime-library/reference/atexit.md)  
[_cexit, _c_exit](../../c-runtime-library/reference/cexit-c-exit.md)  
[_exec- und _wexec-Funktionen](../../c-runtime-library/exec-wexec-functions.md)  
[_onexit, _onexit_m](../../c-runtime-library/reference/onexit-onexit-m.md)  
[quick_exit](../../c-runtime-library/reference/quick-exit1.md)  
[_spawn-, _wspawn-Funktionen](../../c-runtime-library/spawn-wspawn-functions.md)  
[system, _wsystem](../../c-runtime-library/reference/system-wsystem.md)  

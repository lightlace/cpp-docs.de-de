---
title: _cexit, _c_exit
ms.date: 11/04/2016
apiname:
- _c_exit
- _cexit
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
- _cexit
- c_exit
- _c_exit
- cexit
helpviewer_keywords:
- cleanup operations during processes
- cexit function
- _c_exit function
- _cexit function
- c_exit function
ms.assetid: f3072045-9924-4b1a-9fef-b0dcd6d12663
ms.openlocfilehash: a075e8a8e965a195765b86ffa21fed0915dbf5ab
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62335489"
---
# <a name="cexit-cexit"></a>_cexit, _c_exit

Führt Bereinigungsvorgänge aus und kehrt zurück, ohne dass der Prozess beendet wird.

## <a name="syntax"></a>Syntax

```C
void _cexit( void );
void _c_exit( void );
```

## <a name="remarks"></a>Hinweise

Die **_cexit** Funktionsaufrufe, in der Last in, First Out (LIFO)-Auftrag, indem registrierten Funktionen **von "atexit"** und **_onexit**. Klicken Sie dann **_cexit** alle e/a-Puffer leert und schließt alle geöffneten Streams vor dem zurückgeben. **_c_exit** ist identisch mit **_exit** jedoch an den aufrufenden Prozess ohne Verarbeitung zurückgegeben **von "atexit"** oder **_onexit** oder Streampuffer zu leeren. Das Verhalten der **beenden**, **_exit**, **_cexit**, und **_c_exit** wird in der folgenden Tabelle dargestellt.

|Funktion|Verhalten|
|--------------|--------------|
|**exit**|Führt vollständige C-Bibliotheksbeendigungsprozeduren aus, beendet den Prozess und beendet mit dem angegebenen Statuscode.|
|**_exit**|Führt schnelle C-Bibliotheksbeendigungsprozeduren aus, beendet den Prozess und beendet mit dem angegebenen Statuscode.|
|**_cexit**|Führt vollständige C-Bibliotheksbeendigungsprozeduren aus und kehrt zum Aufrufer zurück, beendet jedoch nicht den Prozess.|
|**_c_exit**|Führt schnelle C-Bibliotheksbeendigungsprozeduren aus und kehrt zum Aufrufer zurück, beendet jedoch nicht den Prozess.|

Beim Aufrufen der **_cexit** oder **_c_exit** Funktionen, die Destruktoren für jedes zum Zeitpunkt des Aufrufs vorhandene temporäre oder automatische Objekt nicht aufgerufen. Ein automatisches Objekt ist ein Objekt, das in einer Funktion definiert wird, in der das Objekt nicht als statisch deklariert ist. Ein temporäres Objekt ist ein Objekt, das vom Compiler erstellt wird. Zum Zerstören eines automatischen Objekts vor dem Aufruf **_cexit** oder **_c_exit**explizit den Destruktor für das Objekt wie folgt aufrufen:

```cpp
myObject.myClass::~myClass( );
```

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_cexit**|\<process.h>|
|**_c_exit**|\<process.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Prozess- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)<br/>
[abort](abort.md)<br/>
[atexit](atexit.md)<br/>
[_exec- und _wexec-Funktionen](../../c-runtime-library/exec-wexec-functions.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[_onexit, _onexit_m](onexit-onexit-m.md)<br/>
[_spawn-, _wspawn-Funktionen](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>

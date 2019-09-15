---
title: _cexit, _c_exit
ms.date: 11/04/2016
api_name:
- _c_exit
- _cexit
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: aa25d73bef1d85adfed77ba926e2d381e02e45e8
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70939253"
---
# <a name="_cexit-_c_exit"></a>_cexit, _c_exit

Führt Bereinigungsvorgänge aus und kehrt zurück, ohne dass der Prozess beendet wird.

## <a name="syntax"></a>Syntax

```C
void _cexit( void );
void _c_exit( void );
```

## <a name="remarks"></a>Hinweise

Die **_cexit** -Funktion ruft in der LIFO-Reihenfolge (Last in, First Out) die von **atexit** und **_onexit**registrierten Funktionen auf. Dann **_cexit** Leert alle e/a-Puffer und schließt alle geöffneten Streams vor der Rückgabe. **_c_exit** entspricht **_exit** , aber kehrt zum aufrufenden Prozess zurück, ohne **atexit** oder **_onexit** zu verarbeiten oder Streampuffer zu leeren. Das Verhalten von **Exit**, **_exit**, **_cexit**und **_c_exit** ist in der folgenden Tabelle dargestellt.

|Funktion|Verhalten|
|--------------|--------------|
|**exit**|Führt vollständige C-Bibliotheksbeendigungsprozeduren aus, beendet den Prozess und beendet mit dem angegebenen Statuscode.|
|**_exit**|Führt schnelle C-Bibliotheksbeendigungsprozeduren aus, beendet den Prozess und beendet mit dem angegebenen Statuscode.|
|**_cexit**|Führt vollständige C-Bibliotheksbeendigungsprozeduren aus und kehrt zum Aufrufer zurück, beendet jedoch nicht den Prozess.|
|**_c_exit**|Führt schnelle C-Bibliotheksbeendigungsprozeduren aus und kehrt zum Aufrufer zurück, beendet jedoch nicht den Prozess.|

Wenn Sie die **_cexit** -Funktion oder die **_c_exit** -Funktion aufrufen, werden die debugtoren für alle temporären oder automatischen Objekte, die zum Zeitpunkt des Aufrufs vorhanden sind, nicht aufgerufen. Ein automatisches Objekt ist ein Objekt, das in einer Funktion definiert wird, in der das Objekt nicht als statisch deklariert ist. Ein temporäres Objekt ist ein Objekt, das vom Compiler erstellt wird. Um ein automatisches Objekt vor dem Aufrufen von **_cexit** oder **_c_exit**zu zerstören, rufen Sie den Dekonstruktor für das Objekt explizit wie folgt auf:

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

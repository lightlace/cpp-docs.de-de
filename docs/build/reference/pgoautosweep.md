---
title: "\"PgoAutoSweep\""
ms.date: 03/14/2018
f1_keywords:
- PgoAutoSweep
- PogoAutoSweepA
- PogoAutoSweepW
ms.openlocfilehash: 356504da91a6778b5e873ca218df01944461d59c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50456640"
---
# <a name="pgoautosweep"></a>"PgoAutoSweep"

`PgoAutoSweep` Speichert die aktuellen Profilinformationen Indikator in einer Datei, und klicken Sie dann den Zähler zurückgesetzt. Verwenden Sie die Funktion während der profilgesteuerten Optimierung, Schulungen, die alle Profildaten aus das aktive Programm in eine PGC-Datei zur späteren Verwendung in den Build für die Optimierung zu schreiben.

## <a name="syntax"></a>Syntax

```cpp
void PgoAutoSweep(const char* name);    // ANSI/MBCS
void PgoAutoSweep(const wchar_t* name); // UNICODE
```

### <a name="parameters"></a>Parameter

*name*<br/>
Eine identifizierende Zeichenfolge für die gespeicherten PGC-Datei.

## <a name="remarks"></a>Hinweise

Rufen Sie `PgoAutoSweep` aus Ihrer Anwendung zu speichern, die Profildaten zu einem beliebigen Zeitpunkt während der anwendungsausführung zurücksetzen. In einem instrumentierten Build `PgoAutoSweep` erfasst die aktuellen Daten für die profilerstellung, speichert es in einer Datei und die Profil-Zähler zurückgesetzt. Dies entspricht dem Aufruf der [Pgosweep](pgosweep.md) Befehl zu einem bestimmten Zeitpunkt in der ausführbaren Datei. In einem optimierten Build `PgoAutoSweep` ist keine Aktion.

Die gespeicherten Profildaten für den Leistungsindikator befindet sich in einer Datei namens *Base_name*-*Namen*! *Wert*.pgc, in denen *Base_name* ist der Basisname der ausführbaren Datei, *Namen* ist der an übergebene Parameter `PgoAutoSweep`, und *Wert* ist ein eindeutiger Wert, in der Regel eine monoton steigende Zahl, um Datei Namenskonflikte zu verhindern.

Die PGC-Dateien, die von erstellten `PgoAutoSweep` müssen zusammengeführt werden, in einer PGD-Datei verwendet werden, um eine optimierte ausführbare Datei zu erstellen. Sie können die ["pgomgr"](pgomgr.md) Befehl aus, um die Zusammenführung ausführen.

Sie können den Namen der zusammengeführte PGD-Datei während des Builds für die Optimierung für dem Linker übergeben, mit der **PGD =**_Filename_ Argument für die [/USERPROFILE angegeben](useprofile.md) -Linkeroption, oder mit der veralteten **/PGD** -Linkeroption. Wenn Sie in eine Datei mit dem Namen der PGC-Dateien zusammenführen *Base_name*PGD, Sie müssen nicht auf den Dateinamen in der Befehlszeile angeben, da der Dateiname der Linker standardmäßig übernimmt.

Die `PgoAutoSweep` Funktion verwaltet die Threadsicherheit-Einstellung angegeben, wenn das instrumentierte Build erstellt wird. Wenn Sie die Standardeinstellung verwenden, oder geben Sie die **NOEXACT** Argument für die [/genprofile oder/fastgenprofile]() -Linkeroption, Aufrufe von `PgoAutoSweep` sind nicht threadsicher. Die **EXACT** Argument erstellt eine Thread-sicher und genauere, aber langsamer, instrumentierte ausführbare Datei.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|`PgoAutoSweep`|\<pgobootrun.h>|

Die ausführbare Datei muss die Datei "pgobootrun.lib" herstellen in den verknüpften Bibliotheken enthalten. Diese Datei ist in Visual Studio-Installation, in das Verzeichnis des VC++-Bibliotheken für jede unterstützte Architektur enthalten.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird `PgoAutoSweep` zwei. PGC-Dateien zu unterschiedlichen Zeitpunkten während der Ausführung. Die erste enthält Daten, die das Laufzeitverhalten bis beschreiben `count` ist gleich 3 ist, und die zweite enthält die Daten, die nach diesem Punkt erst kurz vor Beendigung der Anwendung gesammelt.

```cpp
// pgoautosweep.cpp
// Compile by using: cl /c /GL /W4 /EHsc /O2 pgoautosweep.cpp
// Link to instrument: link /LTCG /genprofile pgobootrun.lib pgoautosweep.obj
// Run to generate data: pgoautosweep
// Merge data by using command line pgomgr tool:
// pgomgr /merge pgoautosweep-func1!1.pgc pgoautosweep-func2!1.pgc pgoautosweep.pgd
// Link to optimize: link /LTCG /useprofile pgobootrun.lib pgoautosweep.obj

#include <iostream>
#include <windows.h>
#include <pgobootrun.h>

void func2(int count)
{
    std::cout << "hello from func2 " << count << std::endl;
    Sleep(2000);
}

void func1(int count)
{
    std::cout << "hello from func1 " << count << std::endl;
    Sleep(2000);
}

int main()
{
    int count = 10;
    while (count--)
    {
        if (count < 3)
            func2(count);
        else
        {
            func1(count);
            if (count == 3)
            {
                PgoAutoSweep("func1");
            }
        }
    }
    PgoAutoSweep("func2");
}
```

Kompilieren Sie in einer Developer-Eingabeaufforderung den Code in eine Objektdatei mit diesem Befehl:

`cl /c /GL /W4 /EHsc /O2 pgoautosweep.cpp`

Generieren Sie dann einen instrumentierten Build für das Training, indem Sie mithilfe des folgenden Befehls:

`link /LTCG /genprofile pgobootrun.lib pgoautosweep.obj`

Führen Sie die instrumentierte ausführbare Datei, um die Trainingsdaten zu erfassen. Die Ausgabe durch die Aufrufe `PgoAutoSweep` wird gespeichert, in Dateien, die mit dem Namen "PgoAutoSweep"-func1! 1.pgc und "PgoAutoSweep"-func2! 1.pgc. Die Ausgabe des Programms sollte wie folgt aussehen, während der Ausführung:

```Output
hello from func1 9
hello from func1 8
hello from func1 7
hello from func1 6
hello from func1 5
hello from func1 4
hello from func1 3
hello from func2 2
hello from func2 1
hello from func2 0
```

Die gespeicherten Daten in einer Schulung Profildatenbank zusammenführen, durch Ausführen der **"pgomgr"** Befehl:

`pgoautosweep-func1!1.pgc pgoautosweep-func2!1.pgc`

Die Ausgabe dieses Befehls sieht etwa folgendermaßen aus:

```Output
Microsoft (R) Profile Guided Optimization Manager 14.13.26128.0
Copyright (C) Microsoft Corporation. All rights reserved.

Merging pgoautosweep-func1!1.pgc
pgoautosweep-func1!1.pgc: Used  3.8% (22304 / 589824) of total space reserved.  0.0% of the counts were dropped due to overflow.
Merging pgoautosweep-func2!1.pgc
pgoautosweep-func2!1.pgc: Used  3.8% (22424 / 589824) of total space reserved.  0.0% of the counts were dropped due to overflow.
```

Jetzt können Sie diese Trainingsdaten zum Generieren von eines optimierten Builds aus. Verwenden Sie diesen Befehl, um die optimierte ausführbare Datei zu erstellen:

`link /LTCG /useprofile pgobootrun.lib pgoautosweep.obj`

```Output
Microsoft (R) Incremental Linker Version 14.13.26128.0
Copyright (C) Microsoft Corporation.  All rights reserved.

Merging pgoautosweep!1.pgc
pgoautosweep!1.pgc: Used  3.9% (22904 / 589824) of total space reserved.  0.0% of the counts were dropped due to overflow.
  Reading PGD file 1: pgoautosweep.pgd
Generating code

0 of 0 ( 0.0%) original invalid call sites were matched.
0 new call sites were added.
294 of 294 (100.00%) profiled functions will be compiled for speed
348 of 1239 inline instances were from dead/cold paths
294 of 294 functions (100.0%) were optimized using profile data
16870 of 16870 instructions (100.0%) were optimized using profile data
Finished generating code
```

## <a name="see-also"></a>Siehe auch

[Profilgesteuerte Optimierungen](profile-guided-optimizations.md)<br/>
[pgosweep](pgosweep.md)<br/>

---
title: PgoAutoSweep | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
f1_keywords:
- PgoAutoSweep
- PogoAutoSweepA
- PogoAutoSweepW
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 988a73dd8c4ad6929ef04691ad1959df7ea7bdd7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379496"
---
# <a name="pgoautosweep"></a>PgoAutoSweep

`PgoAutoSweep` Speichert das aktuelle Profil Indikatorinformationen in einer Datei, und klicken Sie dann die Zähler zurückgesetzt. Verwenden Sie die Funktion während der profilgesteuerten Optimierung Schulungen für alle Profildaten aus der ausgeführten Anwendung in eine PGC-Datei zur späteren Verwendung in der Optimierung Build zu schreiben.

## <a name="syntax"></a>Syntax

```cpp
void PgoAutoSweep(const char* name);    // ANSI/MBCS
void PgoAutoSweep(const wchar_t* name); // UNICODE
```

### <a name="parameters"></a>Parameter

*name*<br/>
Eine identifizierende Zeichenfolge für die gespeicherten PGC-Datei.

## <a name="remarks"></a>Hinweise

Sie können Aufrufen `PgoAutoSweep` aus Ihrer Anwendung zu speichern, die Profildaten zu einem beliebigen Zeitpunkt während der Ausführung der Anwendung zurückgesetzt. In einen instrumentierten Build `PgoAutoSweep` aktuelle Profilerstellungsdaten erfasst, speichert es in einer Datei und die Profil-Zähler zurückgesetzt. Es ist das Äquivalent eines Aufrufs der [Pgosweep](pgosweep.md) Befehl zu einem bestimmten Zeitpunkt in der ausführbaren Datei. In einem optimierten Build `PgoAutoSweep` ist nicht möglich.

Die gespeicherten Profildaten für den Leistungsindikator befindet sich in einer Datei namens *Base_name*-*Namen*! *Wert*PGC, in denen *Base_name* ist der Basisname der ausführbaren Datei, *Namen* wird an der Parameter übergeben `PgoAutoSweep`, und *Wert* ist ein eindeutiger Wert, in der Regel eine monoton steigende Zahl, um Datei Namenskonflikte zu verhindern.

Die PGC-Dateien erstellt, indem `PgoAutoSweep` PGD-Datei verwendet werden soll, erstellen Sie eine optimierte ausführbare Datei zusammengeführt werden muss. Sie können die [Pgomgr](pgomgr.md) Befehl aus, um die Zusammenführung auszuführen.

Sie können den Namen der zusammengeführten PGD-Datei während der Builderstellung Optimierung an dem Linker übergeben, indem die **PGD =**_Filename_ Argument an die [/useprofile](useprofile.md) (Linkeroption), oder durch Mithilfe des veralteten **/PGD** (Linkeroption). Wenn Sie die PGC-Dateien in eine Datei mit dem Namen merge *Base_name*PGD, Sie müssen nicht den Dateinamen in der Befehlszeile angeben, da der Dateiname der Linker standardmäßig übernimmt.

Die `PgoAutoSweep` Funktion verwaltet die Threadsicherheit Einstellung angegeben, wenn das instrumentierte Build erstellt wird. Wenn Sie die Standardeinstellung verwenden, oder geben Sie die **NOEXACT** Argument an die [/genprofile oder/fastgenprofile]() Linkeroption, Aufrufe von `PgoAutoSweep` sind nicht threadsicher. Die **EXACT** Argument erstellt, eine threadsichere und genauere, aber verlangsamt, instrumentierte ausführbare Datei.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|`PgoAutoSweep`|\<pgobootrun.h>|

Die ausführbare Datei muss die pgobootrun.lib-Datei in den verknüpften Bibliotheken enthalten. Diese Datei ist in Visual Studio-Installation, in das Verzeichnis des VC-Bibliotheken für jede unterstützte Architektur enthalten.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird `PgoAutoSweep` zwei erstellen. PGC-Dateien zu unterschiedlichen Zeitpunkten während der Ausführung. Die erste Zeile enthält Daten, die das Laufzeitverhalten bis beschreiben `count` gleich 3, und das zweite enthält die Daten nach diesem Zeitpunkt erst kurz vor Beendigung der Anwendung gesammelt.

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

Kompilieren Sie in einem Developer-Eingabeaufforderung den Code eine Objektdatei mit diesem Befehl ein:

`cl /c /GL /W4 /EHsc /O2 pgoautosweep.cpp`

Anschließend erstellen Sie einen instrumentierten Build für das Training mit diesem Befehl:

`link /LTCG /genprofile pgobootrun.lib pgoautosweep.obj`

Führen Sie die instrumentierte ausführbare Datei, um die Trainingsdaten zu erfassen. Von den Aufrufen an die Datenausgabe `PgoAutoSweep` wird gespeichert, in Dateien mit dem Namen Pgoautosweep func1! 1.pgc und Pgoautosweep func2! 1.pgc. Während diese ausgeführt wird, sollte die Ausgabe des Programms wie folgt aussehen:

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

Ein Profil Trainingsdatenbank durch Ausführen die gespeicherten Daten Zusammenführen der **Pgomgr** Befehl:

`pgoautosweep-func1!1.pgc pgoautosweep-func2!1.pgc`

Die Ausgabe dieses Befehls sieht etwa wie folgt:

```Output
Microsoft (R) Profile Guided Optimization Manager 14.13.26128.0
Copyright (C) Microsoft Corporation. All rights reserved.

Merging pgoautosweep-func1!1.pgc
pgoautosweep-func1!1.pgc: Used  3.8% (22304 / 589824) of total space reserved.  0.0% of the counts were dropped due to overflow.
Merging pgoautosweep-func2!1.pgc
pgoautosweep-func2!1.pgc: Used  3.8% (22424 / 589824) of total space reserved.  0.0% of the counts were dropped due to overflow.
```

Jetzt können Sie diese Trainingsdaten, einen optimierten Build generiert. Verwenden Sie diesen Befehl, um die optimierte ausführbare Datei zu erstellen:

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

---
title: Umgebungsvariablen für Profilgesteuerte Optimierungen | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- profile-guided optimizations, environment variables
ms.assetid: f95a6d1e-49a4-4802-a144-092026b600a3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 19edc9c8a2702e5b7ac9ae4a49364718f19d3900
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379444"
---
# <a name="environment-variables-for-profile-guided-optimizations"></a>Umgebungsvariablen für profilgesteuerte Optimierungen

Es gibt drei Umgebungsvariablen, die Testszenarien auf ein Bild mit erstellt betreffen **/LTCG: PGI** für Profilgesteuerte Optimierungen:

- **PogoSafeMode** gibt an, ob schnelle oder abgesicherte Modus zur anwendungsprofilerstellung verwendet.

- **VCPROFILE_ALLOC_SCALE** fügt zusätzlichen Arbeitsspeicher für die Verwendung durch den Profiler.

- **VCPROFILE_PATH** können Sie den Ordner für PGC-Dateien angeben.

**Die Umgebungsvariablen PogoSafeMode und VCPROFILE_ALLOC_SCALE sind in Visual Studio 2015 ab veraltet.** Die Optionen des Linkers [/genprofile oder/fastgenprofile](genprofile-fastgenprofile-generate-profiling-instrumented-build.md) und [/useprofile](useprofile.md) das gleiche Verhalten für den Linker als diese Umgebungsvariablen angeben.

## <a name="pogosafemode"></a>PogoSafeMode

Diese Umgebungsvariable ist veraltet. Verwenden der **EXACT** oder **NOEXACT** Argumente **/genprofile** oder **/fastgenprofile** auf dieses Verhalten zu steuern.

Deaktivieren oder Festlegen der **PogoSafeMode** Umgebungsvariable, um anzugeben, ob schnelle oder abgesicherte Modus zur anwendungsprofilerstellung auf X86 verwenden Systeme.

Profilgesteuerte Optimierung (PGO) besitzt zwei mögliche Modi während der Profilerstellungsphase: *schnellen Modus* und *im abgesicherten Modus*. Wenn die profilerstellung im schnellen Modus stattfindet, verwendet der **INC** Anweisung, um Leistungsindikatoren zu erhöhen. Die **INC** -Anweisung ist schneller, jedoch nicht threadsicher. Wenn die profilerstellung im abgesicherten Modus stattfindet, verwendet der **SPERRE INC** Anweisung, um Leistungsindikatoren zu erhöhen. Die **SPERRE INC** -Anweisung besitzt die gleiche Funktionalität wie die **INC** -Anweisung und ist threadsicher, dabei jedoch langsamer als die **INC** Anweisung.

Standardmäßig wird PGO-Profilerstellung im schnellen Modus ausgeführt. **PogoSafeMode** ist nur erforderlich, wenn Sie den abgesicherten Modus verwenden möchten.

Um PGO-profilerstellung im abgesicherten Modus auszuführen, müssen Sie entweder die Umgebungsvariable verwenden **PogoSafeMode** oder den Linkerschalter **/PogoSafeMode**, je nachdem, auf dem System. Wenn Sie die Profilerstellung auf einem x64-Computer ausführen, müssen Sie den Linkerschalter verwenden. Wenn Sie die profilerstellung auf x X86 ausführen-Computer können den Linker wechseln, oder legen Sie die **PogoSafeMode** -Umgebungsvariable auf einen beliebigen Wert, bevor Sie den Optimierungsprozess zu starten.

### <a name="pogosafemode-syntax"></a>PogoSafeMode-syntax

> **Legen Sie PogoSafeMode**[**=**_Wert_]

Legen Sie **PogoSafeMode** auf einen beliebigen Wert im abgesicherten Modus zu aktivieren. Legen Sie keinen Wert auf einen früheren Wert deaktivieren und reaktivieren schnellen Modus.

## <a name="vcprofileallocscale"></a>VCPROFILE_ALLOC_SCALE

Diese Umgebungsvariable ist veraltet. Verwenden der **MEMMIN** und **MEMMAX** Argumente **/genprofile** oder **/fastgenprofile** auf dieses Verhalten zu steuern.

Ändern der **VCPROFILE_ALLOC_SCALE** -Umgebungsvariable so ändern Sie die Größe des Arbeitsspeichers, die die Profildaten enthält zugeordnet. In seltenen Fällen kann es werden genügend Arbeitsspeicher zur Unterstützung beim Ausführen des Testszenarios Profil Datensammlung. In diesen Fällen können Sie die Menge an Arbeitsspeicher erhöhen, indem **VCPROFILE_ALLOC_SCALE**. Wenn Sie während eines Testlaufs eine Fehlermeldung, der angibt erhalten, dass Sie nicht genügend Arbeitsspeicher verfügen, weisen Sie einen höheren Wert zu **VCPROFILE_ALLOC_SCALE**, bis der Test abgeschlossen, ohne Out-of-Memory-Fehler ausgeführt wird.

### <a name="vcprofileallocscale-syntax"></a>VCPROFILE_ALLOC_SCALE-syntax

> **Legen Sie VCPROFILE_ALLOC_SCALE**[__=__*Scale_value*]

Die *Scale_value* Parameter ist ein Skalierungsfaktor für die Menge an Arbeitsspeicher zum Ausführen des Testszenarios werden sollen.  Der Standard ist 1. Beispielsweise legt diese über die Befehlszeile den Skalierungsfaktor auf 2:

`set VCPROFILE_ALLOC_SCALE=2`

## <a name="vcprofilepath"></a>VCPROFILE_PATH

Verwenden der **VCPROFILE_PATH** -Umgebungsvariable das Verzeichnis zum Erstellen von PGC-Dateien angeben. Standardmäßig werden PGC-Dateien im selben Verzeichnis wie die Binärdatei profilierten erstellt. Wenn der absolute Pfad der Binärdatei nicht vorhanden ist wie die Groß-/Kleinschreibung möglicherweise beim Ausführen von Profilszenarien auf einem anderen Computer aus, in denen die Binärdatei erstellt wurde, Sie können jedoch festlegen **VCPROFILE_PATH** auf einen Pfad, der auf dem Zielcomputer vorhanden ist.

### <a name="vcprofilepath-syntax"></a>VCPROFILE_PATH-syntax

> **Legen Sie VCPROFILE_PATH**[**=**_Pfad_]

Legen Sie die *Pfad* Parameter in das Verzeichnis in der PGC-Dateien hinzugefügt. Mit dieser Befehlszeile wird z. B. den Ordner, auf C:\profile:

`set VCPROFILE_PATH=c:\profile`

## <a name="see-also"></a>Siehe auch

[Profilgesteuerte Optimierungen](../../build/reference/profile-guided-optimizations.md)<br/>
[/ GENPROFILE und/fastgenprofile](genprofile-fastgenprofile-generate-profiling-instrumented-build.md)<br/>
[/ USEPROFILE](useprofile.md)<br/>

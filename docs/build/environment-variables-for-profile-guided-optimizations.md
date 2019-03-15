---
title: Umgebungsvariablen für profilgesteuerte Optimierungen
ms.date: 03/14/2018
helpviewer_keywords:
- profile-guided optimizations, environment variables
ms.assetid: f95a6d1e-49a4-4802-a144-092026b600a3
ms.openlocfilehash: 099e57f1ac69223adafe7bec1af4cc3452915e86
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57825826"
---
# <a name="environment-variables-for-profile-guided-optimizations"></a>Umgebungsvariablen für profilgesteuerte Optimierungen

Es gibt drei Umgebungsvariablen, die Testszenarien, die auf einem Image erstellt, die mit Auswirkungen auf **/LTCG: PGI** für Profilgesteuerte Optimierungen:

- **PogoSafeMode** gibt an, ob schnelle oder abgesicherte Modus zur anwendungsprofilerstellung verwendet.

- **VCPROFILE_ALLOC_SCALE** fügt zusätzlichen Arbeitsspeicher für die Verwendung durch den Profiler.

- **VCPROFILE_PATH** können Sie den Ordner für PGC-Dateien angeben.

**Die Umgebungsvariablen PogoSafeMode und VCPROFILE_ALLOC_SCALE sind ab Visual Studio 2015 veraltet.** Die Optionen des Linkers [/genprofile oder/fastgenprofile](reference/genprofile-fastgenprofile-generate-profiling-instrumented-build.md) und [/USERPROFILE angegeben](reference/useprofile.md) Geben Sie das gleiche linkerverhalten, als diese Umgebungsvariablen.

## <a name="pogosafemode"></a>PogoSafeMode

Diese Umgebungsvariable ist veraltet. Verwenden der **EXACT** oder **NOEXACT** Argumente **/genprofile** oder **/fastgenprofile** zur Steuerung dieses Verhaltens.

Deaktivieren oder Festlegen der **PogoSafeMode** Umgebungsvariable, um anzugeben, ob schnelle oder abgesicherte Modus zu verwenden, für die anwendungsprofilerstellung auf X86 Systeme.

Profilgesteuerte Optimierung (PGO) besitzt zwei mögliche Modi während der Profilerstellungsphase: *schnellen Modus* und *im abgesicherten Modus*. Wenn die profilerstellung im schnellen Modus stattfindet, die sie verwendet die **INC** Anweisung, um Daten von Leistungsindikatoren zu erhöhen. Die **INC** Anweisung ist schneller, aber ist nicht threadsicher. Wenn die profilerstellung im abgesicherten Modus stattfindet, er verwendet den **SPERRE INC** Anweisung, um Daten von Leistungsindikatoren zu erhöhen. Die **SPERRE INC** Anweisung weist die gleiche Funktionalität wie die **INC** -Anweisung und ist threadsicher, aber es ist langsamer als die **INC** Anweisung.

Standardmäßig wird PGO-Profilerstellung im schnellen Modus ausgeführt. **PogoSafeMode** ist nur erforderlich, wenn Sie den abgesicherten Modus verwenden möchten.

Um PGO-profilerstellung im abgesicherten Modus auszuführen, müssen Sie entweder die Umgebungsvariable verwenden **PogoSafeMode** oder den Linkerschalter **/PogoSafeMode**, je nachdem, auf dem System. Wenn Sie die Profilerstellung auf einem x64-Computer ausführen, müssen Sie den Linkerschalter verwenden. Wenn Sie während der profilerstellung auf x X86 ausführen-Computer können Sie den Linker wechseln, oder legen Sie die **PogoSafeMode** -Umgebungsvariable auf einen beliebigen Wert aus, bevor Sie den Optimierungsprozess starten.

### <a name="pogosafemode-syntax"></a>PogoSafeMode-syntax

> **Legen Sie PogoSafeMode**[**=**_Wert_]

Legen Sie **PogoSafeMode** auf einen beliebigen Wert im abgesicherten Modus zu aktivieren. Legen Sie keinen Wert auf einen früheren Wert zu löschen und erneutes Aktivieren der schnelle Modus.

## <a name="vcprofileallocscale"></a>VCPROFILE_ALLOC_SCALE

Diese Umgebungsvariable ist veraltet. Verwenden der **MEMMIN** und **MEMMAX** Argumente **/genprofile** oder **/fastgenprofile** zur Steuerung dieses Verhaltens.

Ändern der **VCPROFILE_ALLOC_SCALE** -Umgebungsvariable so ändern Sie die Menge an Arbeitsspeicher zugewiesen wird, um die Profildaten enthält. In seltenen Fällen nicht mehr genügend Arbeitsspeicher verfügbar ist, zur Unterstützung bei der Ausführung von Testszenarien Profil Datensammlung. In diesen Fällen können Sie die Menge an Arbeitsspeicher erhöhen, indem Sie die Einstellung **VCPROFILE_ALLOC_SCALE**. Wenn Sie während eines Testlaufs, der angibt, dass Sie nicht genügend Arbeitsspeicher verfügen eine Fehlermeldung erhalten, weisen Sie einen höheren Wert zu **VCPROFILE_ALLOC_SCALE**, bis der Test abgeschlossen ist, ohne Out-of-Memory-Fehler ausgeführt wird.

### <a name="vcprofileallocscale-syntax"></a>VCPROFILE_ALLOC_SCALE-syntax

> **set VCPROFILE_ALLOC_SCALE**[__=__*scale_value*]

Die *Scale_value* -Parameter ist ein Skalierungsfaktor für die Menge an Arbeitsspeicher, die für die Ausführung von Testszenarien verwendet werden sollen.  Der Standard ist 1. Mit dieser Befehlszeile werden z. B. den Skalierungsfaktor auf 2 festgelegt:

`set VCPROFILE_ALLOC_SCALE=2`

## <a name="vcprofilepath"></a>VCPROFILE_PATH

Verwenden der **VCPROFILE_PATH** Umgebungsvariable das Verzeichnis zum Erstellen von PGC-Dateien angeben. Standardmäßig werden die PGC-Dateien im selben Verzeichnis wie die Binärdatei, profiliert werden erstellt. Wenn der absolute Pfad der Binärdatei nicht vorhanden ist, wie der Fall sein kann, beim Ausführen von Szenarien mit Profil auf einem anderen Computer aus, in dem das Binary erstellt wurde, Sie können jedoch festlegen **VCPROFILE_PATH** auf einen Pfad, der auf dem Zielcomputer vorhanden ist.

### <a name="vcprofilepath-syntax"></a>VCPROFILE_PATH-syntax

> **Legen Sie VCPROFILE_PATH**[**=**_Pfad_]

Legen Sie die *Pfad* Parameter, um den Verzeichnispfad, der PGC-Dateien hinzugefügt. Mit dieser Befehlszeile wird z. B. den Ordner, auf C:\profile:

`set VCPROFILE_PATH=c:\profile`

## <a name="see-also"></a>Siehe auch

[Profilgesteuerte Optimierungen](profile-guided-optimizations.md)<br/>
[/ GENPROFILE und/fastgenprofile](reference/genprofile-fastgenprofile-generate-profiling-instrumented-build.md)<br/>
[/USEPROFILE](reference/useprofile.md)<br/>

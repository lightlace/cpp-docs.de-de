---
title: / POGOSAFEMODE (PGO im abgesicherten Threadmodus ausgeführt) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
f1_keywords:
- POGOSAFEMODE
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 886fbae5fbeb7606ec0321595f061d2262988170
ms.sourcegitcommit: ee7d74683af7631441c8c7f65ef5ceceaee4a5ee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/22/2018
---
# <a name="pogosafemode-run-pgo-in-thread-safe-mode"></a>/ POGOSAFEMODE (PGO im abgesicherten Threadmodus ausgeführt)

**Die /POGOSAFEMODE-Option ist veraltet ab Visual Studio 2015**. Verwenden der [/genprofile: genaue](genprofile-fastgenprofile-generate-profiling-instrumented-build.md) und **/GENPROFILE:NOEXACT** Optionen stattdessen. Die **/POGOSAFEMODE** (Linkeroption) gibt an, dass das instrumentierte Build erstellt wird, um die Thread-sichere nutzen für Datenerfassung der Benutzerprofile während der profilgesteuerten Optimierung (PGO) trainieren ausgeführt wird.

## <a name="syntax"></a>Syntax

> **/POGOSAFEMODE**

## <a name="remarks"></a>Hinweise

Profilgesteuerte Optimierung (PGO) besitzt zwei mögliche Modi während der Profilerstellungsphase: *schnellen Modus* und *im abgesicherten Modus*. Profilerstellung im schnellen Modus stattfindet, wird eine Inkrement-Anweisung verwendet, werden Datenindikatoren erhöhen. Die Schrittweite-Anweisung ist schneller, aber es ist nicht threadsicher. Wenn die profilerstellung im abgesicherten Modus stattfindet, verwendet es die interlocked-Inkrement-Anweisung werden Datenindikatoren erhöhen. Diese Anweisung hat die gleiche Funktion wie das Inkrement-Anweisung und ist threadsicher, dabei jedoch langsamer.

Die **/POGOSAFEMODE** Option legt den instrumentierten Build im abgesicherten Modus verwenden. Diese Option kann nur verwendet werden, wenn die veralteten [/LTCG: PGINSTRUMENT](ltcg-link-time-code-generation.md) angegeben wird, während der Linkerphase der PGO-Instrumentation.

Standardmäßig wird PGO-Profilerstellung im schnellen Modus ausgeführt. **/ POGOSAFEMODE** ist nur erforderlich, wenn Sie den abgesicherten Modus verwenden möchten.

Um PGO-profilerstellung im abgesicherten Modus auszuführen, müssen Sie entweder verwenden **/genprofile: genaue** (bevorzugt) fest, oder verwenden Sie die Umgebungsvariable [PogoSafeMode](environment-variables-for-profile-guided-optimizations.md) oder den Linkerschalter **/POGOSAFEMODE**, je nachdem, auf dem System. Wenn Sie die Profilerstellung auf einem x64-Computer ausführen, müssen Sie den Linkerschalter verwenden. Wenn Sie die profilerstellung auf x X86 durchführen-Computer können Sie den Linkerschalter verwenden oder die Umgebungsvariable auf einen beliebigen Wert definieren, bevor die PGO-Instrumentation-Prozess zu starten.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **Linker** > **Optimierung** Eigenschaftenseite.

1. In der **Link-Time Code Generation** -Eigenschaft, wählen Sie **Profile Guided Optimization - Instrumentieren (/ LTCG: PGINSTRUMENT)**.

1. Wählen Sie die **Konfigurationseigenschaften** > **Linker** > **Befehlszeile** Eigenschaftenseite.

1. Geben Sie die **/POGOSAFEMODE** option in der **Zusatzoptionen** Feld. Wählen Sie **OK** zum Speichern der Änderungen.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[/ GENPROFILE und/fastgenprofile](genprofile-fastgenprofile-generate-profiling-instrumented-build.md)<br/>
[/LTCG](ltcg-link-time-code-generation.md)<br/>
[Profilgesteuerte Optimierungen](../../build/reference/profile-guided-optimizations.md)<br/>
[Umgebungsvariablen für profilgesteuerte Optimierungen](../../build/reference/environment-variables-for-profile-guided-optimizations.md)<br/>

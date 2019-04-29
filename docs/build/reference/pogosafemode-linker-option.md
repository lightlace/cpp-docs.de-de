---
title: / POGOSAFEMODE (PGO im abgesicherten Threadmodus ausgeführt)
ms.date: 03/14/2018
f1_keywords:
- POGOSAFEMODE
ms.openlocfilehash: bbb328bf67d7823305a43f1d61252747cf5ea29e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62319719"
---
# <a name="pogosafemode-run-pgo-in-thread-safe-mode"></a>/ POGOSAFEMODE (PGO im abgesicherten Threadmodus ausgeführt)

**Die /POGOSAFEMODE-Option ist ab Visual Studio 2015 veraltet**. Verwenden der [/genprofile: genaue](genprofile-fastgenprofile-generate-profiling-instrumented-build.md) und **/GENPROFILE:NOEXACT** stattdessen "Optionen". Die **/POGOSAFEMODE** (Linkeroption) gibt an, dass das instrumentierte Build erstellt wird, um threadsicheren Modus für die Datenerfassung Profil während der profilgesteuerten Optimierung (PGO) trainingsläufe zu verwenden.

## <a name="syntax"></a>Syntax

> **/POGOSAFEMODE**

## <a name="remarks"></a>Hinweise

Profilgesteuerte Optimierung (PGO) besitzt zwei mögliche Modi während der Profilerstellungsphase: *schnellen Modus* und *im abgesicherten Modus*. Bei der profilerstellung im schnellen Modus stattfindet, verwendet eine Anweisung Inkrement Datenindikatoren erhöhen. Die Schrittweite-Anweisung ist schneller, aber es ist nicht threadsicher. Wenn die profilerstellung im abgesicherten Modus stattfindet, wird die interlocked-Inkrement-Anweisung werden Datenindikatoren zu erhöhen. Diese Anweisung hat die gleiche Funktion wie die Inkrement-Anweisung und ist threadsicher, aber er langsamer als ist.

Die **/POGOSAFEMODE** Option wird das instrumentierte Build im abgesicherten Modus zu verwenden. Diese Option ist nur möglich verwendet werden, wenn die als veraltet markierten [/LTCG: PGINSTRUMENT](ltcg-link-time-code-generation.md) angegeben wird, während der Linkerphase der PGO-Instrumentation.

Standardmäßig wird PGO-Profilerstellung im schnellen Modus ausgeführt. **/ POGOSAFEMODE** ist nur erforderlich, wenn Sie den abgesicherten Modus verwenden möchten.

Um PGO-profilerstellung im abgesicherten Modus auszuführen, müssen Sie verwenden entweder **/genprofile: genaue** (bevorzugt), oder verwenden Sie die Umgebungsvariable [PogoSafeMode](../environment-variables-for-profile-guided-optimizations.md) oder den Linkerschalter **/POGOSAFEMODE**, je nachdem, auf dem System. Wenn Sie die Profilerstellung auf einem x64-Computer ausführen, müssen Sie den Linkerschalter verwenden. Wenn Sie während der profilerstellung auf x X86 ausführen-Computer können Sie den Linkerschalter verwenden oder die Umgebungsvariable auf einen beliebigen Wert definieren, bevor Sie beginnen, dass der Prozess der PGO-Instrumentation.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **Linker** > **Optimierung** Eigenschaftenseite.

1. In der **Link-Zeitcodegenerierung** Eigenschaft wählen **Profilgesteuerte Optimierung - Instrumentieren (/ LTCG: PGINSTRUMENT)**.

1. Wählen Sie die **Konfigurationseigenschaften** > **Linker** > **Befehlszeile** Eigenschaftenseite.

1. Geben Sie die **/POGOSAFEMODE** option in der **zusätzliche Optionen** Feld. Klicken Sie auf **OK**, um die Änderungen zu speichern.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[/ GENPROFILE und/fastgenprofile](genprofile-fastgenprofile-generate-profiling-instrumented-build.md)<br/>
[/LTCG](ltcg-link-time-code-generation.md)<br/>
[Profilgesteuerte Optimierungen](../profile-guided-optimizations.md)<br/>
[Umgebungsvariablen für profilgesteuerte Optimierungen](../environment-variables-for-profile-guided-optimizations.md)<br/>

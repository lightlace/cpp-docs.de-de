---
title: / USEPROFILE (Verwendung von PGO-Daten mit LTCG) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
f1_keywords:
- USEPROFILE
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 156a571eaa3db31b8c5345f1550346503651665d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32377992"
---
# <a name="useprofile-run-pgo-in-thread-safe-mode"></a>/ USEPROFILE (PGO im abgesicherten Threadmodus ausgeführt)

Diese Linkeroption zusammen mit [/LTCG (Link-Time Code Generation](ltcg-link-time-code-generation.md) weist den Linker an, mit der Trainingsdaten für die profilgesteuerte Optimierung (PGO) erstellen.

## <a name="syntax"></a>Syntax

> **/ USEPROFILE**[**:**{**AGGRESSIVE**|**PGD =**_Filename_}]

### <a name="arguments"></a>Argumente

**AGGRESSIVE**<br/>
Dieses optionale Argument gibt an, dass es sich bei aggressiven Geschwindigkeit Optimierungen, die während der Generierung von optimiertem Code verwendet werden soll.

**PGD**=*Dateiname*<br/>
Gibt einen Basisdateinamen für die PGD-Datei an. Standardmäßig wird vom Linker der ausführbaren Basisdateiname mit der Erweiterung PGD verwendet.

## <a name="remarks"></a>Hinweise

Die **/useprofile** Linkeroption dient zusammen mit **/LTCG** generieren oder einen optimierten Build basierend auf PGO Training Data aktualisiert werden. Dies entspricht der veralteten **/LTCG: PGUPDATE** und **/LTCG: PGOPTIMIZE** Optionen.

Das optionale **AGGRESSIVE** Argument deaktiviert hinsichtlich der Größe Heuristik, um zu versuchen, die Geschwindigkeit zu optimieren. Dies kann in Optimierungen führen, die im Wesentlichen erhöhen die Größe Ihrer ausführbaren Datei, und die resultierende Geschwindigkeit kann nicht vergrößert. Sie sollten ein Profil erstellen und vergleichen Sie die Ergebnisse der Verwendung und nicht mit **AGGRESSIVE**. Dieses Argument muss explizit angegeben werden. Es ist nicht standardmäßig aktiviert.

Die **PGD** Argument gibt einen optionalen Namen für das Training Daten PGD-Datei zu verwenden, entspricht der Vorgehensweise in [/genprofile oder/fastgenprofile](genprofile-fastgenprofile-generate-profiling-instrumented-build.md). Dies entspricht der veralteten **/PGD** wechseln. Standardmäßig oder wenn keine *Filename* angegeben wird, eine PGD-Datei, die den gleichen Basisnamen hat, wie die ausführbare Datei verwendet wird.

Die **/useprofile** Linkeroption ist neu in Visual Studio 2015.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **Linker** > **Optimierung** Eigenschaftenseite.

1. In der **Link-Time Code Generation** -Eigenschaft, wählen Sie **mit Link-Time Code Generation (/ LTCG)**.

1. Wählen Sie die **Konfigurationseigenschaften** > **Linker** > **Befehlszeile** Eigenschaftenseite.

1. Geben Sie die **/useprofile** Option und optionalen Argumenten in der **Zusatzoptionen** Feld. Wählen Sie **OK** zum Speichern der Änderungen.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[/ GENPROFILE und/fastgenprofile](genprofile-fastgenprofile-generate-profiling-instrumented-build.md)<br/>
[/LTCG](ltcg-link-time-code-generation.md)<br/>
[Profilgesteuerte Optimierungen](../../build/reference/profile-guided-optimizations.md)<br/>
[Umgebungsvariablen für profilgesteuerte Optimierungen](../../build/reference/environment-variables-for-profile-guided-optimizations.md)<br/>

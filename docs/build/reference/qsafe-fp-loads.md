---
title: / Qsafe_fp_loads | Microsoft-Dokumentation
ms.custom: ''
ms.date: 01/24/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0af28b391390f28be4e111b55c909dcae66ca2f8
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45713660"
---
# <a name="qsafefploads"></a>/Qsafe_fp_loads

Erfordert ganzzahlige Verschiebungsanweisungen für Gleitkommawerte und deaktiviert bestimmte Gleitkomma-Ladeoptimierungen.

## <a name="syntax"></a>Syntax

> **/Qsafe_fp_loads**

## <a name="remarks"></a>Hinweise

**/ Qsafe_fp_loads** ist nur in Compilern verfügbar, mit der Zielplattform X86; es ist nicht verfügbar, in dem Compiler, X64 oder ARM abzielen.

**/ Qsafe_fp_loads** erzwingt, dass der Compiler, ganzzahlige verschiebungsanweisungen anstelle der Gleitkomma-verschiebungsanweisungen verwenden Sie zum Verschieben von Daten zwischen Arbeitsspeicher und MMX registriert. Diese Option deaktiviert auch Registerladeoptimierung für Gleitkommawerte, die in mehreren Kontrollpfaden geladen werden können, wenn der Wert (beispielsweise NaN) beim Laden eine Ausnahme verursacht.

Diese Option wird überschrieben, indem [/fp: mit Ausnahme von](../../build/reference/fp-specify-floating-point-behavior.md). **/ Qsafe_fp_loads** gibt an, eine Teilmenge des Compilerverhaltens an, die angegebenen **/fp: mit Ausnahme von**.

**/ Qsafe_fp_loads** ist nicht kompatibel mit ["/ CLR"](../../build/reference/clr-common-language-runtime-compilation.md) und [fast](../../build/reference/fp-specify-floating-point-behavior.md). Weitere Informationen über Gleitkomma-Compileroptionen finden Sie unter [/fp (Festlegen des Gleitkommaverhaltens)](../../build/reference/fp-specify-floating-point-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **Befehlszeile** Eigenschaftenseite.

1. Geben Sie die Compileroption in der **zusätzliche Optionen** Feld. Wählen Sie **OK** um die Änderung zu übernehmen.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[/ Q-Optionen (Operationen auf niedriger Ebene)](../../build/reference/q-options-low-level-operations.md)
[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)

---
title: / Qsafe_fp_loads | Microsoft Docs
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
ms.openlocfilehash: 1462303f9e178c70a845066bc7a0a3ce78a99e15
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="qsafefploads"></a>/Qsafe_fp_loads

Erfordert ganzzahlige Verschiebungsanweisungen für Gleitkommawerte und deaktiviert bestimmte Gleitkomma-Ladeoptimierungen.

## <a name="syntax"></a>Syntax

> **/Qsafe_fp_loads**

## <a name="remarks"></a>Hinweise

**/ Qsafe_fp_loads** ist nur in Compilern verfügbar, die gezielt X86; es ist nicht in Compilern, die auf X64 oder ARM abzielen.

**/ Qsafe_fp_loads** erzwingt der Compiler, ganzzahlige verschiebungsanweisungen anstelle der Gleitkomma-verschiebungsanweisungen verwenden Sie zum Verschieben von Daten zwischen Arbeitsspeicher und MMX registriert. Diese Option deaktiviert auch Registerladeoptimierung für Gleitkommawerte, die in mehreren Kontrollpfaden geladen werden können, wenn der Wert (beispielsweise NaN) beim Laden eine Ausnahme verursacht.

Diese Option wird überschrieben, indem [/fp: außer](../../build/reference/fp-specify-floating-point-behavior.md). **/ Qsafe_fp_loads** gibt eine Teilmenge des Compilerverhaltens an, die angegebenen **/fp: außer**.

**/ Qsafe_fp_loads** ist inkompatibel mit ["/ CLR"](../../build/reference/clr-common-language-runtime-compilation.md) und [/fp: fast](../../build/reference/fp-specify-floating-point-behavior.md). Weitere Informationen zu den floating Point-Compileroptionen finden Sie unter [/fp (Festlegen von Floating-Verhalten)](../../build/reference/fp-specify-floating-point-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **Befehlszeile** Eigenschaftenseite.

1. Geben Sie die Compileroption "in der **Zusatzoptionen** Feld. Wählen Sie **OK** um die Änderung zu übernehmen.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[/Q-Optionen (Vorgänge auf niedriger Ebene)](../../build/reference/q-options-low-level-operations.md)  
[Compileroptionen](../../build/reference/compiler-options.md)  
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)  

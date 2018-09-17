---
title: -O1, -O2 (Größe minimieren, Geschwindigkeit maximieren) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/25/2017
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /o2
- /o1
dev_langs:
- C++
helpviewer_keywords:
- maximize speed compiler option [C++]
- minimize size compiler option [C++]
- -O2 compiler option [C++]
- fast code
- small code
- O2 compiler option [C++]
- /O2 compiler option [C++]
- -O1 compiler option [C++]
- O1 compiler option [C++]
- /O1 compiler option [C++]
ms.assetid: 2d1423f5-53d9-44da-8908-b33a351656c2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 832ea689b2db9a34b55664b695747079ac277bae
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45702558"
---
# <a name="o1-o2-minimize-size-maximize-speed"></a>/O1, /O2 (Größe minimieren, Geschwindigkeit maximieren)

Wählt einen vordefinierten Satz von Optionen, die Einfluss auf die Größe und Geschwindigkeit des generierten Codes.

## <a name="syntax"></a>Syntax

> / O1 "/ O2"

## <a name="remarks"></a>Hinweise

Die **"/ O1"** und **"/ O2"** Compileroptionen sind eine schnelle Möglichkeit, mehrere spezifische Optimierungsoptionen gleichzeitig festlegen. Die **"/ O1"** Option legt fest, die Optionen für die einzelnen Optimierung, die den kleinsten Code in den meisten Fällen zu erstellen. Die **"/ O2"** Option legt fest, die Optionen, die den schnellsten Code in den meisten Fällen zu erstellen. Die **"/ O2"** ist die Standardoption für Releasebuilds. Diese Tabelle zeigt die Optionen, die festgelegt werden, indem **"/ O1"** und **"/ O2"**:

|Option|Äquivalent zu|
|------------|-------------------|
|**/ O1** (Größe minimieren)|["/ Og"](../../build/reference/og-global-optimizations.md) [/OS](../../build/reference/os-ot-favor-small-code-favor-fast-code.md) [/Oy](../../build/reference/oy-frame-pointer-omission.md) [/Ob2](../../build/reference/ob-inline-function-expansion.md) [/GF](../../build/reference/gf-eliminate-duplicate-strings.md)  [ /Gy](../../build/reference/gy-enable-function-level-linking.md)|
|**/ O2** (Geschwindigkeit maximieren)|["/ Og"](../../build/reference/og-global-optimizations.md) [/Oi](../../build/reference/oi-generate-intrinsic-functions.md) [/Ot](../../build/reference/os-ot-favor-small-code-favor-fast-code.md) [/Oy](../../build/reference/oy-frame-pointer-omission.md) [/Ob2](../../build/reference/ob-inline-function-expansion.md) [/GF](../../build/reference/gf-eliminate-duplicate-strings.md)  [ /Gy](../../build/reference/gy-enable-function-level-linking.md)|

**/ O1** und **"/ O2"** gegenseitig aus.

> [!NOTE]
> **X86 bestimmte** diese Optionen beinhalten die Verwendung der Frame-Pointer Omission ([/Oy](../../build/reference/oy-frame-pointer-omission.md)) Option.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Klicken Sie unter **Konfigurationseigenschaften**öffnen **C/C++-** und wählen Sie dann die **Optimierung** Eigenschaftenseite.

1. Ändern der **Optimierung** Eigenschaft.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Optimization%2A>.

## <a name="see-also"></a>Siehe auch

[/ O-Optionen (Code optimieren)](../../build/reference/o-options-optimize-code.md)
[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)<br/>
[/EH (Ausnahmebehandlungsmodell)](../../build/reference/eh-exception-handling-model.md)

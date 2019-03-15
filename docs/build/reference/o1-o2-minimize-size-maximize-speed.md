---
title: /O1, /O2 (Größe minimieren, Geschwindigkeit maximieren)
ms.date: 09/25/2017
f1_keywords:
- /o2
- /o1
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
ms.openlocfilehash: d33fe6bceae09267fd3f79ffe3dc26864e87c764
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57820584"
---
# <a name="o1-o2-minimize-size-maximize-speed"></a>/O1, /O2 (Größe minimieren, Geschwindigkeit maximieren)

Wählt einen vordefinierten Satz von Optionen, die Einfluss auf die Größe und Geschwindigkeit des generierten Codes.

## <a name="syntax"></a>Syntax

> /O1 /O2

## <a name="remarks"></a>Hinweise

Die **"/ O1"** und **"/ O2"** Compileroptionen sind eine schnelle Möglichkeit, mehrere spezifische Optimierungsoptionen gleichzeitig festlegen. Die **"/ O1"** Option legt fest, die Optionen für die einzelnen Optimierung, die den kleinsten Code in den meisten Fällen zu erstellen. Die **"/ O2"** Option legt fest, die Optionen, die den schnellsten Code in den meisten Fällen zu erstellen. Die **"/ O2"** ist die Standardoption für Releasebuilds. Diese Tabelle zeigt die Optionen, die festgelegt werden, indem **"/ O1"** und **"/ O2"**:

|Option|Äquivalent zu|
|------------|-------------------|
|**/ O1** (Größe minimieren)|[/Og](og-global-optimizations.md) [/Os](os-ot-favor-small-code-favor-fast-code.md) [/Oy](oy-frame-pointer-omission.md) [/Ob2](ob-inline-function-expansion.md) [/GF](gf-eliminate-duplicate-strings.md) [/Gy](gy-enable-function-level-linking.md)|
|**/ O2** (Geschwindigkeit maximieren)|[/Og](og-global-optimizations.md) [/Oi](oi-generate-intrinsic-functions.md) [/Ot](os-ot-favor-small-code-favor-fast-code.md) [/Oy](oy-frame-pointer-omission.md) [/Ob2](ob-inline-function-expansion.md) [/GF](gf-eliminate-duplicate-strings.md) [/Gy](gy-enable-function-level-linking.md)|

**/ O1** und **"/ O2"** gegenseitig aus.

> [!NOTE]
> **X86 bestimmte** diese Optionen beinhalten die Verwendung der Frame-Pointer Omission ([/Oy](oy-frame-pointer-omission.md)) Option.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Klicken Sie unter **Konfigurationseigenschaften**öffnen **C/C++-** und wählen Sie dann die **Optimierung** Eigenschaftenseite.

1. Ändern der **Optimierung** Eigenschaft.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Optimization%2A>.

## <a name="see-also"></a>Siehe auch

[/O-Optionen (Code optimieren)](o-options-optimize-code.md)<br/>
[MSVC-Compiler-Optionen](compiler-options.md)<br/>
[MSVC-Compiler-Befehlszeilensyntax](compiler-command-line-syntax.md)<br/>
[/EH (Ausnahmebehandlungsmodell)](eh-exception-handling-model.md)

---
title: /QIntel-jcc-erratum
description: Describes the Microsoft C/C++ compiler (MSVC) /QIntel-jcc-erratum option.
ms.date: 01/07/2020
f1_keywords:
- QIntel-jcc-erratum
helpviewer_keywords:
- /QIntel-jcc-erratum
- -QIntel-jcc-erratum
ms.openlocfilehash: f311da04b833b06124c5e6237ea83a31319858ca
ms.sourcegitcommit: a930a9b47bd95599265d6ba83bb87e46ae748949
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2020
ms.locfileid: "76520918"
---
# <a name="qintel-jcc-erratum"></a>/QIntel-jcc-erratum

::: moniker range="<=vs-2017"

The **/QIntel-jcc-erratum** option is available in Visual Studio 2019 version 16.5 and later.

::: moniker-end

::: moniker range=">=vs-2019"

Specifies that the compiler generates instructions to mitigate the performance impact caused by the Intel Jump Conditional Code (JCC) erratum microcode update in certain Intel processors.

## <a name="syntax"></a>Syntax

> **/QIntel-jcc-erratum**

## <a name="remarks"></a>Hinweise

Under **/QIntel-jcc-erratum**, the compiler detects jump and macro-fused jump instructions that cross or end on a 32-byte boundary. It aligns these instructions to the boundary. This change mitigates the performance impact of microcode updates that prevent the JCC erratum in certain Intel processors. For more information about the erratum, see [Mitigations for Jump Conditional Code Erratum](https://www.intel.com/content/dam/support/us/en/documents/processors/mitigations-jump-conditional-code-erratum.pdf) on the Intel website.

The **/QIntel-jcc-erratum** option is available in Visual Studio 2019 version 16.5 and later. This option is only available in compilers that target x86 and x64. The option isn't available in compilers that target ARM processors.

The **/QIntel-jcc-erratum** option is off by default, and works only in optimized builds. This option can increase code size.

**/QIntel-jcc-erratum** is incompatible with [/clr](clr-common-language-runtime-compilation.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen erhalten Sie unter [Set C++ compiler and build properties in Visual Studio (Festlegen der Compiler- und Buildeigenschaften (C++) in Visual Studio)](../working-with-project-properties.md).

1. Select the **Configuration Properties** > **C/C++** > **Code Generation** property page.

1. Select a value for the **Enable Intel JCC Erratum Mitigation** property. Wählen Sie **OK** aus, um die Änderung zu übernehmen.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[/Q options (Low-level operations)](q-options-low-level-operations.md)\
[MSVC compiler options](compiler-options.md)\
[MSVC compiler command-line syntax](compiler-command-line-syntax.md)

::: moniker-end

---
title: /arch (ARM)
ms.date: 11/04/2016
ms.assetid: 4f1406ff-f174-487c-a126-8ab06cf447c1
ms.openlocfilehash: b732a74d5fe223fdaf3b161d4ae92093ab5df407
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62295201"
---
# <a name="arch-arm"></a>/arch (ARM)

Gibt die Architektur für die Codegenerierung auf ARM an. Siehe auch [/arch (x86)](arch-x86.md) und [/arch (x64)](arch-x64.md).

## <a name="syntax"></a>Syntax

```
/arch:[ARMv7VE|VFPv4]
```

## <a name="arguments"></a>Argumente

**/arch:ARMv7VE**<br/>
Ermöglicht die Verwendung von Anweisungen für ARMv7VE-Virtualisierungserweiterungen.

**/arch:VFPv4**<br/>
Ermöglicht die Verwendung von ARM-VFPv4-Anweisungen. Wenn diese Option nicht angegeben wird, ist VFPv3 die Standardeinstellung.

## <a name="remarks"></a>Hinweise

Die `_M_ARM_FP` Makro (für ARM) gibt an, welche, sofern vorhanden, **/arch** -Compileroption verwendet wurde. Weitere Informationen finden Sie unter [Predefined Macros](../../preprocessor/predefined-macros.md).

Bei Verwendung von ["/ CLR"](clr-common-language-runtime-compilation.md) kompiliert werden, **/arch** hat keine Auswirkungen auf die codegenerierung für verwaltete Funktionen. **/ arch** nur wirkt sich auf die codegenerierung für systemeigene Funktionen Codes.

### <a name="to-set-the-archarmv7ve-or-archvfpv4-compiler-option-in-visual-studio"></a>Zum Festlegen der /arch:ARMv7VE oder /arch:VFPv4-Compileroption in Visual Studio

1. Öffnen der **Eigenschaftenseiten** im Dialogfeld für das Projekt. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Wählen Sie die **C/C++-** Ordner.

1. Wählen Sie die **Befehlszeile** Eigenschaftenseite.

1. In der **zusätzliche Optionen** fügen `/arch:ARMv7VE` oder `/arch:VFPv4`.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableEnhancedInstructionSet%2A>.

## <a name="see-also"></a>Siehe auch

[/arch (Mindestanforderungen an die CPU-Architektur)](arch-minimum-cpu-architecture.md)<br/>
[MSVC-Compileroptionen](compiler-options.md)<br/>
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)

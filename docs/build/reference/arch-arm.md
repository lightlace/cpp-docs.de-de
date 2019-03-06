---
title: /arch (ARM)
ms.date: 11/04/2016
ms.assetid: 4f1406ff-f174-487c-a126-8ab06cf447c1
ms.openlocfilehash: 7fd396f4ed9c02daff5363342d7c851d022919ac
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57424989"
---
# <a name="arch-arm"></a>/arch (ARM)

Gibt die Architektur für die Codegenerierung auf ARM an. Siehe auch [/arch (x86)](../../build/reference/arch-x86.md) und [/arch (x64)](../../build/reference/arch-x64.md).

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

Bei Verwendung von ["/ CLR"](../../build/reference/clr-common-language-runtime-compilation.md) kompiliert werden, **/arch** hat keine Auswirkungen auf die codegenerierung für verwaltete Funktionen. **/ arch** nur wirkt sich auf die codegenerierung für systemeigene Funktionen Codes.

### <a name="to-set-the-archarmv7ve-or-archvfpv4-compiler-option-in-visual-studio"></a>Zum Festlegen der /arch:ARMv7VE oder /arch:VFPv4-Compileroption in Visual Studio

1. Öffnen der **Eigenschaftenseiten** im Dialogfeld für das Projekt. Weitere Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Wählen Sie die **C/C++-** Ordner.

1. Wählen Sie die **Befehlszeile** Eigenschaftenseite.

1. In der **zusätzliche Optionen** fügen `/arch:ARMv7VE` oder `/arch:VFPv4`.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableEnhancedInstructionSet%2A>.

## <a name="see-also"></a>Siehe auch

[/arch (Mindestanforderungen an die CPU-Architektur)](../../build/reference/arch-minimum-cpu-architecture.md)<br/>
[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)

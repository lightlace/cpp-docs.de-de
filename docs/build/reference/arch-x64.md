---
title: -arch (x64) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
ms.assetid: ecda22bf-5bed-43f4-99fb-88aedd83d9d8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 236923732a193830fe3fad643570666db56cddac
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45707355"
---
# <a name="arch-x64"></a>/arch (x64)

Gibt die Architektur für die Codegenerierung auf x64 an. Siehe auch [/arch (x86)](../../build/reference/arch-x86.md) und [/arch (ARM)](../../build/reference/arch-arm.md).

## <a name="syntax"></a>Syntax

```
/arch:[AVX|AVX2]
```

## <a name="arguments"></a>Argumente

**/ arch: AVX**<br/>
Aktiviert die Verwendung von Intel Advanced Vector Extensions-Anweisungen.

**/ arch: avx2**<br/>
Aktiviert die Verwendung von Intel Advanced Vector Extensions 2-Anweisungen.

## <a name="remarks"></a>Hinweise

**/ arch** nur wirkt sich auf die codegenerierung für systemeigene Funktionen Codes. Bei Verwendung von ["/ CLR"](../../build/reference/clr-common-language-runtime-compilation.md) kompiliert werden, **/arch** hat keine Auswirkungen auf die codegenerierung für verwaltete Funktionen.

Die `__AVX__` -Präprozessorsymbol verwendet, wenn die **/arch: AVX** -Compileroption angegeben ist. Die `__AVX2__` -Präprozessorsymbol verwendet, wenn die **/arch: avx2** -Compileroption angegeben ist. Weitere Informationen finden Sie unter [Predefined Macros](../../preprocessor/predefined-macros.md). Die **/arch: avx2** Option wurde in Visual Studio 2013 Update 2 Version 12.0.34567.1 eingeführt.

### <a name="to-set-the-archavx-or-archavx2-compiler-option-in-visual-studio"></a>So legen Sie die /arch:AVX- oder /arch:AVX2-Compileroption in Visual Studio fest

1. Öffnen der **Eigenschaftenseiten** im Dialogfeld für das Projekt. Weitere Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften**, **C/C++-** Ordner.

1. Wählen Sie die **Codegenerierung** Eigenschaftenseite.

1. In der **Erweitertes Anweisungsset aktivieren** Dropdownliste wählen **Advanced Vector Extensions (/ Arch: AVX)** oder **Advanced Vector Extensions 2 (/ Arch: AVX2)**.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableEnhancedInstructionSet%2A>.

## <a name="see-also"></a>Siehe auch

[/ arch (minimale CPU-Architektur)](../../build/reference/arch-minimum-cpu-architecture.md)
[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)
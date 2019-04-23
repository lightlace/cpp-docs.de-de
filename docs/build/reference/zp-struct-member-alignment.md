---
title: /Zp (Ausrichten des Strukturmembers)
ms.date: 04/04/2019
f1_keywords:
- /zp
- VC.Project.VCCLCompilerTool.StructMemberAlignment
- VC.Project.VCCLWCECompilerTool.StructMemberAlignment
helpviewer_keywords:
- Struct Member Alignment compiler option
- Zp compiler option
- /Zp compiler option [C++]
- -Zp compiler option [C++]
ms.assetid: 5242f656-ed9b-48a3-bc73-cfcf3ed2520f
ms.openlocfilehash: d76cd93c7af4228bff8f73fa3bcbf40fa149b0be
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59237163"
---
# <a name="zp-struct-member-alignment"></a>/Zp (Ausrichten des Strukturmembers)

Steuert, wie die Member einer Struktur im Speicher abgelegt werden, und gibt die gleichen Packen von Metriken für alle Strukturen in einem Modul.

## <a name="syntax"></a>Syntax

> **/Zp**[**1**|**2**|**4**|**8**|**16**]

## <a name="remarks"></a>Hinweise

Die **/Zp**_n_ Option teilt dem Compiler, wo die einzelnen Strukturmember gespeichert. Der Compiler speichert Member an einer Grenze, die die kleinere von entweder die Größe der der Elementtyp ist nach der ersten oder *n*-Byte-Grenze.

Die verfügbaren Packen-Werte werden in der folgenden Tabelle beschrieben:

|/ Zp-argument|Effekt|
|-|-|
|1|Komprimiert Strukturen auf 1-Byte-Begrenzungen. Identisch mit **/Zp**.|
|2|Komprimiert Strukturen auf 2-Byte-Begrenzungen.|
|4|Komprimiert Strukturen auf 4-Byte-Begrenzungen.|
|8|Komprimiert Strukturen auf 8-Byte-Begrenzungen (Standard für X86, ARM und ARM64).|
|16| Komprimiert Strukturen auf 16-Byte-Begrenzungen (Standard für X64).|

Verwenden Sie diese Option nicht, es sei denn, Sie bestimmte ausrichtungsanforderungen haben.

> [!WARNING]
> Im Windows SDK C++-Header festgelegt und vorausgesetzt **"/ zp8"** intern packen. Arbeitsspeicher, die eine Beschädigung kann auftreten, wenn die **/Zp** Einstellung geändert wird, in das Windows SDK-Header. Die Header sind nicht betroffen von einem **/Zp** Option, die Sie in der Befehlszeile festlegen.

Sie können auch [Pack](../../preprocessor/pack.md) Ausrichten von Strukturen. Weitere Informationen zur Ausrichtung finden Sie unter:

- [align](../../cpp/align-cpp.md)

- [__alignof-Operator](../../cpp/alignof-operator.md)

- [__unaligned](../../cpp/unaligned.md)

- [/ALIGN (Abschnittsausrichtung)](align-section-alignment.md)

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **Codegenerierung** Eigenschaftenseite.

1. Ändern der **Ausrichtung der Strukturmember an** Eigenschaft.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.StructMemberAlignment%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Compiler-Optionen](compiler-options.md) \
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)

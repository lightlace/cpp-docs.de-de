---
title: -favor (optimieren für Besonderheiten der Architektur) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /favor
dev_langs:
- C++
helpviewer_keywords:
- -favor compiler option [C++]
- /favor compiler option [C++]
ms.assetid: ad264df2-e30f-4d68-8bd0-10d6bee71a2a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 03d1bdce12e461446f1804844040457dae6e9d43
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45724756"
---
# <a name="favor-optimize-for-architecture-specifics"></a>/favor (Optimieren für Besonderheiten der Architektur)

**/ favor:** `option` generiert Code, der für eine bestimmte Architektur oder für die Einzelheiten der Micro-Architekturen, in der AMD und Intel-Architekturen optimiert ist.

## <a name="syntax"></a>Syntax

```
/favor:{blend | ATOM | AMD64 | INTEL64}
```

## <a name="remarks"></a>Hinweise

**/ favor: Blend**<br/>
(X86- und X64) erzeugt den Code, der für die Einzelheiten der Micro-Architekturen, in der AMD und Intel-Architekturen optimiert ist. Während **/favor: Blend** erhalten möglicherweise nicht die beste Leistung für einen bestimmten Prozessor möglich ist, wurde entwickelt, um die beste Leistung für eine Vielzahl von X86 und X64-Prozessoren zu gewährleisten. In der Standardeinstellung **/favor: Blend** ist aktiviert.

**/favor:Atom**<br/>
(X86- und X64) erzeugt den Code, der für die Einzelheiten der Intel Atom-Prozessor und Intel Centrino Atom-Prozessortechnologien optimiert ist. Mithilfe von generierten Code **/favor:ATOM** Intel SSSE3, SSE3, SSE und SSE2-Anweisungen für Intel-Prozessoren kann auch erstellt werden.

**/favor:AMD64**<br/>
(nur X64) optimiert den generierten Code für AMD Opteron und Athlon-Prozessoren, 64-Bit-Erweiterungen unterstützen. Der optimierte Code kann auf alle X64 kompatible Plattformen ausführen. Mithilfe von generierten Code **/favor:AMD64** möglicherweise unzureichende Leistung auf Intel-Prozessoren, die Intel64 zu unterstützen.

**/favor:Intel64**<br/>
(nur X64) optimiert den generierten Code für Intel-Prozessoren, die Intel64, zu unterstützen, die in der Regel eine bessere Leistung für diese Plattform liefert. Der resultierende Code kann auf alle X64 ausführen Plattform. Mit generierten Code **/favor:INTEL64** möglicherweise unzureichende Leistung auf AMD Opteron und Athlon-Prozessoren, 64-Bit-Erweiterungen unterstützen.

> [!NOTE]
> Intel64-Architektur wurde zuvor als Extended Memory 64 Technology bezeichnet, und die entsprechende Compileroption wurde **/favor:EM64T**.

Informationen über das Programmieren für die X64-Architektur finden Sie unter [X64 Softwarekonventionen](../../build/x64-software-conventions.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Wählen Sie die **C/C++-** Ordner.

1. Wählen Sie die **Befehlszeile** Eigenschaftenseite.

1. Geben Sie die Compileroption in der **zusätzliche Optionen** Feld.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)
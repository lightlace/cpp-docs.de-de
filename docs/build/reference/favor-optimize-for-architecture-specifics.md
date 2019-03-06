---
title: /favor (Optimieren für Besonderheiten der Architektur)
ms.date: 11/04/2016
f1_keywords:
- /favor
helpviewer_keywords:
- -favor compiler option [C++]
- /favor compiler option [C++]
ms.assetid: ad264df2-e30f-4d68-8bd0-10d6bee71a2a
ms.openlocfilehash: 1f76164468375e84380c6f02050c6c7a35b32412
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57418983"
---
# <a name="favor-optimize-for-architecture-specifics"></a>/favor (Optimieren für Besonderheiten der Architektur)

**/ favor:** `option` generiert Code, der für eine bestimmte Architektur oder für die Einzelheiten der Micro-Architekturen, in der AMD und Intel-Architekturen optimiert ist.

## <a name="syntax"></a>Syntax

> **/favor:**{**blend** | **ATOM** | **AMD64** | **INTEL64**}

## <a name="remarks"></a>Hinweise

**/favor:blend**<br/>
(X86- und X64) erzeugt den Code, der für die Einzelheiten der Micro-Architekturen, in der AMD und Intel-Architekturen optimiert ist. Während **/favor: Blend** erhalten möglicherweise nicht die beste Leistung für einen bestimmten Prozessor möglich ist, wurde entwickelt, um die beste Leistung für eine Vielzahl von X86 und X64-Prozessoren zu gewährleisten. In der Standardeinstellung **/favor: Blend** ist aktiviert.

**/favor:ATOM**<br/>
(X86- und X64) erzeugt den Code, der für die Einzelheiten der Intel Atom-Prozessor und Intel Centrino Atom-Prozessortechnologien optimiert ist. Mithilfe von generierten Code **/favor:ATOM** Intel SSSE3, SSE3, SSE und SSE2-Anweisungen für Intel-Prozessoren kann auch erstellt werden.

**/favor:AMD64**<br/>
(nur X64) optimiert den generierten Code für AMD Opteron und Athlon-Prozessoren, 64-Bit-Erweiterungen unterstützen. Der optimierte Code kann auf alle X64 kompatible Plattformen ausführen. Mithilfe von generierten Code **/favor:AMD64** möglicherweise unzureichende Leistung auf Intel-Prozessoren, die Intel64 zu unterstützen.

**/favor:INTEL64**<br/>
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

---
title: /Tc, /Tp, /TC, /TP (Typ der Quelldatei angeben)
ms.date: 1/11/2018
f1_keywords:
- VC.Project.VCCLWCECompilerTool.CompileAs
- VC.Project.VCCLCompilerTool.CompileAs
- /Tp
- /tc
helpviewer_keywords:
- Tp compiler option [C++]
- /Tc compiler option [C++]
- -Tc compiler option [C++]
- source files, specifying to compiler
- Tc compiler option [C++]
- /Tp compiler option [C++]
- -Tp compiler option [C++]
ms.openlocfilehash: f7ee51c858c9f90440cf0c2b21799ef7473cf6da
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62317444"
---
# <a name="tc-tp-tc-tp-specify-source-file-type"></a>/Tc, /Tp, /TC, /TP (Typ der Quelldatei angeben)

Die **/TC** Option gibt an, dass das Filename-Argument eine C-Quelldatei, auch wenn sie nicht über eine c-Erweiterung verfügt. Die **/TP** Option gibt an, dass das Filename-Argument eine C++-Quelldatei, auch wenn sie eine Erweiterung .cpp oder .cxx hat. Ein Leerzeichen zwischen der Option und der Dateiname ist optional. Jede Option gibt eine Datei an. um zusätzliche Dateien anzugeben, wiederholen Sie die Option aus.

**/ TC** und **/TP** sind globale Varianten von **/TC** und **/TP**. Sie geben dem Compiler, alle Dateien, die mit dem Namen in der Befehlszeile als C-Quelldateien zu behandeln (**/TC**) oder C++-Quelldateien (**/TP**), unabhängig von Speicherort in der Befehlszeile in Bezug auf die Option. Diese globalen Optionen können überschrieben werden, für eine einzelne Datei von **/TC** oder **/TP**.

## <a name="syntax"></a>Syntax

> **/Tc** _filename_
>  **/Tp** _filename_
>  **/TC**
>  **/TP**

## <a name="arguments"></a>Argumente

*filename*<br/>
Eine C- oder C++-Quelldatei.

## <a name="remarks"></a>Hinweise

In der Standardeinstellung **CL** wird davon ausgegangen, dass Dateien mit der Erweiterung .c C-Quelldateien und Dateien mit der .cpp oder .cxx C++-Quelldateien sind.

Wenn entweder die **TC** oder **Tc** angegeben wird, eine Angabe in der [/Zc: wchar_t (Wchar_t ist der systemeigene Typ)](zc-wchar-t-wchar-t-is-native-type.md) Option wird ignoriert.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **erweitert** Eigenschaftenseite.

1. Ändern der **Kompilierungsart** Eigenschaft. Wählen Sie **OK** oder **übernehmen** zum Übernehmen der Änderungen.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CompileAs%2A>.

## <a name="examples"></a>Beispiele

Diese Befehlszeile CL gibt an, dass MAIN.c, TEST.prg und COLLATE.prg alle C-Quelldateien. CL Print.prg nicht.

> CL-MAIN. C /TcTEST.PRG /TcCOLLATE.PRG drucken. PRG

Diese Befehlszeile CL gibt an, dass TEST1.c, TEST2.cxx, TEST3.huh und TEST4.o werden als C++-Dateien kompiliert, TEST5.z wird als C-Datei.

> CL TEST1.C TEST2.CXX TEST3.HUH TEST4.O /Tc TEST5.Z /TP

## <a name="see-also"></a>Siehe auch

[MSVC-Compileroptionen](compiler-options.md)<br/>
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)

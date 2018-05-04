---
title: / Tc, / TP, / TC, / TP (Typ der Quelldatei angeben) | Microsoft Docs
ms.date: 1/11/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLWCECompilerTool.CompileAs
- VC.Project.VCCLCompilerTool.CompileAs
- /Tp
- /tc
dev_langs:
- C++
helpviewer_keywords:
- Tp compiler option [C++]
- /Tc compiler option [C++]
- -Tc compiler option [C++]
- source files, specifying to compiler
- Tc compiler option [C++]
- /Tp compiler option [C++]
- -Tp compiler option [C++]
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9cb612d5c26fd4db51222c480539867d5e506b70
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="tc-tp-tc-tp-specify-source-file-type"></a>/Tc, /Tp, /TC, /TP (Typ der Quelldatei angeben)

Die **/TC** Option gibt an, dass das Filename-Argument eine C-Quelldatei ist, auch wenn sie nicht über eine c-Erweiterung verfügt. Die **/TP** Option gibt an, dass das Filename-Argument eine C++-Quelldatei ist, selbst wenn sie eine Erweiterung .cpp oder .cxx besitzt. Ein Leerzeichen zwischen der Option und der Dateiname ist optional. Jede Option gibt eine Datei an. Wiederholen Sie die Option, um zusätzliche Dateien anzugeben.

**/ TC** und **/TP** sind globale Varianten von **/TC** und **/TP**. Sie geben Sie an den Compiler alle Dateien, die mit dem Namen in der Befehlszeile als C-Quelldateien behandelt (**/TC**) oder C++-Quelldateien (**/TP**), unabhängig von der Position in der Befehlszeile in Bezug auf die Option. Diese globalen Optionen können überschrieben werden, auf eine einzelne Datei anhand der **/TC** oder **/TP**.

## <a name="syntax"></a>Syntax

> **/ TC** _Dateiname_  
> **/ TP** _Dateiname_  
> **/TC**  
> **/TP**  

## <a name="arguments"></a>Argumente

*filename*  
Eine C- oder C++-Quelldatei.

## <a name="remarks"></a>Hinweise

Standardmäßig **CL** wird davon ausgegangen, dass Dateien mit der Erweiterung .c C-Quelldateien und Dateien mit der .cpp oder .cxx C++-Quelldateien sind.

Wenn entweder die **TC** oder **Tc** angegeben wird, einer Spezifikation des der [/Zc: wchar_t (Wchar_t ist der systemeigene Typ)](../../build/reference/zc-wchar-t-wchar-t-is-native-type.md) Option wird ignoriert.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **erweitert** Eigenschaftenseite.

1. Ändern der **Kompilierungsart** Eigenschaft. Wählen Sie **OK** oder **übernehmen** um die Änderungen zu übernehmen.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CompileAs%2A>.

## <a name="examples"></a>Beispiele

Mit dieser Befehlszeile CL gibt an, dass MAIN.c, TEST.prg und COLLATE.prg alle C#-Quelldateien. CL Print.prg nicht.

> CL-MAIN. C /TcTEST.PRG /TcCOLLATE.PRG drucken. PRG

Mit dieser Befehlszeile CL gibt an, dass TEST1.c, TEST2.cxx, TEST3.huh und TEST4.o als C++-Dateien kompiliert werden und TEST5.z als C-Datei kompiliert wird.

> CL TEST1.C TEST2.CXX TEST3.HUH TEST4.O /Tc TEST5.Z /TP

## <a name="see-also"></a>Siehe auch

[Compileroptionen](../../build/reference/compiler-options.md)  
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)  

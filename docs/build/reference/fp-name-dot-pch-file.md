---
title: /Fp (Name der PCH-Datei)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.PrecompiledHeaderFile
- /fp
- VC.Project.VCCLWCECompilerTool.PrecompiledHeaderFile
helpviewer_keywords:
- Fp compiler option [C++]
- -Fp compiler option [C++]
- naming precompiler header files
- PCH files, naming
- names [C++], PCH
- .pch files, naming
- precompiled header files, naming
- /Fp compiler option [C++]
ms.assetid: 0fcd9cbd-e09f-44d3-9715-b41efb5d0be2
ms.openlocfilehash: 95506e17dff47e51cb7a3d83b629880f63422d26
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62270991"
---
# <a name="fp-name-pch-file"></a>/Fp (Name der PCH-Datei)

Stellt einen Pfadnamen für einen vorkompilierten Header anstelle des Standardpfadnamens bereit.

## <a name="syntax"></a>Syntax

> **/ Fp**<em>Pfadname</em>

## <a name="remarks"></a>Hinweise

Verwenden Sie diese Option mit ["/ Yc" (Erstellen vorkompilierter Headerdatei)](yc-create-precompiled-header-file.md) oder [/Yu (vorkompilierte Headerdatei verwenden)](yu-use-precompiled-header-file.md) um einen Pfadnamen für einen vorkompilierten Header anstelle des Standardpfadnamens bereitzustellen. Sie können auch **/fp** mit **"/ Yc"** die Verwendung einer vorkompilierten Headerdatei an, die von unterscheidet der **"/ Yc"**<em>Dateiname</em> Argument und von der Basisname der Quelldatei.

Wenn Sie eine Erweiterung nicht als Teil des Pfadnamens angeben, wird davon ausgegangen, dass eine Erweiterung des PCH. Wenn Sie ein Verzeichnis ohne einen Dateinamen angeben, wird der Standarddateiname VC*x*0.pch, wobei *x* ist die Hauptversion von Visual C++ verwendet.

Sie können auch die **/fp** mit option **"/ Yu"**.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Klicken Sie auf den Ordner **C/C++** .

1. Klicken Sie auf die **vorkompilierte Header** Eigenschaftenseite.

1. Ändern der **vorkompilierte Headerdatei** Eigenschaft.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.PrecompiledHeaderFile%2A>.

## <a name="example"></a>Beispiel

Wenn eine vorkompilierte Headerdatei für eine Debugversion des Programms erstellt werden soll, und Sie die Headerdateien und Quellcode kompiliert werden, können Sie z. B. einen Befehl angeben:

```
CL /DDEBUG /Zi /Yc /FpDPROG.PCH PROG.CPP
```

## <a name="example"></a>Beispiel

Der folgende Befehl gibt die Verwendung einer vorkompilierten Headerdatei mit dem Namen MYPCH.pch. Der Compiler wird davon ausgegangen, dass der Quellcode im PROG.cpp MYAPP.h vorkompiliert wurde und der vorkompilierte Code in MYPCH.pch befindet. Er verwendet den Inhalt des MYPCH.pch und kompiliert die restlichen PROG.cpp eine .obj-Datei zu erstellen. Die Ausgabe dieses Beispiels wird eine Datei namens PROG.exe.

```
CL /YuMYAPP.H /FpMYPCH.PCH PROG.CPP
```

## <a name="see-also"></a>Siehe auch

[Ausgabedatei (/F) Optionen](output-file-f-options.md)<br/>
[MSVC-Compileroptionen](compiler-options.md)<br/>
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)<br/>
[Festlegen des Pfadnamens](specifying-the-pathname.md)

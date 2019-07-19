---
title: /X (Standardincludepfade ignorieren)
ms.date: 07/18/2019
f1_keywords:
- /x
- VC.Project.VCCLCompilerTool.OVERWRITEStandardIncludePath
- VC.Project.VCCLWCECompilerTool.OVERWRITEStandardIncludePath
- VC.Project.VCCLCompilerTool.IgnoreStandardIncludePath
helpviewer_keywords:
- /X compiler option [C++]
- include files, ignore standard path
- -X compiler option [C++]
- include directories, ignore standard
- X compiler option
- Ignore Standard Include Paths compiler option
ms.assetid: 16bdf2cc-c8dc-46e4-bdcc-f3caeba5e1ef
ms.openlocfilehash: 16f903b98d69472fe1a33b084fe6393ecf9ec001
ms.sourcegitcommit: 0867d648e0955ebad7260b5fbebfd6cd4d58f3c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/19/2019
ms.locfileid: "68341051"
---
# <a name="x-ignore-standard-include-paths"></a>/X (Standardincludepfade ignorieren)

Verhindert, dass der Compiler in Verzeichnissen, die in den path-und INCLUDE-Umgebungsvariablen angegeben sind, nach Includedateien sucht.

## <a name="syntax"></a>Syntax

```
/X
```

## <a name="remarks"></a>Hinweise

Sie können diese Option mit der Option [/I (weitere Includeverzeichnisse)](i-additional-include-directories.md) ( **/I**`directory`) verwenden.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen erhalten Sie unter [Set C++ compiler and build properties in Visual Studio (Festlegen der Compiler- und Buildeigenschaften (C++) in Visual Studio)](../working-with-project-properties.md).

1. Klicken Sie auf den Ordner **C/C++** .

1. Klicken Sie auf die Eigenschaften Seite **Präprozessor** .

1. Ändern Sie die Eigenschaft Standardincludepfad **ignorieren** .

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.IgnoreStandardIncludePath%2A>.

## <a name="example"></a>Beispiel

Im folgenden Befehl `/X` weist den Compiler an, Speicherorte zu ignorieren, die durch den Pfad und die include- `/I` Umgebungsvariablen angegeben sind, und gibt das Verzeichnis an, in dem nach Includedateien gesucht werden soll:

```
CL /X /I \ALT\INCLUDE MAIN.C
```

## <a name="see-also"></a>Siehe auch

[MSVC-Compileroptionen](compiler-options.md)<br/>
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)

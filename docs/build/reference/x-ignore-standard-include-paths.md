---
title: /X (Standardincludepfade ignorieren)
ms.date: 11/04/2016
f1_keywords:
- /x
- VC.Project.VCCLCompilerTool.OVERWRITEStandardIncludePath
- VC.Project.VCCLWCECompilerTool.OVERWRITEStandardIncludePath
helpviewer_keywords:
- /X compiler option [C++]
- include files, ignore standard path
- -X compiler option [C++]
- include directories, ignore standard
- X compiler option
- Ignore Standard Include Paths compiler option
ms.assetid: 16bdf2cc-c8dc-46e4-bdcc-f3caeba5e1ef
ms.openlocfilehash: 23942803ae0a25aaddd7f5844b303528c2c7ccb9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50663761"
---
# <a name="x-ignore-standard-include-paths"></a>/X (Standardincludepfade ignorieren)

Verhindert, dass der Compiler in in der PATH und INCLUDE-Umgebungsvariablen angegebenen Verzeichnisse nach Includedateien gesucht werden.

## <a name="syntax"></a>Syntax

```
/X
```

## <a name="remarks"></a>Hinweise

Sie können diese Option mit der [/i (Zusätzliche Includeverzeichnisse)](../../build/reference/i-additional-include-directories.md) (**/i**`directory`) Option.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Klicken Sie auf den Ordner **C/C++** .

1. Klicken Sie auf die **Präprozessor** Eigenschaftenseite.

1. Ändern der **Standardincludepfad ignorieren** Eigenschaft.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.IgnoreStandardIncludePath%2A>.

## <a name="example"></a>Beispiel

In den folgenden Befehl `/X` weist den Compiler an, die durch die Umgebungsvariablen PATH und INCLUDE angegeben Speicherorte zu ignorieren und `/I` gibt an, das Verzeichnis, in dem gesucht werden soll, für die Includedateien:

```
CL /X /I \ALT\INCLUDE MAIN.C
```

## <a name="see-also"></a>Siehe auch

[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)
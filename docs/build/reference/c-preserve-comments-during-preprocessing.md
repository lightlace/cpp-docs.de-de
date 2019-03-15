---
title: /C (Kommentare bei der Vorverarbeitung beibehalten)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.KeepComments
- /c
- VC.Project.VCCLWCECompilerTool.KeepComments
helpviewer_keywords:
- comments, not stripping during preprocessing
- preserve comments during preprocessing
- -c compiler option [C++]
- c compiler option [C++]
- /c compiler option [C++]
ms.assetid: 944567ca-16bc-4728-befe-d414a7787f26
ms.openlocfilehash: c5854fd1255ab509d8778828de25638dd821d74b
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57821442"
---
# <a name="c-preserve-comments-during-preprocessing"></a>/C (Kommentare bei der Vorverarbeitung beibehalten)

Behält Kommentare beim Präprozessorlauf bei

## <a name="syntax"></a>Syntax

```
/C
```

## <a name="remarks"></a>Hinweise

Diese Compileroption erfordert die **/e**, **/p**, oder **/EP** Option.

Im folgenden Codebeispiel wird der Quellcodekommentar angezeigt.

```
// C_compiler_option.cpp
// compile with: /E /C /c
int i;   // a variable
```

In diesem Beispiel wird die folgende Ausgabe erzeugt.

```
#line 1 "C_compiler_option.cpp"
int i;   // a variable
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Klicken Sie auf den Ordner **C/C++** .

1. Klicken Sie auf die **Präprozessor** Eigenschaftenseite.

1. Ändern der **Kommentare beibehalten** Eigenschaft.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.KeepComments%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Compiler-Optionen](compiler-options.md)<br/>
[MSVC-Compiler-Befehlszeilensyntax](compiler-command-line-syntax.md)<br/>
[/E (In StdOut vorverarbeiten)](e-preprocess-to-stdout.md)<br/>
[/P (In einer Datei vorverarbeiten)](p-preprocess-to-a-file.md)<br/>
[/EP (In StdOut ohne #line-Anweisungen vorverarbeiten)](ep-preprocess-to-stdout-without-hash-line-directives.md)

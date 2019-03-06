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
ms.openlocfilehash: 5502cfda1afe05d8e4944de870349a8db2860f92
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57416786"
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

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Klicken Sie auf den Ordner **C/C++** .

1. Klicken Sie auf die **Präprozessor** Eigenschaftenseite.

1. Ändern der **Kommentare beibehalten** Eigenschaft.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.KeepComments%2A>.

## <a name="see-also"></a>Siehe auch

[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)<br/>
[/E (In StdOut vorverarbeiten)](../../build/reference/e-preprocess-to-stdout.md)<br/>
[/P (In einer Datei vorverarbeiten)](../../build/reference/p-preprocess-to-a-file.md)<br/>
[/EP (In StdOut ohne #line-Anweisungen vorverarbeiten)](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md)

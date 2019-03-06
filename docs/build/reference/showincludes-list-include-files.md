---
title: /showIncludes (Includedateien auflisten)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLWCECompilerTool.ShowIncludes
- VC.Project.VCCLCompilerTool.ShowIncludes
- /showincludes
helpviewer_keywords:
- include files
- /showIncludes compiler option [C++]
- include files, displaying in compilation
- -showIncludes compiler option [C++]
- showIncludes compiler option [C++]
ms.assetid: 0b74b052-f594-45a6-a7c7-09e1a319547d
ms.openlocfilehash: 0c968f406043f5c0b5fd04c18e22a77cd640d873
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57424157"
---
# <a name="showincludes-list-include-files"></a>/showIncludes (Includedateien auflisten)

Bewirkt, dass der Compiler eine Liste der Includedateien ausgeben. Geschachtelte enthalten Dateien sind auch angezeigten (Dateien, die aus den Dateien enthaltenen, die Sie einschließen).

## <a name="syntax"></a>Syntax

```
/showIncludes
```

## <a name="remarks"></a>Hinweise

Wenn während der Kompilierung eine Include-Datei gefunden wird, ist eine Nachricht z. B. Ausgabe:

```
Note: including file: d:\MyDir\include\stdio.h
```

Geschachtelte enthalten Dateien werden durch ein Leerzeichen für jede Schachtelungsebene, Einzug angezeigt, z.B.:

```
Note: including file: d:\temp\1.h
Note: including file:  d:\temp\2.h
```

In diesem Fall `2.h` wurde innerhalb von `1.h`, daher den Einzug.

Die **/showIncludes** Option ausgibt `stderr`, nicht `stdout`.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Klicken Sie auf den Ordner **C/C++** .

1. Klicken Sie auf die **erweitert** Eigenschaftenseite.

1. Ändern der **Includes anzeigen** Eigenschaft.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ShowIncludes%2A>.

## <a name="see-also"></a>Siehe auch

[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)

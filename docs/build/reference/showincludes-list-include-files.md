---
title: -ShowIncludes (Includedateien auflisten) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLWCECompilerTool.ShowIncludes
- VC.Project.VCCLCompilerTool.ShowIncludes
- /showincludes
dev_langs:
- C++
helpviewer_keywords:
- include files
- /showIncludes compiler option [C++]
- include files, displaying in compilation
- -showIncludes compiler option [C++]
- showIncludes compiler option [C++]
ms.assetid: 0b74b052-f594-45a6-a7c7-09e1a319547d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 51305212f97482c6963ee2ba0d272c5c4692416e
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45709386"
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
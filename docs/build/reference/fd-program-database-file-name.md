---
title: -Fd (Programmdatenbank-Dateiname) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /FD
- VC.Project.VCCLWCECompilerTool.ProgramDataBaseFileName
- VC.Project.VCCLCompilerTool.ProgramDataBaseFileName
dev_langs:
- C++
helpviewer_keywords:
- /FD compiler option [C++]
- program database file name [C++]
- -FD compiler option [C++]
- PDB files, creating
- program database compiler option [C++]
- .pdb files, creating
- FD compiler option [C++]
ms.assetid: 3977a9ed-f0ac-45df-bf06-01cedd2ba85a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cfa59f889c472651eb40ddcf297ca51bd34f4e41
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46389940"
---
# <a name="fd-program-database-file-name"></a>/Fd (Programmdatenbank-Dateiname)

Gibt einen Dateinamen für die von erstellten Programmdatenbankdatei (PDB) [/Z7, / Zi, / Zi (Debuginformationsformat)](../../build/reference/z7-zi-zi-debug-information-format.md).

## <a name="syntax"></a>Syntax

```
/Fdpathname
```

## <a name="remarks"></a>Hinweise

Ohne **/FD**, standardmäßig der Name der PDB-Datei VC*x*0.pdb, wobei *x* ist die Hauptversion von Visual C++ verwendet.

Wenn Sie einen Pfadnamen angeben, die nicht auf einen Dateinamen enthalten ist (der Pfad endet mit einem umgekehrten Schrägstrich), erstellt der Compiler eine PDB-Datei mit dem Namen VC*x*0 PDB-Datei im angegebenen Verzeichnis.

Wenn Sie einen Dateinamen, der keine Erweiterung enthält angeben, verwendet der Compiler die PDB-Datei als Durchwahl.

Diese Option dient auch als Name die (IDB)-Statusdatei, die für die minimale Neuerstellung und der inkrementellen Kompilierung verwendet.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Klicken Sie auf den Ordner **C/C++** .

1. Klicken  Sie auf die Eigenschaftenseite **Ausgabedateien** .

1. Ändern der **Programmdatenbank-Dateiname** Eigenschaft.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ProgramDataBaseFileName%2A>.

## <a name="example"></a>Beispiel

Dieser Befehlszeile wird eine PDB-Datei mit dem Namen PROG.pdb und eine IDB-Datei mit dem Namen PROG.idb erstellt:

```
CL /DDEBUG /Zi /FdPROG.PDB PROG.CPP
```

## <a name="see-also"></a>Siehe auch

[Ausgabedatei (/F) Optionen](../../build/reference/output-file-f-options.md)<br/>
[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)<br/>
[Festlegen des Pfadnamens](../../build/reference/specifying-the-pathname.md)
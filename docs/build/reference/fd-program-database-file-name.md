---
title: /Fd (Programmdatenbank-Dateiname)
ms.date: 11/04/2016
f1_keywords:
- /FD
- VC.Project.VCCLWCECompilerTool.ProgramDataBaseFileName
- VC.Project.VCCLCompilerTool.ProgramDataBaseFileName
helpviewer_keywords:
- /FD compiler option [C++]
- program database file name [C++]
- -FD compiler option [C++]
- PDB files, creating
- program database compiler option [C++]
- .pdb files, creating
- FD compiler option [C++]
ms.assetid: 3977a9ed-f0ac-45df-bf06-01cedd2ba85a
ms.openlocfilehash: c686de7dc9c9c20c404240db558d2ff66078ceb7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62292730"
---
# <a name="fd-program-database-file-name"></a>/Fd (Programmdatenbank-Dateiname)

Gibt einen Dateinamen für die von erstellten Programmdatenbankdatei (PDB) [/Z7, / Zi, / Zi (Debuginformationsformat)](z7-zi-zi-debug-information-format.md).

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

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

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

[Ausgabedatei (/F) Optionen](output-file-f-options.md)<br/>
[MSVC-Compileroptionen](compiler-options.md)<br/>
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)<br/>
[Festlegen des Pfadnamens](specifying-the-pathname.md)

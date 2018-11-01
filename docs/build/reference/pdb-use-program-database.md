---
title: /PDB (Programmdatenbank verwenden)
ms.date: 11/04/2016
f1_keywords:
- /pdb
- VC.Project.VCLinkerTool.ProgramDatabaseFile
helpviewer_keywords:
- -PDB linker option
- /PDB linker option
- PDB linker option
- PDB files, creating
- .pdb files, creating
ms.assetid: d23db0ce-10cb-427a-bc60-d6b2a852723d
ms.openlocfilehash: c7d3b571a429d780c0c5eea0ad498499c615245f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50589542"
---
# <a name="pdb-use-program-database"></a>/PDB (Programmdatenbank verwenden)

```
/PDB:filename
```

## <a name="arguments"></a>Argumente

*filename*<br/>
Ein vom Benutzer angegebene Name für die Programmdatenbank (PDB), die der Linker erstellt. Sie können den Standardnamen ersetzt.

## <a name="remarks"></a>Hinweise

In der Standardeinstellung beim [/DEBUG](../../build/reference/debug-generate-debug-info.md) angegeben ist, wird der Linker erstellt eine Programmdatenbank (PDB) der Debuginformationen enthalten. Der Dateiname für die PDB-Datei hat den Basisnamen des Programms und der Dateierweiterung ".pdb".

Verwenden Sie/PDB:*Filename* um den Namen der PDB-Datei anzugeben. Wenn "/ Debug" nicht angegeben ist, wird der/PDB-Option ignoriert.

Eine PDB-Datei kann bis zu 2 GB sein.

Weitere Informationen finden Sie unter [PDB-Dateien als Linkereingabe](../../build/reference/dot-pdb-files-as-linker-input.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Klicken Sie auf die **Linker** Ordner.

1. Klicken Sie auf die **Debuggen** Eigenschaftenseite.

1. Ändern der **Programmdatenbank-Datei erstellen** Eigenschaft.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ProgramDatabaseFile%2A>.

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)
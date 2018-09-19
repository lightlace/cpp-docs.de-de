---
title: -PDBSTRIPPED (Private Symbole entfernen) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /pdbstripped
- VC.Project.VCLinkerTool.StripPrivateSymbols
dev_langs:
- C++
helpviewer_keywords:
- /PDBSTRIPPED linker option
- -PDBSTRIPPED linker option
- .pdb files, stripping private symbols
- PDB files, stripping private symbols
- PDBSTRIPPED linker option
ms.assetid: 9b9e0070-6a13-4142-8180-19c003fbbd55
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0680f265214849c2e46c4ceb23dcb71bdff61c3f
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45710839"
---
# <a name="pdbstripped-strip-private-symbols"></a>/PDBSTRIPPED (Private Symbole entfernen)

```
/PDBSTRIPPED:pdb_file_name
```

## <a name="arguments"></a>Argumente

*pdb_file_name*<br/>
Ein benutzerdefinierter Name für die entfernten Programmdatenbank (PDB), die der Linker erstellt.

## <a name="remarks"></a>Hinweise

Die/PDBSTRIPPED-Option erstellt eine zweite Programmdatenbankdatei (PDB), wenn das Programmabbild mit einer der Compiler- oder Linkeroptionen erstellt wurde, die eine PDB-Datei zu generieren ([/DEBUG](../../build/reference/debug-generate-debug-info.md), ["/ Z7"](../../build/reference/z7-zi-zi-debug-information-format.md), / Zd oder/Zi). Die zweite PDB-Datei enthält keine Symbole, die nicht an Kunden weitergegeben werden. Die zweite PDB-Datei enthält nur:

- Öffentliche Symbole

- Die Liste von Objektdateien und die Teile der ausführbaren Datei an, denen sie beitragen

- Debug-Datensätze Frame Zeiger Optimierung (FPO) verwendet, um den Stapel zu durchlaufen

Die bereinigte PDB-Datei wird nicht enthalten:

- Typinformationen

- Informationen zur Zeilennummer

- Pro-Objekt Datei CodeView-Symbole, z. B. für Funktionen, "lokal" und statischen Daten

Die vollständige PDB-Datei wird bei der Verwendung von/PDBSTRIPPED weiterhin generiert.

Wenn Sie eine PDB-Datei nicht erstellen, wird die/PDBSTRIPPED ignoriert.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Klicken Sie auf die **Linker** Ordner.

1. Klicken Sie auf die **Debuggen** Eigenschaftenseite.

1. Ändern der **Private Symbole entfernen** Eigenschaft.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.StripPrivateSymbols%2A>.

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)
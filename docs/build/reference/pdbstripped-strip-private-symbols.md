---
title: -PDBSTRIPPED (Private Symbole entfernen) | Microsoft Docs
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
ms.openlocfilehash: 331e490512afe8e9267eb1d0d370cbcf99aa99aa
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="pdbstripped-strip-private-symbols"></a>/PDBSTRIPPED (Private Symbole entfernen)
```  
/PDBSTRIPPED:pdb_file_name  
```  
  
## <a name="remarks"></a>Hinweise  
 Dabei gilt:  
  
 *pdb_file_name*  
 Ein benutzerdefinierter Name für die reduzierte Programmdatenbank (PDB), die der Linker erstellt.  
  
## <a name="remarks"></a>Hinweise  
 Die Option/PDBSTRIPPED erstellt eine zweite Programmdatenbankdatei (PDB), wenn das Programmabbild mit einer der Compiler- oder Linkeroptionen erstellt wurde, die eine PDB-Datei zu generieren ([/DEBUG](../../build/reference/debug-generate-debug-info.md), ["/ Z7"](../../build/reference/z7-zi-zi-debug-information-format.md), "/ Zd" oder/Zi). Die zweite PDB-Datei enthält keine Symbole, die nicht an Kunden weitergegeben werden. Es enthält nur die zweite PDB-Datei:  
  
-   Öffentliche Symbole  
  
-   Die Liste der Objektdateien und die Teile der ausführbaren Datei zu der sie beitragen  
  
-   Debug-Datensätze Frame Zeiger Optimierung (FPO) verwendet, um den Stapel zu durchlaufen.  
  
 Die reduzierte PDB-Datei wird nicht enthalten:  
  
-   Typinformationen  
  
-   Zeilennummerninformationen  
  
-   Pro-Objekt Datei Codeansichtsinformationen Symbole, etwa solche für Funktionen, "lokal" und statischen Daten  
  
 Die vollständige PDB-Datei wird bei der Verwendung von/PDBSTRIPPED weiterhin generiert.  
  
 Wenn Sie keine PDB-Datei erstellen, wird/PDBSTRIPPED ignoriert.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf die **Linker** Ordner.  
  
3.  Klicken Sie auf die **Debuggen** Eigenschaftenseite.  
  
4.  Ändern der **Private Symbole entfernen** Eigenschaft.  
  
### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.StripPrivateSymbols%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)
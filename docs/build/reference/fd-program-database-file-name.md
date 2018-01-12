---
title: -Fd (Programmdatenbank-Dateiname) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /FD
- VC.Project.VCCLWCECompilerTool.ProgramDataBaseFileName
- VC.Project.VCCLCompilerTool.ProgramDataBaseFileName
dev_langs: C++
helpviewer_keywords:
- /FD compiler option [C++]
- program database file name [C++]
- -FD compiler option [C++]
- PDB files, creating
- program database compiler option [C++]
- .pdb files, creating
- FD compiler option [C++]
ms.assetid: 3977a9ed-f0ac-45df-bf06-01cedd2ba85a
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a9cda26f310ec110c452394e960d3fb81d1f3e8a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="fd-program-database-file-name"></a>/Fd (Programmdatenbank-Dateiname)
Gibt einen Dateinamen für die von erstellte Programmdatenbankdatei (PDB) ["/ Z7", / Zi, / Zi (Debuginformationsformat)](../../build/reference/z7-zi-zi-debug-information-format.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
/Fdpathname  
```  
  
## <a name="remarks"></a>Hinweise  
 Ohne **/FD**, der Namen der PDB-Datei standardmäßig VC*x*0.pdb, in denen *x* die Hauptversion von Visual C++ verwendet wird.  
  
 Wenn Sie einen Pfadnamen angeben, die keinen Dateinamen enthalten (der Pfad endet mit einem umgekehrten Schrägstrich), erstellt der Compiler eine PDB-Datei mit dem Namen VC*x*0 PDB-Datei im angegebenen Verzeichnis.  
  
 Wenn Sie einen Dateinamen, der keine Erweiterung enthält angeben, verwendet der Compiler PDB-Datei als Durchwahl.  
  
 Diese Option benennt auch die Statusdatei (IDB), die für die minimale Neuerstellung und der inkrementellen Kompilierung verwendet.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **C/C++** .  
  
3.  Klicken  Sie auf die Eigenschaftenseite **Ausgabedateien** .  
  
4.  Ändern der **Programmdatenbank-Dateiname** Eigenschaft.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ProgramDataBaseFileName%2A>.  
  
## <a name="example"></a>Beispiel  
 Mit dieser Befehlszeile erstellt eine PDB-Datei mit dem Namen PROG.pdb und eine IDB-Datei mit dem Namen PROG.idb erstellt:  
  
```  
CL /DDEBUG /Zi /FdPROG.PDB PROG.CPP  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Ausgabedatei (/ F) Optionen](../../build/reference/output-file-f-options.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)   
 [Festlegen des Pfadnamens](../../build/reference/specifying-the-pathname.md)
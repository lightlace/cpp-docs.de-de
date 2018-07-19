---
title: -ShowIncludes (Includedateien Liste) | Microsoft Docs
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
ms.openlocfilehash: 6eac7df694994b625e08ded710d43837d857df2d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32378339"
---
# <a name="showincludes-list-include-files"></a>/showIncludes (Includedateien auflisten)
Weist den Compiler, eine Liste der Includedateien auszugeben. Geschachtelte enthalten Dateien sind ebenfalls angezeigt (Dateien ist, aus den Dateien, die Sie einschließen).  
  
## <a name="syntax"></a>Syntax  
  
```  
/showIncludes  
```  
  
## <a name="remarks"></a>Hinweise  
 Wenn eine Include-Datei während der Kompilierung gefunden wird, ist eine Nachricht Ausgabe, zum Beispiel:  
  
```  
Note: including file: d:\MyDir\include\stdio.h  
```  
  
 Geschachtelte enthalten Dateien werden z. B. durch einen Einzug für jede Schachtelungsebene, angegeben:  
  
```  
Note: including file: d:\temp\1.h  
Note: including file:  d:\temp\2.h  
```  
  
 In diesem Fall `2.h` wurde innerhalb von `1.h`, daher den Einzug.  
  
 Die **/showIncludes** Option ausgibt `stderr`, nicht `stdout`.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **C/C++** .  
  
3.  Klicken Sie auf die **erweitert** Eigenschaftenseite.  
  
4.  Ändern der **anzeigen enthält** Eigenschaft.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ShowIncludes%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)
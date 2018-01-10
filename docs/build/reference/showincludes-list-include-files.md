---
title: -ShowIncludes (Includedateien Liste) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLWCECompilerTool.ShowIncludes
- VC.Project.VCCLCompilerTool.ShowIncludes
- /showincludes
dev_langs: C++
helpviewer_keywords:
- include files
- /showIncludes compiler option [C++]
- include files, displaying in compilation
- -showIncludes compiler option [C++]
- showIncludes compiler option [C++]
ms.assetid: 0b74b052-f594-45a6-a7c7-09e1a319547d
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cb88ff6d8a314ebd5cb0390f2c920f5b1d04e3e9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
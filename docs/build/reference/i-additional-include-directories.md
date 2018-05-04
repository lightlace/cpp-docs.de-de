---
title: – I (Zusätzliche Includeverzeichnisse) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLWCECompilerTool.AdditionalIncludeDirectories
- VC.Project.VCCLCompilerTool.AdditionalIncludeDirectories
- /I
- VC.Project.VCNMakeTool.IncludeSearchPath
dev_langs:
- C++
helpviewer_keywords:
- /I compiler option [C++]
- Additional Include Directories compiler option
- I compiler option [C++]
- -I compiler option [C++]
- set include directories
- include directories, compiler option [C++]
ms.assetid: 3e9add2a-5ed8-4d15-ad79-5b411e313a49
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 435714d72eeabe74f0cd85509d74dff5d541b019
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="i-additional-include-directories"></a>/I (Zusätzliche Includeverzeichnisse)
Fügt ein Verzeichnis zur Liste der Verzeichnisse, die nach Includedateien gesucht wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
/I[ ]directory  
```  
  
## <a name="arguments"></a>Argumente  
 `directory`  
 Das Verzeichnis aus, um die Liste der Verzeichnisse hinzugefügt werden, die nach Includedateien gesucht werden.  
  
## <a name="remarks"></a>Hinweise  
 Um mehr als ein Verzeichnis hinzuzufügen, verwenden Sie diese Option mehrmals. Nur verwendet werden, bis die angegebene Includedatei gefunden wird, werden die Verzeichnisse durchsucht.  
  
 Verwenden Sie diese Option, mit der ignorieren Standard Standardincludepfad ([/x (ignorieren Standard Standardincludepfad)](../../build/reference/x-ignore-standard-include-paths.md)) Option.  
  
 Der Compiler durchsucht die Verzeichnisse in der folgenden Reihenfolge:  
  
1.  Verzeichnisse, die die Quelldatei enthält.  
  
2.  Mit angegebenen Verzeichnissen der **/i** Option in der Reihenfolge, in der CL sie gefunden wird.  
  
3.  Angegebenen Verzeichnissen der **INCLUDE** -Umgebungsvariablen angegeben.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **C/C++** .  
  
3.  Klicken Sie auf die **allgemeine** Eigenschaftenseite.  
  
4.  Ändern der **Zusätzliche Includeverzeichnisse** Eigenschaft.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalIncludeDirectories%2A>.  
  
## <a name="example"></a>Beispiel  
 Der folgende Befehl sucht die Includedateien, die von MAIN.c angefordert wird, in der folgenden Reihenfolge: zuerst in das Verzeichnis, MAIN.c, enthält, klicken Sie dann in das Verzeichnis \include"-Unterverzeichnis aus, und klicken Sie dann in das Verzeichnis \MY\INCLUDE und schließlich in den Verzeichnissen zugewiesen EINSCHLIEßEN Umgebungsvariable.  
  
```  
CL /I \INCLUDE /I\MY\INCLUDE MAIN.C  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)
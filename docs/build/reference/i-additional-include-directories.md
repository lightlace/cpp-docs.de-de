---
title: -Ich (Zusätzliche Includeverzeichnisse) | Microsoft-Dokumentation
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
ms.openlocfilehash: 506f0900cfc7ef5f84e11b2c76d4b593f81d10ba
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44109083"
---
# <a name="i-additional-include-directories"></a>/I (Zusätzliche Includeverzeichnisse)
Fügt ein Verzeichnis zur Liste der Verzeichnisse, die nach Includedateien durchsucht.

## <a name="syntax"></a>Syntax

```  
/I[ ]directory
```  

## <a name="arguments"></a>Argumente
*Verzeichnis*<br/>
Das Verzeichnis in der Liste der Verzeichnisse hinzugefügt werden, die nach Includedateien durchsucht werden.

## <a name="remarks"></a>Hinweise
Um mehr als ein Verzeichnis hinzuzufügen, verwenden Sie diese Option mehr als einmal. Verzeichnisse werden durchsucht, nur bis zum angegebenen Includedatei gefunden wird.

Sie können diese Option verwenden, mit der Standardincludepfade ignorieren ([/x (ignorieren Sie Include-Standardpfad)](../../build/reference/x-ignore-standard-include-paths.md)) Option.

Der Compiler sucht für Verzeichnisse in der folgenden Reihenfolge:

1.  Verzeichnisse, die die Quelldatei enthält.

2.  Verzeichnisse, die mit angegebenen die **/i** Option in der Reihenfolge, in der CL aufruft.

3.  Im angegebenen Verzeichnisse der **INCLUDE** -Umgebungsvariablen angegeben.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

2.  Klicken Sie auf den Ordner **C/C++** .

3.  Klicken Sie auf die **allgemeine** Eigenschaftenseite.

4.  Ändern der **Additional Include Directories** Eigenschaft.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalIncludeDirectories%2A>.

## <a name="example"></a>Beispiel
Der folgende Befehl sucht die Includedateien, die von MAIN.c angefordert wird, in der folgenden Reihenfolge: zuerst in das Verzeichnis, die dann in das Verzeichnis \include"-Unterverzeichnis aus, und klicken Sie dann in das Verzeichnis \MY\INCLUDE MAIN.c, enthält, und schließlich in den Verzeichnissen zugewiesen, die einzuschließende Umgebungsvariable.

```  
CL /I \INCLUDE /I\MY\INCLUDE MAIN.C
```  

## <a name="see-also"></a>Siehe auch
[Compileroptionen](../../build/reference/compiler-options.md)   
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)
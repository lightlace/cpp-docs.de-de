---
title: '-EP (Vorverarbeitung an "stdout" ohne #line-Direktiven) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /ep
- VC.Project.VCCLCompilerTool.GeneratePreprocessedFileNoLines
dev_langs:
- C++
helpviewer_keywords:
- copy preprocessor output to stdout
- preprocessor output, copy to stdout
- -EP compiler option [C++]
- EP compiler option [C++]
- /EP compiler option [C++]
ms.assetid: 6ec411ae-e33d-4ef5-956e-0054635eabea
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 38047fecbbd1bbaa87db3766b046efa8b446d93a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32375382"
---
# <a name="ep-preprocess-to-stdout-without-line-directives"></a>/EP (Vorverarbeitung an "stdout" ohne #line-Anweisungen)
Führt eine vorverarbeitung für C- und C++-Quelldateien und die vorverarbeiteten Dateien in das Standardausgabegerät kopiert.  
  
## <a name="syntax"></a>Syntax  
  
```  
/EP  
```  
  
## <a name="remarks"></a>Hinweise  
 In den Prozess alle Präprozessordirektiven durchgeführt werden, makroerweiterungen erfolgen und Kommentare werden entfernt. Um Kommentare in der vorverarbeiteten Ausgabedatei beizubehalten, verwenden Sie die [/c (beibehalten Kommentare beim Präprozessorlauf)](../../build/reference/c-preserve-comments-during-preprocessing.md) mit option **/EP**.  
  
 Die **/EP** Option unterdrückt die Kompilierung. Sie müssen die vorverarbeitete Datei für die Kompilierung erneut. **/ EP** unterdrückt auch die Ausgabedateien der **/FA**, **/FA**, und **/FM** Optionen. Weitere Informationen finden Sie unter [/FA, / FA (Listing File)](../../build/reference/fa-fa-listing-file.md) und [/FM (Name der Zuordnungsdatei)](../../build/reference/fm-name-mapfile.md).  
  
 Fehler bei späteren Phasen der Verarbeitung finden Sie in die Zeilennummern der vorverarbeiteten Datei statt auf die ursprüngliche Quelldatei. Verwenden Sie gegebenenfalls Zeilennummern zum Verweisen auf die ursprüngliche Quelldatei [/e (Vorverarbeitung an "stdout")](../../build/reference/e-preprocess-to-stdout.md) stattdessen. Die **/e** Option fügt `#line` Anweisungen an die Ausgabe für diesen Zweck.  
  
 Zum Senden der vorverarbeiteten Ausgabedatei mit `#line` Direktiven in eine Datei mithilfe der [/p (Vorverarbeitung in eine Datei)](../../build/reference/p-preprocess-to-a-file.md) -option von Windows.  
  
 "Stdout", mit der vorverarbeiteten Ausgabedatei an `#line` -Direktiven verwenden **/p** und **/EP** zusammen.  
  
 Sie können keine vorkompilierten Header mit dem **/EP** Option.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **C/C++** .  
  
3.  Klicken Sie auf die **Präprozessor** Eigenschaftenseite.  
  
4.  Ändern der **Präprozessorlauf** Eigenschaft.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GeneratePreprocessedFile%2A>.  
  
## <a name="example"></a>Beispiel  
 Die folgende Befehlszeile führt eine vorverarbeitung der Datei `ADD.C`behält Kommentare und das Ergebnis auf dem Standardausgabegerät angezeigt:  
  
```  
CL /EP /C ADD.C  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)
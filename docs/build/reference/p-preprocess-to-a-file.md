---
title: -P (Vorverarbeitung in eine Datei) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.GeneratePreprocessedFile
- /p
- VC.Project.VCCLWCECompilerTool.GeneratePreprocessedFile
dev_langs:
- C++
helpviewer_keywords:
- /P compiler option [C++]
- -P compiler option [C++]
- P compiler option [C++]
- output files, preprocessor
- preprocessing output files
ms.assetid: 123ee54f-8219-4a6f-9876-4227023d83fc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 26e9d2d63c7244990a047749f15273b45229c7bd
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="p-preprocess-to-a-file"></a>/P (Vorverarbeitung in eine Datei)
Führt eine vorverarbeitung für C- und C++-Quelldateien, und der vorverarbeiteten Ausgabedatei in eine Datei schreibt.  
  
## <a name="syntax"></a>Syntax  
  
```  
/P  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Datei hat den gleichen Basisnamen wie die Quelldatei und die Erweiterung trägt. In den Prozess alle Präprozessordirektiven durchgeführt werden, makroerweiterungen erfolgen und Kommentare werden entfernt. Um Kommentare in der vorverarbeiteten Ausgabedatei beizubehalten, verwenden Sie die [/c (beibehalten Kommentare beim Präprozessorlauf)](../../build/reference/c-preserve-comments-during-preprocessing.md) zusammen mit option **/p**.  
  
 **/ P** fügt `#line` Anweisungen an die Ausgabe am Anfang und Ende jeder Datei enthalten und um Linien, die von Präprozessordirektiven für die bedingte Kompilierung entfernt. Diese Direktiven nummerieren Sie die Zeilen der vorverarbeiteten Datei neu. Fehler bei späteren Phasen der Verarbeitung daher finden die Zeilennummern der ursprüngliche Quelldatei und statt der Zeilen in der vorverarbeiteten Datei. Unterdrückt die Generierung von `#line` -Direktiven verwenden [/EP (Vorverarbeitung an "stdout" ohne #line-Direktiven)](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) sowie **/p**.  
  
 Die **/p** Option unterdrückt die Kompilierung. OBJ-Datei ist nicht erzeugen, auch wenn Sie [/Fo (Name der Objektdatei)](../../build/reference/fo-object-file-name.md). Sie müssen die vorverarbeitete Datei für die Kompilierung erneut. **/ P** unterdrückt auch die Ausgabedateien der **/FA**, **/FA**, und **/FM** Optionen. Weitere Informationen finden Sie unter [/FA, / FA (Listing File)](../../build/reference/fa-fa-listing-file.md) und [/FM (Name der Zuordnungsdatei)](../../build/reference/fm-name-mapfile.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **C/C++** .  
  
3.  Klicken Sie auf die **Präprozessor** Eigenschaftenseite.  
  
4.  Ändern der **Präprozessorlauf** Eigenschaft.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GeneratePreprocessedFile%2A>.  
  
## <a name="example"></a>Beispiel  
 Die folgende Befehlszeile führt eine vorverarbeitung `ADD.C`, behält Kommentare, fügt `#line` Direktiven und das Ergebnis in eine Datei, schreibt `ADD.I`:  
  
```  
CL /P /C ADD.C  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)   
 [/Fi (Ausgabedateinamen vorverarbeiten)](../../build/reference/fi-preprocess-output-file-name.md)
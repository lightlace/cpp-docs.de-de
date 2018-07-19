---
title: -E (Vorverarbeitung an "stdout") | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /e
dev_langs:
- C++
helpviewer_keywords:
- -E compiler option [C++]
- /E compiler option [C++]
- preprocessor output, copy to stdout
- preprocessor output
ms.assetid: ddbb1725-d950-4978-ab2f-30a5cd7b778c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3f9105c5c75bc4695d0b00debdff49acf78690b1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32376913"
---
# <a name="e-preprocess-to-stdout"></a>/E (Vorverarbeitung an "stdout")
Führt eine vorverarbeitung für C- und C++-Quelldateien und die vorverarbeiteten Dateien in das Standardausgabegerät kopiert.  
  
## <a name="syntax"></a>Syntax  
  
```  
/E  
```  
  
## <a name="remarks"></a>Hinweise  
 In diesem Prozess alle Präprozessordirektiven durchgeführt werden, makroerweiterungen erfolgen und Kommentare werden entfernt. Um Kommentare in der vorverarbeiteten Ausgabedatei beizubehalten, verwenden Sie die [/c (beibehalten Kommentare beim Präprozessorlauf)](../../build/reference/c-preserve-comments-during-preprocessing.md) sowie-Compileroption.  
  
 **/ E** fügt `#line` Direktive, um die Ausgabe am Anfang und Ende jeder Datei enthalten und um Linien, die von Präprozessordirektiven für die bedingte Kompilierung entfernt. Diese Direktiven nummerieren Sie die Zeilen der vorverarbeiteten Datei neu. Fehler bei späteren Phasen der Verarbeitung daher finden die Zeilennummern der ursprüngliche Quelldatei und statt der Zeilen in der vorverarbeiteten Datei.  
  
 Die **/e** Option unterdrückt die Kompilierung. Sie müssen die vorverarbeitete Datei für die Kompilierung erneut. **/ E** unterdrückt auch die Ausgabedateien der **/FA**, **/FA**, und **/FM** Optionen. Weitere Informationen finden Sie unter [/FA, / FA (Listing File)](../../build/reference/fa-fa-listing-file.md) und [/FM (Name der Zuordnungsdatei)](../../build/reference/fm-name-mapfile.md).  
  
 Unterdrückt `#line` Direktiven, verwenden die [/EP (Vorverarbeitung an "stdout" ohne #line-Direktiven)](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) -option von Windows.  
  
 Eine Datei statt auf der vorverarbeiteten Ausgabedatei an `stdout`, verwenden Sie die [/p (Vorverarbeitung in eine Datei)](../../build/reference/p-preprocess-to-a-file.md) -option von Windows.  
  
 Unterdrückt `#line` Direktiven und der vorverarbeiteten Ausgabe in eine Datei verwenden **/p** und **/EP** zusammen.  
  
 Sie können keine vorkompilierten Header mit dem **/e** Option.  
  
 Beachten Sie, dass bei der vorverarbeitung in eine separate Datei Leerzeichen nicht nach Token ausgegeben werden. Dies kann in einem ungültigen Programm führen oder unbeabsichtigte Nebeneffekte. Das folgende Programm wird erfolgreich kompiliert:  
  
```  
#define m(x) x  
m(int)main( )  
{  
   return 0;  
}  
```  
  
 Allerdings beim Kompilieren mit:  
  
```  
cl -E test.cpp > test2.cpp  
```  
  
 `int main` in test2.cpp werden falsch `intmain`.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **C/C++** .  
  
3.  Klicken Sie auf die Eigenschaftenseite **Befehlszeile** .  
  
4.  Geben Sie die Compileroption in der **Zusatzoptionen**Feld.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GeneratePreprocessedFile%2A>.  
  
## <a name="example"></a>Beispiel  
 Die folgende Befehlszeile führt eine vorverarbeitung `ADD.C`, behält Kommentare, fügt `#line` Direktiven und das Ergebnis auf dem Standardausgabegerät angezeigt:  
  
```  
CL /E /C ADD.C  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)
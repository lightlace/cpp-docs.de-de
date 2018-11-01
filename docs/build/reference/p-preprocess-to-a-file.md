---
title: /P (Vorverarbeitung in eine Datei)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.GeneratePreprocessedFile
- /p
- VC.Project.VCCLWCECompilerTool.GeneratePreprocessedFile
helpviewer_keywords:
- /P compiler option [C++]
- -P compiler option [C++]
- P compiler option [C++]
- output files, preprocessor
- preprocessing output files
ms.assetid: 123ee54f-8219-4a6f-9876-4227023d83fc
ms.openlocfilehash: 9b3d84d94ed75acd68011b895afbc4f190019673
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50622235"
---
# <a name="p-preprocess-to-a-file"></a>/P (Vorverarbeitung in eine Datei)

C- und C++-Quelldateien vorverarbeitet, und schreibt die vorverarbeitete Ausgabe in eine Datei.

## <a name="syntax"></a>Syntax

```
/P
```

## <a name="remarks"></a>Hinweise

Die Datei hat den gleichen Basisnamen wie die Quelldatei und die Erweiterung fügen. Im Prozess alle Präprozessordirektiven durchgeführt werden, makroerweiterungen werden ausgeführt und Kommentare werden entfernt. Um Kommentare in die vorverarbeitete Ausgabe beizubehalten, verwenden Sie die [/c (beibehalten der bei der Vorverarbeitung Kommentare)](../../build/reference/c-preserve-comments-during-preprocessing.md) -Option zusammen mit **/p**.

**/ P** fügt `#line` Anweisungen für die Ausgabe am Anfang und Ende jeder Datei enthalten und um Linien, die von präprozessoranweisungen für die bedingte Kompilierung entfernt. Diese Direktiven nummerieren Sie die Zeilen der vorverarbeiteten Datei neu. Daher finden Sie Fehler, die in späteren Phasen der Verarbeitung generiert die Zeilennummern der ursprünglichen Quelldatei anstelle von Zeilen in der vorverarbeiteten Datei. Unterdrückt die Generierung von `#line` -Anweisungen verwenden [/EP (Vorverarbeitung an "stdout" ohne #line-Anweisungen)](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) sowie **/p**.

Die **/p** Option unterdrückt die Kompilierung. Er wird keine OBJ-Datei erzeugt, auch wenn Sie [/Fo (Name der Objektdatei)](../../build/reference/fo-object-file-name.md). Sie müssen die vorverarbeitete Datei für die Kompilierung erneut. **/ P** unterdrückt auch die Ausgabedateien von dem **/FA**, **/FA**, und **/FM** Optionen. Weitere Informationen finden Sie unter [/FA, / FA (Listendatei)](../../build/reference/fa-fa-listing-file.md) und [/FM (Name der Zuordnungsdatei)](../../build/reference/fm-name-mapfile.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Klicken Sie auf den Ordner **C/C++** .

1. Klicken Sie auf die **Präprozessor** Eigenschaftenseite.

1. Ändern der **Präprozessorlauf** Eigenschaft.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GeneratePreprocessedFile%2A>.

## <a name="example"></a>Beispiel

Die folgende Befehlszeile führt eine vorverarbeitung `ADD.C`, behält Kommentare, fügt `#line` -Direktiven und das Ergebnis in eine Datei, schreibt `ADD.I`:

```
CL /P /C ADD.C
```

## <a name="see-also"></a>Siehe auch

[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)<br/>
[/Fi (Ausgabedateinamen vorverarbeiten)](../../build/reference/fi-preprocess-output-file-name.md)
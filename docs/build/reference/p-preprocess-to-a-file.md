---
title: -P (Vorverarbeitung in eine Datei) | Microsoft-Dokumentation
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
ms.openlocfilehash: 4cbec53526fe90d1b4644b5b9fdd667d0fffcbe8
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45714505"
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
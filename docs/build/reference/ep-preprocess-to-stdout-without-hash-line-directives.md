---
title: '/EP (Vorverarbeitung an "stdout" ohne #line-Anweisungen)'
ms.date: 11/04/2016
f1_keywords:
- /ep
- VC.Project.VCCLCompilerTool.GeneratePreprocessedFileNoLines
helpviewer_keywords:
- copy preprocessor output to stdout
- preprocessor output, copy to stdout
- -EP compiler option [C++]
- EP compiler option [C++]
- /EP compiler option [C++]
ms.assetid: 6ec411ae-e33d-4ef5-956e-0054635eabea
ms.openlocfilehash: 49745b644234c0e5ce92661f14304531aaca5c69
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57807334"
---
# <a name="ep-preprocess-to-stdout-without-line-directives"></a>/EP (Vorverarbeitung an "stdout" ohne #line-Anweisungen)

C- und C++-Quelldateien vorverarbeitet, und die vorverarbeiteten Dateien in das Standardausgabegerät kopiert.

## <a name="syntax"></a>Syntax

```
/EP
```

## <a name="remarks"></a>Hinweise

Im Prozess alle Präprozessordirektiven durchgeführt werden, makroerweiterungen werden ausgeführt und Kommentare werden entfernt. Um Kommentare in die vorverarbeitete Ausgabe beizubehalten, verwenden Sie die [/c (beibehalten der bei der Vorverarbeitung Kommentare)](c-preserve-comments-during-preprocessing.md) mit option **/EP**.

Die **/EP** Option unterdrückt die Kompilierung. Sie müssen die vorverarbeitete Datei für die Kompilierung erneut. **/ EP** unterdrückt auch die Ausgabedateien von dem **/FA**, **/FA**, und **/FM** Optionen. Weitere Informationen finden Sie unter [/FA, / FA (Listendatei)](fa-fa-listing-file.md) und [/FM (Name der Zuordnungsdatei)](fm-name-mapfile.md).

Fehler bei der späteren Phasen der Verarbeitung finden Sie in die Zeilennummern der vorverarbeiteten Datei statt auf die ursprüngliche Quelldatei. Wenn Sie Zeilennummern, um auf die ursprüngliche Quelldatei verweisen möchten, verwenden Sie [/e (Vorverarbeitung an "stdout")](e-preprocess-to-stdout.md) stattdessen. Die **/e** Option fügt `#line` Anweisungen an die Ausgabe für diesen Zweck.

Senden Sie die vorverarbeitete Ausgabe mit `#line` verwenden Sie die Anweisungen in eine Datei, die [/p (Vorverarbeitung in eine Datei)](p-preprocess-to-a-file.md) option.

Senden Sie die vorverarbeitete Ausgabe an "stdout", mit `#line` -Anweisungen verwenden **/p** und **/EP** zusammen.

Sie können keine vorkompilierten Header mit dem **/EP** Option.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Klicken Sie auf den Ordner **C/C++** .

1. Klicken Sie auf die **Präprozessor** Eigenschaftenseite.

1. Ändern der **Präprozessorlauf** Eigenschaft.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GeneratePreprocessedFile%2A>.

## <a name="example"></a>Beispiel

Die folgende Befehlszeile führt eine vorverarbeitung Datei `ADD.C`behält Kommentare und zeigt das Ergebnis auf das Standardausgabegerät:

```
CL /EP /C ADD.C
```

## <a name="see-also"></a>Siehe auch

[MSVC-Compiler-Optionen](compiler-options.md)<br/>
[MSVC-Compiler-Befehlszeilensyntax](compiler-command-line-syntax.md)

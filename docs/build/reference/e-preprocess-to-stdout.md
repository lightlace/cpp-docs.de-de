---
title: /E (Vorverarbeitung an "stdout")
ms.date: 11/04/2016
f1_keywords:
- /e
helpviewer_keywords:
- -E compiler option [C++]
- /E compiler option [C++]
- preprocessor output, copy to stdout
- preprocessor output
ms.assetid: ddbb1725-d950-4978-ab2f-30a5cd7b778c
ms.openlocfilehash: 892203d300c07711d06cff602128ec6e9ceb351c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50504572"
---
# <a name="e-preprocess-to-stdout"></a>/E (Vorverarbeitung an "stdout")

C- und C++-Quelldateien vorverarbeitet, und die vorverarbeiteten Dateien in das Standardausgabegerät kopiert.

## <a name="syntax"></a>Syntax

```
/E
```

## <a name="remarks"></a>Hinweise

In diesem Prozess alle Präprozessordirektiven durchgeführt werden, makroerweiterungen werden ausgeführt und Kommentare werden entfernt. Um Kommentare in die vorverarbeitete Ausgabe beizubehalten, verwenden Sie die [/c (beibehalten der bei der Vorverarbeitung Kommentare)](../../build/reference/c-preserve-comments-during-preprocessing.md) auch die Compileroption.

**/ E** fügt `#line` Anweisungen für die Ausgabe am Anfang und Ende jeder Datei enthalten und um Linien, die von präprozessoranweisungen für die bedingte Kompilierung entfernt. Diese Direktiven nummerieren Sie die Zeilen der vorverarbeiteten Datei neu. Daher finden Sie Fehler, die in späteren Phasen der Verarbeitung generiert die Zeilennummern der ursprünglichen Quelldatei anstelle von Zeilen in der vorverarbeiteten Datei.

Die **/e** Option unterdrückt die Kompilierung. Sie müssen die vorverarbeitete Datei für die Kompilierung erneut. **/ E** unterdrückt auch die Ausgabedateien von dem **/FA**, **/FA**, und **/FM** Optionen. Weitere Informationen finden Sie unter [/FA, / FA (Listendatei)](../../build/reference/fa-fa-listing-file.md) und [/FM (Name der Zuordnungsdatei)](../../build/reference/fm-name-mapfile.md).

Unterdrückt `#line` -Anweisungen verwenden die [/EP (Vorverarbeitung an "stdout" ohne #line-Anweisungen)](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) option.

Senden Sie die vorverarbeitete Ausgabe in eine Datei statt auf `stdout`, verwenden Sie die [/p (Vorverarbeitung in eine Datei)](../../build/reference/p-preprocess-to-a-file.md) option.

Unterdrückt `#line` verwenden Sie die Anweisungen und senden die vorverarbeitete Ausgabe in eine Datei, **/p** und **/EP** zusammen.

Sie können keine vorkompilierten Header mit dem **/e** Option.

Beachten Sie, dass bei der vorverarbeitung in eine separate Datei Leerzeichen nicht nach dem Token ausgegeben werden. Dies kann dazu führen, in einem ungültigen Programm oder haben unerwünschte Nebeneffekte. Das folgende Programm kompiliert erfolgreich:

```
#define m(x) x
m(int)main( )
{
   return 0;
}
```

Allerdings bei der Kompilierung mit:

```
cl -E test.cpp > test2.cpp
```

`int main` in test2.cpp werden falsch `intmain`.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Klicken Sie auf den Ordner **C/C++** .

1. Klicken Sie auf die Eigenschaftenseite **Befehlszeile** .

1. Geben Sie die Compileroption in der **zusätzliche Optionen**Feld.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GeneratePreprocessedFile%2A>.

## <a name="example"></a>Beispiel

Die folgende Befehlszeile führt eine vorverarbeitung `ADD.C`, behält Kommentare, fügt `#line` -Anweisungen und das Ergebnis in das Standardausgabegerät angezeigt:

```
CL /E /C ADD.C
```

## <a name="see-also"></a>Siehe auch

[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)
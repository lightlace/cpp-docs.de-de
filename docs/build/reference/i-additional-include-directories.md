---
title: / I (Zusätzliche Includeverzeichnisse)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLWCECompilerTool.AdditionalIncludeDirectories
- VC.Project.VCCLCompilerTool.AdditionalIncludeDirectories
- /I
- VC.Project.VCNMakeTool.IncludeSearchPath
helpviewer_keywords:
- /I compiler option [C++]
- Additional Include Directories compiler option
- I compiler option [C++]
- -I compiler option [C++]
- set include directories
- include directories, compiler option [C++]
ms.assetid: 3e9add2a-5ed8-4d15-ad79-5b411e313a49
ms.openlocfilehash: 6ec8b15e77fec5214013c484e617904ed29e8197
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62270141"
---
# <a name="i-additional-include-directories"></a>/ I (Zusätzliche Includeverzeichnisse)

Fügt ein Verzeichnis zur Liste der Verzeichnisse, die nach Includedateien durchsucht.

## <a name="syntax"></a>Syntax

> **/ I**[]*Verzeichnis*

### <a name="arguments"></a>Argumente

*directory*<br/>
Das Verzeichnis in der Liste der Verzeichnisse hinzugefügt werden, die nach Includedateien durchsucht werden.

## <a name="remarks"></a>Hinweise

Um mehr als ein Verzeichnis hinzuzufügen, verwenden Sie diese Option mehr als einmal. Verzeichnisse werden durchsucht, nur bis zum angegebenen Includedatei gefunden wird.

Können Sie diese Option mit dem ([/x (ignorieren Sie Include-Standardpfad)](x-ignore-standard-include-paths.md)) Option.

Der Compiler sucht Verzeichnisse, in der folgenden Reihenfolge:

1. Wenn angegeben, mit einem [#include-Direktive](../../preprocessor/hash-include-directive-c-cpp.md) in doppelte Anführungszeichen Form sucht zuerst lokale Verzeichnisse. Die Suche beginnt im selben Verzeichnis wie die Datei mit den **#include** Anweisung. Wenn dies fehlschlägt, um die Datei nicht finden, durchsucht es in die Verzeichnissen der aktuell geöffneten Includedateien in umgekehrter Reihenfolge, in dem sie geöffnet wurden. Die Suche beginnt im Verzeichnis der übergeordneten Includedatei und wird nach oben durch die Verzeichnisse aller Includedateien der zweiten übergeordneten Ebene fortgesetzt.

1. Wenn angegeben, mit einem **#include** -Direktive in spitzen Klammern Formular aus, oder wenn die Suche im lokalen Verzeichnis fehlgeschlagen ist, sucht er angegebene Verzeichnissen mithilfe der **/i** Option in der Reihenfolge, in der CL aufruft in der Befehlszeile.

1. Im angegebenen Verzeichnisse der **INCLUDE** -Umgebungsvariablen angegeben.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **allgemeine** Eigenschaftenseite.

1. Ändern der **Additional Include Directories** Eigenschaft.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalIncludeDirectories%2A>.

## <a name="example"></a>Beispiel

Der folgende Befehl sucht nach den Include-Dateien, die von MAIN.c angefordert wird, in der folgenden Reihenfolge: Wenn es sich bei mit doppelten Anführungszeichen angegeben, werden zuerst lokale Dateien durchsucht. Als Nächstes Suche wird fortgesetzt, im Verzeichnis \include"-Unterverzeichnis aus, und klicken Sie dann in das Verzeichnis \MY\INCLUDE und zugewiesen schließlich in den Verzeichnissen INCLUDE-Umgebungsvariable.

```
CL /I \INCLUDE /I\MY\INCLUDE MAIN.C
```

## <a name="see-also"></a>Siehe auch

[MSVC-Compileroptionen](compiler-options.md)<br/>
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)

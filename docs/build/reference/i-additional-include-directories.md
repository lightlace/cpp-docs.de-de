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
ms.openlocfilehash: 0dc1769924880d8cb1b5dc173dd614e87584cac9
ms.sourcegitcommit: 45835842604602a011813d0cd70abc5df91b89ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2018
ms.locfileid: "50750391"
---
# <a name="i-additional-include-directories"></a>/ I (Zusätzliche Includeverzeichnisse)

Fügt ein Verzeichnis zur Liste der Verzeichnisse, die nach Includedateien durchsucht.

## <a name="syntax"></a>Syntax

> **/ I**[]*Verzeichnis*

### <a name="arguments"></a>Argumente

*Verzeichnis*<br/>
Das Verzeichnis in der Liste der Verzeichnisse hinzugefügt werden, die nach Includedateien durchsucht werden.

## <a name="remarks"></a>Hinweise

Um mehr als ein Verzeichnis hinzuzufügen, verwenden Sie diese Option mehr als einmal. Verzeichnisse werden durchsucht, nur bis zum angegebenen Includedatei gefunden wird.

Können Sie diese Option mit dem ([/x (ignorieren Sie Include-Standardpfad)](../../build/reference/x-ignore-standard-include-paths.md)) Option.

Der Compiler sucht Verzeichnisse, in der folgenden Reihenfolge:

1. Wenn angegeben, mit einem [#include-Direktive](../../preprocessor/hash-include-directive-c-cpp.md) in doppelte Anführungszeichen Form sucht zuerst lokale Verzeichnisse. Die Suche beginnt im selben Verzeichnis wie die Datei mit den **#include** Anweisung. Wenn dies fehlschlägt, um die Datei nicht finden, durchsucht es in die Verzeichnissen der aktuell geöffneten Includedateien in umgekehrter Reihenfolge, in dem sie geöffnet wurden. Die Suche beginnt im Verzeichnis der übergeordneten Includedatei und wird nach oben durch die Verzeichnisse aller Includedateien der zweiten übergeordneten Ebene fortgesetzt.

1. Wenn angegeben, mit einem **#include** -Direktive in spitzen Klammern Formular aus, oder wenn die Suche im lokalen Verzeichnis fehlgeschlagen ist, sucht er angegebene Verzeichnissen mithilfe der **/i** Option in der Reihenfolge, in der CL aufruft in der Befehlszeile.

1. Im angegebenen Verzeichnisse der **INCLUDE** -Umgebungsvariablen angegeben.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **allgemeine** Eigenschaftenseite.

1. Ändern der **Additional Include Directories** Eigenschaft.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalIncludeDirectories%2A>.

## <a name="example"></a>Beispiel

Der folgende Befehl sucht die Includedateien, die von MAIN.c angefordert wird, in der folgenden Reihenfolge: zuerst, wenn es sich bei mit doppelten Anführungszeichen angegeben, lokale Dateien werden durchsucht. Als Nächstes Suche wird fortgesetzt, im Verzeichnis \include"-Unterverzeichnis aus, und klicken Sie dann in das Verzeichnis \MY\INCLUDE und zugewiesen schließlich in den Verzeichnissen INCLUDE-Umgebungsvariable.

```
CL /I \INCLUDE /I\MY\INCLUDE MAIN.C
```

## <a name="see-also"></a>Siehe auch

[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)
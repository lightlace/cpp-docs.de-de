---
title: /doc (Verarbeiten von Dokumentationskommentaren) (C/C++)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.GenerateXMLDocumentationFiles
- /doc
- VC.Project.VCCLCompilerTool.XMLDocumentationFileName
helpviewer_keywords:
- /doc compiler option [C++]
- comments, C++ code
- XML documentation, comments in source files
- -doc compiler option [C++]
ms.assetid: b54f7e2c-f28f-4f46-9ed6-0db09be2cc63
ms.openlocfilehash: 39b614b1ab21a654a35e30b0d3acffa15d244fb0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50530038"
---
# <a name="doc-process-documentation-comments-cc"></a>/doc (Verarbeiten von Dokumentationskommentaren) (C/C++)

Bewirkt, dass den Compiler Dokumentationskommentare in Quellcodedateien und eine XDC-Datei für jede Quellcodedatei zu erstellen, die Dokumentationskommentare enthält.

## <a name="syntax"></a>Syntax

> **/ doc**[*Namen*]

## <a name="arguments"></a>Argumente

*name*<br/>
Der Name der XDC-Datei, die der Compiler erstellt. Nur gültig, wenn eine CPP-Datei in der Kompilierung übergeben wird.

## <a name="remarks"></a>Hinweise

Die XDC-Dateien werden in eine XML-Datei mit xdcmake.exe verarbeitet. Weitere Informationen finden Sie unter [XDCMake-Verweis](../../ide/xdcmake-reference.md).

Sie können Ihre Quellcodedateien Dokumentationskommentare hinzufügen. Weitere Informationen finden Sie unter [Empfohlene Tags für Dokumentationskommentare](../../ide/recommended-tags-for-documentation-comments-visual-cpp.md).

Um die generierte XML-Datei mit IntelliSense zu verwenden, stellen Sie den Dateinamen der XML-Datei der Assembly, die Sie verwenden möchten, unterstützen, und legen Sie die XML-Datei im gleichen Verzeichnis wie die Assembly übereinstimmt. Wenn die Assembly in Visual Studio-Projekt verwiesen wird, wird auch die XML-Datei gefunden. Weitere Informationen finden Sie unter [Verwenden von IntelliSense](/visualstudio/ide/using-intellisense) und [Anzeigen von XML-Codekommentaren](/visualstudio/ide/supplying-xml-code-comments).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **Ausgabedateien** Eigenschaftenseite.

1. Ändern der **XML-Dokumentationsdateien generieren** Eigenschaft.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GenerateXMLDocumentationFiles%2A>.

## <a name="see-also"></a>Siehe auch

[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)
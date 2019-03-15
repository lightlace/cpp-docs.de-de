---
title: /AI (Metadatenverzeichnisse festlegen)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.AdditionalUsingDirectories
- VC.Project.VCNMakeTool.AssemblySearchPath
- /AI
- VC.Project.VCCLWCECompilerTool.AdditionalUsingDirectories
helpviewer_keywords:
- /AI compiler option [C++]
- AI compiler option [C++]
- -AI compiler option [C++]
ms.assetid: fb9c1846-504c-4a3b-bb39-c8696de32f6f
ms.openlocfilehash: 3633cfe34a4f9c627f84cf401cb559f02f8c8229
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57810210"
---
# <a name="ai-specify-metadata-directories"></a>/AI (Metadatenverzeichnisse festlegen)

Gibt ein Verzeichnis an, das der Compiler durchsucht, um Dateiverweise aufzulösen, die an die `#using`-Anweisung übergeben wurden.

## <a name="syntax"></a>Syntax

> **/AI**_directory_

## <a name="arguments"></a>Argumente

*directory*<br/>
Das Verzeichnis oder der Pfad, den der Compiler durchsuchen soll.

## <a name="remarks"></a>Hinweise

Nur ein Verzeichnis übergeben werden kann, um eine **/AI** aufrufen. Geben Sie einen **/AI** -Option für jeden Pfad, den der Compiler durchsuchen soll. Um beispielsweise dem compilersuchpfad für sowohl C:\Project\Meta als auch C:\Common\Meta hinzufügen `#using` Hinzufügen von Direktiven, `/AI"C:\Project\Meta" /AI"C:\Common\Meta"` an der Befehlszeile des Compilers oder jedes Verzeichnis zum Hinzufügen der **zusätzliche #using Verzeichnisse** die Eigenschaft in Visual Studio.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **allgemeine** Eigenschaftenseite.

1. Ändern der **zusätzliche #using using Verzeichnisse** Eigenschaft.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalUsingDirectories%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Compiler-Optionen](compiler-options.md)<br/>
[MSVC-Compiler-Befehlszeilensyntax](compiler-command-line-syntax.md)<br/>
[#using-Direktive](../../preprocessor/hash-using-directive-cpp.md)

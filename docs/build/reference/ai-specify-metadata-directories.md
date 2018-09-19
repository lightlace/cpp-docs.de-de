---
title: -AI (Metadatenverzeichnisse festlegen) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.AdditionalUsingDirectories
- VC.Project.VCNMakeTool.AssemblySearchPath
- /AI
- VC.Project.VCCLWCECompilerTool.AdditionalUsingDirectories
dev_langs:
- C++
helpviewer_keywords:
- /AI compiler option [C++]
- AI compiler option [C++]
- -AI compiler option [C++]
ms.assetid: fb9c1846-504c-4a3b-bb39-c8696de32f6f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 985ff4eb96b904dc9c5b4377b336109b00e06b40
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45716587"
---
# <a name="ai-specify-metadata-directories"></a>/AI (Metadatenverzeichnisse festlegen)

Gibt ein Verzeichnis an, das der Compiler durchsucht, um Dateiverweise aufzulösen, die an die `#using`-Direktive übergeben wurden.

## <a name="syntax"></a>Syntax

> **/ AI**_Verzeichnis_

## <a name="arguments"></a>Argumente

*Verzeichnis*<br/>
Das Verzeichnis oder der Pfad, den der Compiler durchsuchen soll.

## <a name="remarks"></a>Hinweise

Nur ein Verzeichnis übergeben werden kann, um eine **/AI** aufrufen. Geben Sie einen **/AI** -Option für jeden Pfad, den der Compiler durchsuchen soll. Um beispielsweise dem compilersuchpfad für sowohl C:\Project\Meta als auch C:\Common\Meta hinzufügen `#using` Hinzufügen von Direktiven, `/AI"C:\Project\Meta" /AI"C:\Common\Meta"` an der Befehlszeile des Compilers oder jedes Verzeichnis zum Hinzufügen der **zusätzliche #using Verzeichnisse** die Eigenschaft in Visual Studio.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

2. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **allgemeine** Eigenschaftenseite.

3. Ändern der **zusätzliche #using using Verzeichnisse** Eigenschaft.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalUsingDirectories%2A>.

## <a name="see-also"></a>Siehe auch

[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)<br/>
[#using-Direktive](../../preprocessor/hash-using-directive-cpp.md)
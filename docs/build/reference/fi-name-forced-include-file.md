---
title: /FI (Name der expliziten Includedatei)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCNMakeTool.ForcedIncludes
- VC.Project.VCCLCompilerTool.ForcedIncludeFiles
- VC.Project.VCCLWCECompilerTool.ForcedIncludeFiles
- /fi
helpviewer_keywords:
- FI compiler option [C++]
- -FI compiler option [C++]
- /FI compiler option [C++]
- preprocess header file compiler option [C++]
ms.assetid: 07e79577-8152-4df9-a64c-aae08c603397
ms.openlocfilehash: b91ca1ba6cc97157be0ab16fc18e065dc501d5fd
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57422467"
---
# <a name="fi-name-forced-include-file"></a>/FI (Name der expliziten Includedatei)

Weist den Präprozessor zum Verarbeiten der angegebenen Header-Datei.

## <a name="syntax"></a>Syntax

```
/FI[ ]pathname
```

## <a name="remarks"></a>Hinweise

Diese Option hat dieselbe Wirkung wie die Datei angeben, in doppelte Anführungszeichen in eine `#include` -Direktive in der ersten Zeile von jeder Quelldatei, die in der Befehlszeile oder in einer Befehlsdatei in der CL-Umgebungsvariablen angegeben. Bei Verwendung mehrerer **/Fi** Optionen, die Dateien befinden sich in der Reihenfolge von CL verarbeitet werden.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Klicken Sie auf den Ordner **C/C++** .

1. Klicken Sie auf die **erweitert** Eigenschaftenseite.

1. Ändern der **Includes erzwingen** Eigenschaft.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ForcedIncludeFiles%2A>.

## <a name="see-also"></a>Siehe auch

[Ausgabedatei (/F) Optionen](../../build/reference/output-file-f-options.md)<br/>
[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)<br/>
[Festlegen des Pfadnamens](../../build/reference/specifying-the-pathname.md)

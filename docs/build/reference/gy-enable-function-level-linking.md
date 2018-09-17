---
title: -Gy (Funktionslevel-Linking aktivieren) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.EnableFunctionLevelLinking
- /gy
- VC.Project.VCCLWCECompilerTool.EnableFunctionLevelLinking
dev_langs:
- C++
helpviewer_keywords:
- enable function-level linking compiler option [C++]
- COMDAT function
- Gy compiler option [C++]
- -Gy compiler option [C++]
- /Gy compiler option [C++]
- packaged functions
ms.assetid: 0d3cf14c-ed7d-4ad3-b4b6-104e56f61046
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 09faa1a1d2b6743b7fce31af32ba4fe1572b592e
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45705002"
---
# <a name="gy-enable-function-level-linking"></a>/Gy (Funktionslevel-Linking aktivieren)

Ermöglicht dem Compiler, einzelne Funktionen in Form von kompilierten Funktionen (COMDATs) zu kompilieren.

## <a name="syntax"></a>Syntax

```
/Gy[-]
```

## <a name="remarks"></a>Hinweise

Der Linker ist erforderlich, dass Funktionen separat als COMDATs ausgeschlossen oder bestellen einzelne Funktionen in einer DLL oder .exe-Datei verpackt werden.

Sie können die Linkeroption [/OPT (Optimierungen)](../../build/reference/opt-optimizations.md) , die .exe-Datei nicht referenzierte Paketfunktionen ausgeschlossen werden sollen.

Sie können die Linkeroption [/Order (Put-Funktionen in Reihenfolge)](../../build/reference/order-put-functions-in-order.md) Paketfunktionen in einer bestimmten Reihenfolge in die .exe-Datei eingeschlossen.

Inline-Funktionen sind immer verpackt, wenn sie als Aufrufe instanziiert werden (Dies geschieht z. B. wenn inlining ist deaktiviert oder eine Funktionsadresse). Darüber hinaus werden in der Klassendeklaration definierte C++-Memberfunktionen automatisch gepackt; andere Funktionen sind nicht, und nach Auswahl dieser Option ist erforderlich, um sie als Paketfunktionen kompilieren.

> [!NOTE]
>  Die ["/ Zi"](../../build/reference/z7-zi-zi-debug-information-format.md) -Option zum Bearbeiten und fortfahren, setzt automatisch das **/Gy** Option.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Klicken Sie auf den Ordner **C/C++** .

1. Klicken Sie auf die **Codegenerierung** Eigenschaftenseite.

1. Ändern der **Funktionslevel-Linking aktivieren** Eigenschaft.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableFunctionLevelLinking%2A>.

## <a name="see-also"></a>Siehe auch

[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)
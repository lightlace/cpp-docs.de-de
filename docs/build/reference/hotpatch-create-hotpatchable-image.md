---
title: /hotpatch (Erstellen eines Hotpatch-fähigen Abbildes)
ms.date: 11/04/2016
f1_keywords:
- /hotpatch
- VC.Project.VCCLCompilerTool.CreateHotpatchableImage
helpviewer_keywords:
- hot patching
- -hotpatch compiler option [C++]
- /hotpatch compiler option [C++]
- hotpatching
ms.assetid: aad539b6-c053-4c78-8682-853d98327798
ms.openlocfilehash: b304edffc024fac084338789134269745111ba00
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50581440"
---
# <a name="hotpatch-create-hotpatchable-image"></a>/hotpatch (Erstellen eines Hotpatch-fähigen Abbildes)

Bereitet ein Image für Hotpatching vor.

## <a name="syntax"></a>Syntax

```
/hotpatch
```

## <a name="remarks"></a>Hinweise

Wenn **/hotpatch** wird verwendet, bei einer Kompilierung muss der Compiler stellt sicher, dass die erste Anweisung jeder Funktion mindestens zwei Byte umfasst, was für HotPatching erforderlich ist.

Zum Abschließen der Vorbereitung für eine hotpatchfähiges Image erstellen, nach der Verwendung von **/hotpatch** zum Kompilieren, müssen Sie verwenden [/FUNCTIONPADMIN (Erstellen eines Hotpatch-fähigen Abbildes)](../../build/reference/functionpadmin-create-hotpatchable-image.md) verknüpfen. Wenn Sie kompilieren und verknüpfen ein Bild mit einem Aufruf von cl.exe, **/hotpatch** impliziert **/functionpadmin**.

Da Anweisungen immer zwei Bytes sind oder mehr in der ARM-Architektur, und da X64 Kompilierung immer so als ob **/hotpatch** angegeben wurde, müssen Sie nicht angeben **/hotpatch** bei Sie Kompilieren für diese Ziele; Allerdings müssen Sie immer noch eine Verknüpfung mit **/functionpadmin** hotpatchfähige Images für sie erstellen. Die **/hotpatch** Compiler-Option nur wirkt sich auf X86 Kompilierung.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Wählen Sie die **C/C++-** Ordner.

1. Wählen Sie die **Befehlszeile** Eigenschaftenseite.

1. Fügen Sie die Compileroption, um die **zusätzliche Optionen** Feld.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="guidance"></a>Empfehlungen

Weitere Informationen zu aktualisierungsverwaltung finden Sie unter "Security Guidance for Update Management" [ http://www.microsoft.com/technet/security/guidance/PatchManagement.mspx ](http://www.microsoft.com/technet/security/guidance/PatchManagement.mspx).

## <a name="see-also"></a>Siehe auch

[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)
---
title: /hotpatch (Erstellen eines Hotpatch-fähigen Abbildes)
ms.date: 11/12/2018
f1_keywords:
- /hotpatch
- VC.Project.VCCLCompilerTool.CreateHotpatchableImage
helpviewer_keywords:
- hot patching
- -hotpatch compiler option [C++]
- /hotpatch compiler option [C++]
- hotpatching
ms.assetid: aad539b6-c053-4c78-8682-853d98327798
ms.openlocfilehash: 8830b26b8fdfc3db2aa5fe31a52e6226fd554946
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57807480"
---
# <a name="hotpatch-create-hotpatchable-image"></a>/hotpatch (Erstellen eines Hotpatch-fähigen Abbildes)

Bereitet ein Image für Hotpatching vor.

## <a name="syntax"></a>Syntax

```
/hotpatch
```

## <a name="remarks"></a>Hinweise

Wenn **/hotpatch** wird verwendet, bei einer Kompilierung muss der Compiler stellt sicher, dass die erste Anweisung jeder Funktion mindestens zwei Byte umfasst, was für HotPatching erforderlich ist.

Zum Abschließen der Vorbereitung für eine hotpatchfähiges Image erstellen, nach der Verwendung von **/hotpatch** zum Kompilieren, müssen Sie verwenden [/FUNCTIONPADMIN (Erstellen eines Hotpatch-fähigen Abbildes)](functionpadmin-create-hotpatchable-image.md) verknüpfen. Wenn Sie kompilieren und verknüpfen ein Bild mit einem Aufruf von cl.exe, **/hotpatch** impliziert **/functionpadmin**.

Da Anweisungen immer zwei Bytes sind oder mehr in der ARM-Architektur, und da X64 Kompilierung immer so als ob **/hotpatch** angegeben wurde, müssen Sie nicht angeben **/hotpatch** bei Sie Kompilieren für diese Ziele; Allerdings müssen Sie immer noch eine Verknüpfung mit **/functionpadmin** hotpatchfähige Images für sie erstellen. Die **/hotpatch** Compiler-Option nur wirkt sich auf X86 Kompilierung.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Wählen Sie die **C/C++-** Ordner.

1. Wählen Sie die **Befehlszeile** Eigenschaftenseite.

1. Fügen Sie die Compileroption, um die **zusätzliche Optionen** Feld.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Compiler-Optionen](compiler-options.md)<br/>
[MSVC-Compiler-Befehlszeilensyntax](compiler-command-line-syntax.md)

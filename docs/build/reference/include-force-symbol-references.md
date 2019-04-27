---
title: /INCLUDE (Symbolverweise erzwingen)
ms.date: 11/04/2016
f1_keywords:
- /include
- VC.Project.VCLinkerTool.ForceSymbolReferences
helpviewer_keywords:
- INCLUDE linker option
- force symbol references linker option
- symbol references linker force
- /INCLUDE linker option
- symbols, add to symbol table
- -INCLUDE linker option
ms.assetid: 4a039677-360a-480f-bd0b-448e239b449c
ms.openlocfilehash: 1f7a443e32ed20550e3017c7e6ce70f4adf5137d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62269869"
---
# <a name="include-force-symbol-references"></a>/INCLUDE (Symbolverweise erzwingen)

```
/INCLUDE:symbol
```

## <a name="parameters"></a>Parameter

*symbol*<br/>
Gibt ein Symbol der Symboltabelle hinzugefügt werden.

## <a name="remarks"></a>Hinweise

Die/Include-Option weist den Linker an, der Symboltabelle ein bestimmtes Symbol hinzuzufügen.

Um mehrere Symbole anzugeben, geben Sie ein Komma (,), ein Semikolon (;) oder ein Leerzeichen zwischen den Symbolnamen. Geben Sie in der Befehlszeile/include:`symbol` einmal für jedes Symbol.

Der Linker löst `symbol` durch Hinzufügen des Objekts, das die Definition des Symbols für das Programm enthält. Diese Funktion ist nützlich für die Einbindung eines Bibliotheksobjekts, das andernfalls nicht zu dem Programm verknüpft werden.

Ein Symbol angeben, wenn diese Option überschreibt das Entfernen dieses Symbols durch [/OPT: REF](opt-optimizations.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Klicken Sie auf die **Linker** Ordner.

1. Klicken Sie auf die **Eingabe** Eigenschaftenseite.

1. Ändern der **Symbolverweise** Eigenschaft.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ForceSymbolReferences%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Linkerreferenz](linking.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)

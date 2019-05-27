---
title: /CLRIMAGETYPE (Angeben des CLR-Bildtyps)
ms.date: 05/16/2019
f1_keywords:
- /CLRIMAGETYPE
- VC.Project.VCLinkerTool.CLRImageType
helpviewer_keywords:
- /CLRIMAGETYPE linker option
- -CLRIMAGETYPE linker option
ms.assetid: 04c60ee6-9dd7-4391-bc03-6926ad0fa116
ms.openlocfilehash: ee2e2ce359a4b877551adf9af71e0187b42cfd42
ms.sourcegitcommit: a10c9390413978d36b8096b684d5ed4cf1553bc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2019
ms.locfileid: "65837482"
---
# <a name="clrimagetype-specify-type-of-clr-image"></a>/CLRIMAGETYPE (Angeben des CLR-Bildtyps)

Legen Sie den CLR-Imagetyp im verknüpften Image fest.

## <a name="syntax"></a>Syntax

> **/CLRIMAGETYPE:** {**IJW**|**PURE**|**SAFE**|**SAFE32BITPREFERRED**}

## <a name="remarks"></a>Anmerkungen

Der Linker akzeptiert systemeigene Objekte und auch MSIL-Objekte, die mit [/clr](clr-common-language-runtime-compilation.md) kompiliert werden. Die Compileroptionen **/clr:pure** und **/clr:safe** sind in Visual Studio 2015 veraltet und werden in Visual Studio 2017 und höher nicht unterstützt. Bei der Übergabe gemischter Objekte im selben Build entspricht die Überprüfbarkeit der erstellten Ausgabedatei standardmäßig der geringsten Überprüfbarkeitsstufe der Eingabemodule. Wenn Sie beispielsweise ein systemeigenes Image und ein Image im gemischten Modus (mit **/clr** kompiliert) übergeben, ist das resultierende Image ein Image im gemischten Modus.

Mit **/CLRIMAGETYPE** können Sie eine niedrige Überprüfbarkeitsstufe angeben, wenn dies erforderlich ist.

Weitere Informationen zum Bestimmen des CLR-Imagetyps einer Datei finden Sie unter [/CLRHEADER](clrheader.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen erhalten Sie unter [Set C++ compiler and build properties in Visual Studio (Festlegen der Compiler- und Buildeigenschaften (C++) in Visual Studio)](../working-with-project-properties.md).

1. Erweitern Sie den Knoten **Konfigurationseigenschaften**.

1. Erweitern Sie den Knoten **Linker**.

1. Wählen Sie die Eigenschaftenseite **Erweitert** aus.

1. Ändern Sie die Eigenschaft **CLR-Imagetyp**.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

1. Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRImageType%2A>.

## <a name="see-also"></a>Siehe auch

- [MSVC-Linkerreferenz](linking.md)
- [MSVC-Linkeroptionen](linker-options.md)

---
title: /CLRIMAGETYPE (Angeben des CLR-Bildtyps)
ms.date: 11/04/2016
f1_keywords:
- /CLRIMAGETYPE
- VC.Project.VCLinkerTool.CLRImageType
helpviewer_keywords:
- /CLRIMAGETYPE linker option
- -CLRIMAGETYPE linker option
ms.assetid: 04c60ee6-9dd7-4391-bc03-6926ad0fa116
ms.openlocfilehash: b2a6df0f778ba079bffefeeacdad22cb398a529a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62272480"
---
# <a name="clrimagetype-specify-type-of-clr-image"></a>/CLRIMAGETYPE (Angeben des CLR-Bildtyps)

Legen Sie die CLR-Imagetyp, in das verknüpfte Bild.

## <a name="syntax"></a>Syntax

> **/CLRIMAGETYPE:**{**IJW**|**PURE**|**SAFE**|**SAFE32BITPREFERRED**}

## <a name="remarks"></a>Hinweise

Der Linker akzeptiert systemeigene Objekte und auch MSIL-Objekte, die kompiliert werden, mithilfe von ["/ CLR"](clr-common-language-runtime-compilation.md). Die **/CLR: pure** und **/CLR: safe** Compileroptionen wurden in Visual Studio 2015 als veraltet markiert und werden in Visual Studio 2017 nicht unterstützt. Bei der Übergabe gemischter Objekte im selben Build entspricht die Überprüfbarkeit der erstellten Ausgabedatei standardmäßig der geringsten Überprüfbarkeitsstufe der Eingabemodule. Z. B., wenn Sie ein systemeigenes Image und ein Image im gemischten Modus übergeben (kompiliert mit **"/ CLR"**), das resultierende Image wird ein Image im gemischten Modus.

Sie können **/CLRIMAGETYPE** eine niedrigere Ebene Überprüfbarkeitsstufe angeben, ist dies die benötigten.

Weitere Informationen zum Bestimmen des CLR-Imagetyps einer Datei finden Sie unter [/CLRHEADER](clrheader.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Erweitern Sie den Knoten **Konfigurationseigenschaften**.

1. Erweitern Sie die **Linker** Knoten.

1. Wählen Sie die **erweitert** Eigenschaftenseite.

1. Ändern der **CLR-Imagetyp** Eigenschaft.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

1. Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRImageType%2A>.

## <a name="see-also"></a>Siehe auch

- [MSVC-Linkerreferenz](linking.md)
- [MSVC-Linkeroptionen](linker-options.md)

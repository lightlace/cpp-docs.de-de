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
ms.openlocfilehash: c4cdb9a9ac3376762d6aa40fd4c13abbdc7b5487
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50461632"
---
# <a name="clrimagetype-specify-type-of-clr-image"></a>/CLRIMAGETYPE (Angeben des CLR-Bildtyps)

Legen Sie die CLR-Imagetyp, in das verknüpfte Bild.

## <a name="syntax"></a>Syntax

> **/ CLRIMAGETYPE:**{**IJW**|**REINER**|**SICHER**|**SAFE32BITPREFERRED**}

## <a name="remarks"></a>Hinweise

Der Linker akzeptiert systemeigene Objekte und auch MSIL-Objekte, die kompiliert werden, mithilfe von ["/ CLR"](../../build/reference/clr-common-language-runtime-compilation.md). Die **/CLR: pure** und **/CLR: safe** Compileroptionen wurden in Visual Studio 2015 als veraltet markiert und werden in Visual Studio 2017 nicht unterstützt. Bei der Übergabe gemischter Objekte im selben Build entspricht die Überprüfbarkeit der erstellten Ausgabedatei standardmäßig der geringsten Überprüfbarkeitsstufe der Eingabemodule. Z. B., wenn Sie ein systemeigenes Image und ein Image im gemischten Modus übergeben (kompiliert mit **"/ CLR"**), das resultierende Image wird ein Image im gemischten Modus.

Sie können **/CLRIMAGETYPE** eine niedrigere Ebene Überprüfbarkeitsstufe angeben, ist dies die benötigten.

Weitere Informationen zum Bestimmen des CLR-Imagetyps einer Datei finden Sie unter [/CLRHEADER](../../build/reference/clrheader.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Erweitern Sie den Knoten **Konfigurationseigenschaften**.

1. Erweitern Sie die **Linker** Knoten.

1. Wählen Sie die **erweitert** Eigenschaftenseite.

1. Ändern der **CLR-Imagetyp** Eigenschaft.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

1. Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRImageType%2A>.

## <a name="see-also"></a>Siehe auch

- [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)
- [Linkeroptionen](../../build/reference/linker-options.md)

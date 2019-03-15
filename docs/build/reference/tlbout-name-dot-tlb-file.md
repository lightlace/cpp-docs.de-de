---
title: /TLBOUT (TLB-Datei benennen)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.TypeLibraryFile
- /tlbout
helpviewer_keywords:
- tlb files, renaming
- TLBOUT linker option
- /TLBOUT linker option
- .tlb files, renaming
- -TLBOUT linker option
ms.assetid: 0df6d078-2e48-46c9-a1a5-02674d85dce8
ms.openlocfilehash: 4e04514933a521bbf9d927fa6b47bacb87896353
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57822261"
---
# <a name="tlbout-name-tlb-file"></a>/TLBOUT (TLB-Datei benennen)

```
/TLBOUT:[path\]filename
```

## <a name="arguments"></a>Argumente

*path*<br/>
Eine Spezifikation der absoluten oder relativen Pfad für die, in dem die TLB-Datei erstellt werden soll.

*filename*<br/>
Gibt den Namen der TLB-Datei, die vom MIDL-Compiler erstellt. Keine Dateierweiterung wird davon ausgegangen, dass; Geben Sie *Filename*tlb, wenn Sie die Erweiterung ".tlb" möchten.

## <a name="remarks"></a>Hinweise

Die/TLBOUT-Option gibt den Namen und die Erweiterung der TLB-Datei.

Der MIDL-Compiler wird vom Linker MSVC aufgerufen, wenn das Verknüpfen von Projekten, die die [Modul](../../windows/module-cpp.md) Attribut.

Wenn/TLBOUT nicht angegeben ist, erhalten die TLB-Datei den Namen [/IDLOUT](idlout-name-midl-output-files.md) *Filename*. Wenn die/IDLOUT nicht angegeben ist, wird die TLB-Datei vc70.tlb aufgerufen werden.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Klicken Sie auf die **Linker** Ordner.

1. Klicken Sie auf die **eingebettete IDL** Eigenschaftenseite.

1. Ändern der **Typbibliothek** Eigenschaft.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

1. Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TypeLibraryFile%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Linker-Referenz](linking.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)<br/>
[/IGNOREIDL (Attribute nicht in MIDL verarbeiten)](ignoreidl-don-t-process-attributes-into-midl.md)<br/>
[/MIDL (MIDL-Befehlszeilenoptionen angeben)](midl-specify-midl-command-line-options.md)<br/>
[Erstellen eines attributierten Programms](../../windows/building-an-attributed-program.md)

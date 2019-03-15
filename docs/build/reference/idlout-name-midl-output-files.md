---
title: /IDLOUT (Namen der MIDL-Ausgabedateien)
ms.date: 11/04/2016
f1_keywords:
- /idlout
- VC.Project.VCLinkerTool.MergedIDLBaseFileName
helpviewer_keywords:
- MIDL, output file names
- .idl files, path
- MIDL
- /IDLOUT linker option
- IDL files, path
- -IDLOUT linker option
- IDLOUT linker option
ms.assetid: 10d00a6a-85b4-4de1-8732-e422c6931509
ms.openlocfilehash: 3816bb85cb3c711075e3fefeec2d706c2f8cc2ff
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57821468"
---
# <a name="idlout-name-midl-output-files"></a>/IDLOUT (Namen der MIDL-Ausgabedateien)

```
/IDLOUT:[path\]filename
```

## <a name="parameters"></a>Parameter

*path*<br/>
Ein absoluter oder relativer Pfad-Spezifikation. Durch Angabe eines Pfads, wirkt sich aus lediglich der Speicherort der einer IDL-Datei. Alle anderen Dateien befinden sich im Projektverzeichnis.

*filename*<br/>
Gibt den Namen der IDL-Datei, die vom MIDL-Compiler erstellt. Keine Dateierweiterung wird davon ausgegangen, dass; Geben Sie *Filename*IDL ggf. eine IDL-Erweiterung.

## <a name="remarks"></a>Hinweise

Die/IDLOUT-Option gibt den Namen und die Erweiterung der IDL-Datei.

Der MIDL-Compiler wird vom Linker MSVC aufgerufen, wenn das Verknüpfen von Projekten, die die [Modul](../../windows/module-cpp.md) Attribut.

/ IDLOUT gibt auch an die Dateinamen der anderen Ausgabedateien der MIDL-Compiler zugeordnet:

- *filename*.tlb

- *filename*_p.c

- *filename*_i.c

- *filename*.h

*FileName* ist der Parameter, die an/IDLOUT übergeben. Wenn [/TLBOUT](tlbout-name-dot-tlb-file.md) angegeben ist, wird die TLB-Datei erhält den Namen von/TLBOUT *Filename*.

Wenn Sie weder die/IDLOUT als auch die/TLBOUT angeben, erstellt der Linker vc70.tlb, vc70.idl, vc70_p.c, vc70_i.c und vc70.h.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Klicken Sie auf die **Linker** Ordner.

1. Klicken Sie auf die **eingebettete IDL** Eigenschaftenseite.

1. Ändern der **Merge IDL-Basisdateiname** Eigenschaft.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MergedIDLBaseFileName%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Linker-Referenz](linking.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)<br/>
[/IGNOREIDL (Attribute nicht in MIDL verarbeiten)](ignoreidl-don-t-process-attributes-into-midl.md)<br/>
[/MIDL (MIDL-Befehlszeilenoptionen angeben)](midl-specify-midl-command-line-options.md)<br/>
[Erstellen eines attributierten Programms](../../windows/building-an-attributed-program.md)

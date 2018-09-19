---
title: -IDLOUT (Namen der MIDL-Ausgabedateien) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /idlout
- VC.Project.VCLinkerTool.MergedIDLBaseFileName
dev_langs:
- C++
helpviewer_keywords:
- MIDL, output file names
- .idl files, path
- MIDL
- /IDLOUT linker option
- IDL files, path
- -IDLOUT linker option
- IDLOUT linker option
ms.assetid: 10d00a6a-85b4-4de1-8732-e422c6931509
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a6749b59a1c12b5d7c3116a925adc727ad6f7ab5
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45721837"
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

Der MIDL-Compiler wird durch den Visual C++-Linker aufgerufen, wenn das Verknüpfen von Projekten, die die [Modul](../../windows/module-cpp.md) Attribut.

/ IDLOUT gibt auch an die Dateinamen der anderen Ausgabedateien der MIDL-Compiler zugeordnet:

- *FileName*TLB-Datei

- *FileName*_p.c

- *FileName*_i.c

- *FileName*h

*FileName* ist der Parameter, die an/IDLOUT übergeben. Wenn [/TLBOUT](../../build/reference/tlbout-name-dot-tlb-file.md) angegeben ist, wird die TLB-Datei erhält den Namen von/TLBOUT *Filename*.

Wenn Sie weder die/IDLOUT als auch die/TLBOUT angeben, erstellt der Linker vc70.tlb, vc70.idl, vc70_p.c, vc70_i.c und vc70.h.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Klicken Sie auf die **Linker** Ordner.

1. Klicken Sie auf die **eingebettete IDL** Eigenschaftenseite.

1. Ändern der **Merge IDL-Basisdateiname** Eigenschaft.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MergedIDLBaseFileName%2A>.

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)<br/>
[/ IGNOREIDL (Attribute nicht in verarbeiten MIDL)](../../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)
[/MIDL (MIDL-Befehlszeilenoptionen angeben)](../../build/reference/midl-specify-midl-command-line-options.md)
[Erstellen eines attributierten Programms](../../windows/building-an-attributed-program.md)
---
title: /MIDL (Optionen für MIDL-Befehlszeile festlegen)
ms.date: 09/05/2018
f1_keywords:
- /midl
- VC.Project.VCLinkerTool.MidlCommandFile
helpviewer_keywords:
- -MIDL linker option
- MIDL
- /MIDL linker option
- MIDL linker option
- MIDL, command line options
ms.assetid: 22dc259e-b34c-4ed3-a380-4beb734482c1
ms.openlocfilehash: 584958ac51bdc491ad1bdd16117ecaad6e000ec7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62321071"
---
# <a name="midl-specify-midl-command-line-options"></a>/MIDL (Optionen für MIDL-Befehlszeile festlegen)

Legt eine Antwortdatei für die Optionen für MIDL-Befehlszeile

## <a name="syntax"></a>Syntax

> **/MIDL:\@**<em>file</em>

## <a name="arguments"></a>Argumente

*datei*<br/>
Der Name der Datei, die enthält [MIDL-Befehlszeilenoptionen](/windows/desktop/Midl/general-midl-command-line-syntax).

## <a name="remarks"></a>Hinweise

Bei allen Optionen für die Konvertierung einer IDL-Datei in eine TLB-Datei zugewiesen werden, der *Datei*; MIDL-Befehlszeilenoptionen können nicht auf dem Linker Befehlszeile angegeben werden. Wenn/MIDL nicht angegeben ist, wird der MIDL-Compiler mit nur den IDL-Dateinamen und keine anderen Optionen aufgerufen werden.

Die Datei sollte eine MIDL-Befehlszeilenoption pro Zeile enthalten.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **Linker** > **eingebettete IDL** Eigenschaftenseite.

1. Ändern der **MIDL-Befehle** Eigenschaft.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MidlCommandFile%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Linkerreferenz](linking.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)<br/>
[/IDLOUT (Namen der MIDL-Ausgabedateien)](idlout-name-midl-output-files.md)<br/>
[/IGNOREIDL (Attribute nicht in MIDL verarbeiten)](ignoreidl-don-t-process-attributes-into-midl.md)<br/>
[/TLBOUT (TLB-Datei benennen)](tlbout-name-dot-tlb-file.md)<br/>
[Erstellen eines attributierten Programms](../../windows/building-an-attributed-program.md)

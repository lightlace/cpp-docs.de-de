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
ms.openlocfilehash: ca172428943d2446490eeb10741966f5e8c9ea85
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492722"
---
# <a name="midl-specify-midl-command-line-options"></a>/MIDL (Optionen für MIDL-Befehlszeile festlegen)

Gibt eine Antwortdatei für die Mittel l-Befehlszeilenoptionen an.

## <a name="syntax"></a>Syntax

> **/MIDL:\@** <em>file</em>

## <a name="arguments"></a>Argumente

*datei*<br/>
Der Name der Datei, die die [Befehlszeilenoptionen](/windows/win32/Midl/general-midl-command-line-syntax)in der Mitte enthält.

## <a name="remarks"></a>Hinweise

Alle Optionen für die Konvertierung einer IDL-Datei in eine TLB-Datei müssen in der *Datei*angegeben werden. In der Befehlszeile des Linkers können keine Mittell-Befehlszeilenoptionen angegeben werden. Wenn/MIDL nicht angegeben ist, wird der Mittelwert Compiler nur mit dem IDL-Dateinamen und ohne weitere Optionen aufgerufen.

Die Datei sollte eine mittlere Befehlszeilenoption pro Zeile enthalten.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen erhalten Sie unter [Set C++ compiler and build properties in Visual Studio (Festlegen der Compiler- und Buildeigenschaften (C++) in Visual Studio)](../working-with-project-properties.md).

1. Wählen Sie die Eigenschaften Seite für den**Linker** > **Embedded IDL** der **Konfigurations Eigenschaften** > aus.

1. Ändern Sie die Eigenschaft " **Mittel l-Befehle** ".

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MidlCommandFile%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Linkerreferenz](linking.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)<br/>
[/IDLOUT (Namen der MIDL-Ausgabedateien)](idlout-name-midl-output-files.md)<br/>
[/IGNOREIDL (Attribute nicht in MIDL verarbeiten)](ignoreidl-don-t-process-attributes-into-midl.md)<br/>
[/TLBOUT (TLB-Datei benennen)](tlbout-name-dot-tlb-file.md)<br/>
[Erstellen eines attributierten Programms](../../windows/building-an-attributed-program.md)

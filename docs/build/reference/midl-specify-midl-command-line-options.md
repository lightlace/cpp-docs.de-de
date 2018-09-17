---
title: -MIDL (MIDL-Befehlszeilenoptionen angeben) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/05/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /midl
- VC.Project.VCLinkerTool.MidlCommandFile
dev_langs:
- C++
helpviewer_keywords:
- -MIDL linker option
- MIDL
- /MIDL linker option
- MIDL linker option
- MIDL, command line options
ms.assetid: 22dc259e-b34c-4ed3-a380-4beb734482c1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ce4c5159a66963268ae83e0c0adfdc082dfcc81c
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45706939"
---
# <a name="midl-specify-midl-command-line-options"></a>/MIDL (Optionen für MIDL-Befehlszeile festlegen)

Legt eine Antwortdatei für die Optionen für MIDL-Befehlszeile

## <a name="syntax"></a>Syntax

> **/ MIDL:\@**<em>Datei</em>

## <a name="arguments"></a>Argumente

*datei*<br/>
Der Name der Datei, die enthält [MIDL-Befehlszeilenoptionen](/windows/desktop/Midl/general-midl-command-line-syntax).

## <a name="remarks"></a>Hinweise

Bei allen Optionen für die Konvertierung einer IDL-Datei in eine TLB-Datei zugewiesen werden, der *Datei*; MIDL-Befehlszeilenoptionen können nicht auf dem Linker Befehlszeile angegeben werden. Wenn/MIDL nicht angegeben ist, wird der MIDL-Compiler mit nur den IDL-Dateinamen und keine anderen Optionen aufgerufen werden.

Die Datei sollte eine MIDL-Befehlszeilenoption pro Zeile enthalten.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).

2. Wählen Sie die **Konfigurationseigenschaften** > **Linker** > **eingebettete IDL** Eigenschaftenseite.

3. Ändern der **MIDL-Befehle** Eigenschaft.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MidlCommandFile%2A>.

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)<br/>
[/ IDLOUT (Namen der MIDL-Ausgabedateien)](../../build/reference/idlout-name-midl-output-files.md)
[/IGNOREIDL (Attribute nicht in verarbeiten MIDL)](../../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)
 [ /TLBOUT (Name. TLB-Datei)](../../build/reference/tlbout-name-dot-tlb-file.md)
[Erstellen eines attributierten Programms](../../windows/building-an-attributed-program.md)
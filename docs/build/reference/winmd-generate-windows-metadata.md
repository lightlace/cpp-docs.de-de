---
title: /WINMD (Windows-Metadaten generieren)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.GenerateWindowsMetadata
ms.assetid: bcfb4901-411e-4c9e-9f78-23028b6e5fcc
ms.openlocfilehash: 45d6492c87b7543a54d031f02dcf09e319150131
ms.sourcegitcommit: 28eae422049ac3381c6b1206664455dbb56cbfb6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2019
ms.locfileid: "66449724"
---
# <a name="winmd-generate-windows-metadata"></a>/WINMD (Windows-Metadaten generieren)

Aktiviert die Generierung einer Windows-Runtime-Metadatendatei (.winmd)-Datei.

> **/WINMD**\[ **:** {**NO**\|**ONLY**}]

## <a name="arguments"></a>Argumente

**/WINMD**<br/>
Die Standardeinstellung für die universelle Windows-Plattform-apps. Der Linker generiert sowohl die binäre ausführbare Datei als auch die winmd-Metadaten-Datei.

**/WINMD:NO**<br/>
Der Linker wird nur die binäre ausführbare Datei, aber nicht in eine winmd-Datei generiert.

**/WINMD:ONLY**<br/>
Der Linker wird nur die winmd-Datei, aber nicht die binäre ausführbare Datei generiert.

## <a name="remarks"></a>Hinweise

Die **/WINMD** -Linkeroption wird für UWP-apps und Windows-Runtime-Komponenten verwendet, um die Erstellung einer Windows-Runtime-Metadatendatei (.winmd) zu steuern. Eine winmd-Datei ist eine Art von DLL, die Metadaten für Windows-Runtime-Typen und im Fall von Runtime-Komponenten, die Implementierungen dieser Typen enthält. Die Metadaten folgen der [ECMA-335](https://www.ecma-international.org/publications/standards/Ecma-335.htm) standard.

Standardmäßig den Namen der Ausgabedatei hat das Format *Binaryname*winmd. Um einen anderen Dateinamen anzugeben, verwenden die [/winmdfile](winmdfile-specify-winmd-file.md) Option.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen erhalten Sie unter [Set C++ compiler and build properties in Visual Studio (Festlegen der Compiler- und Buildeigenschaften (C++) in Visual Studio)](../working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **Linker** > **Windows-Metadaten** Eigenschaftenseite.

1. In der **Windows-Metadaten generieren** Dropdown-Liste Wählen Sie die gewünschte Option.

## <a name="see-also"></a>Siehe auch

[Exemplarische Vorgehensweise: Erstellen einer einfachen Windows-Runtime-Komponente, und es über JavaScript aufrufen](/windows/uwp/winrt-components/walkthrough-creating-a-simple-windows-runtime-component-and-calling-it-from-javascript)<br/>
[Einführung in die Microsoft Interface Definition Language 3.0](/uwp/midl-3/intro)<br/>
[/WINMDFILE (WINMD-Datei angeben)](winmdfile-specify-winmd-file.md)<br/>
[/WINMDKEYFILE (WINMD-Schlüsseldatei angeben)](winmdkeyfile-specify-winmd-key-file.md)<br/>
[/WINMDKEYCONTAINER (Schlüsselcontainer angeben)](winmdkeycontainer-specify-key-container.md)<br/>
[/WINMDDELAYSIGN (WINMD-Datei teilweise signieren)](winmddelaysign-partially-sign-a-winmd.md)<br/>
[MSVC-Linkerreferenz](linking.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)

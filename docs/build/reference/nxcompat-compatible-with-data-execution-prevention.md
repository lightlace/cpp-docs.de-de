---
title: /NXCOMPAT (kompatibel mit Datenausführungsverhinderung)
description: Beschreibt die Option "MicrosoftC++ C/(MSVC)/NXCOMPAT Linker", die eine ausführbare Datei als kompatibel mit der Daten Ausführungs Verhinderung (Data Execution Prevention, DEP) kennzeichnet.
ms.date: 12/17/2019
f1_keywords:
- /NXCOMPAT
helpviewer_keywords:
- /NXCOMPAT linker option
- -NXCOMPAT linker option
- NXCOMPAT linker option
ms.openlocfilehash: f3a0906a49e3524fff3e1ef1643d1eceee28f169
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75298986"
---
# <a name="nxcompat-compatible-with-data-execution-prevention"></a>/NXCOMPAT (kompatibel mit Datenausführungsverhinderung)

Gibt an, dass eine ausführbare Datei mit der Windows-Funktion zur Daten Ausführungs Verhinderung kompatibel ist.

## <a name="syntax"></a>Syntax

> **/NXCOMPAT**[ **:NO**]

## <a name="remarks"></a>Hinweise

Standardmäßig ist **/NXCOMPAT** auf ON eingestellt.

**/NXCOMPAT: Nein** kann verwendet werden, um eine ausführbare Datei explizit als inkompatibel mit der Daten Ausführungs Verhinderung anzugeben.

Weitere Informationen über die Datenausführungsverhinderung finden Sie in diesen Artikeln:

- [Verhinderung von Datenausführung](/windows/win32/Memory/data-execution-prevention)

- [Verhinderung von Datenausführung (Windows Embedded)](/previous-versions/windows/embedded/ms913190\(v=winembedded.5\))

### <a name="to-set-this-linker-option-in-visual-studio"></a>So legen Sie diese Linkeroption in Visual Studio fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen erhalten Sie unter [Set C++ compiler and build properties in Visual Studio (Festlegen der Compiler- und Buildeigenschaften (C++) in Visual Studio)](../working-with-project-properties.md).

1. Wählen Sie die Eigenschaften Seite " **Konfigurations Eigenschaften** > **Linker** > **Befehlszeile** " aus.

1. Geben Sie die Option im Feld **zusätzliche Optionen** ein. Wählen Sie **OK** oder **anwenden** aus, um die Änderung zu übernehmen.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-linkerverweis](linking.md)\
[MSVC-Linkeroptionen](linker-options.md)

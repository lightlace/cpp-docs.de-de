---
title: /NXCOMPAT (kompatibel mit Datenausführungsverhinderung)
ms.date: 12/29/2017
f1_keywords:
- /NXCOMPAT
helpviewer_keywords:
- /NXCOMPAT linker option
- -NXCOMPAT linker option
- NXCOMPAT linker option
ms.openlocfilehash: 7c788f5ec499f0edf0c44f1ff269af9767af6c08
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492664"
---
# <a name="nxcompat-compatible-with-data-execution-prevention"></a>/NXCOMPAT (kompatibel mit Datenausführungsverhinderung)

Gibt an, dass eine ausführbare Datei mit der Windows-Funktion zur Daten Ausführungs Verhinderung kompatibel ist.

## <a name="syntax"></a>Syntax

> **/NXCOMPAT**[ **:NO**]

## <a name="remarks"></a>Hinweise

Standardmäßig ist **/NXCOMPAT** auf ON eingestellt.

**/NXCOMPAT: Nein** kann verwendet werden, um eine ausführbare Datei explizit als inkompatibel mit der Daten Ausführungs Verhinderung anzugeben.

Weitere Informationen über die Datenausführungsverhinderung finden Sie in diesen Artikeln:

- [Eine ausführliche Beschreibung der Funktion zur Daten Ausführungs Verhinderung (Data Execution Prevention, DEP)](https://support.microsoft.com/help/875352/a-detailed-description-of-the-data-execution-prevention-dep-feature-in)

- [Verhinderung von Datenausführung](/windows/win32/Memory/data-execution-prevention)

- [Verhinderung von Datenausführung (Windows Embedded)](/previous-versions/windows/embedded/ms913190\(v=winembedded.5\))

### <a name="to-set-this-linker-option-in-visual-studio"></a>So legen Sie diese Linkeroption in Visual Studio fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen erhalten Sie unter [Set C++ compiler and build properties in Visual Studio (Festlegen der Compiler- und Buildeigenschaften (C++) in Visual Studio)](../working-with-project-properties.md).

1.  > Wählen Sie die Eigenschaften Seite der Linkerbefehlszeile der **Konfigurations Eigenschaften** > .

1. Geben Sie die Option im Feld **zusätzliche Optionen** ein. Wählen Sie **OK** oder **anwenden** aus, um die Änderung zu übernehmen.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Linkerreferenz](linking.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)

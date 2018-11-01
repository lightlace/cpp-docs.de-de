---
title: /NXCOMPAT (kompatibel mit Datenausführungsverhinderung)
ms.date: 12/29/2017
f1_keywords:
- /NXCOMPAT
helpviewer_keywords:
- /NXCOMPAT linker option
- -NXCOMPAT linker option
- NXCOMPAT linker option
ms.openlocfilehash: 815719468e7dcf9325d19efe879b8f4ace040094
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50490492"
---
# <a name="nxcompat-compatible-with-data-execution-prevention"></a>/NXCOMPAT (kompatibel mit Datenausführungsverhinderung)

Gibt an, dass eine ausführbare Datei mit der Windows-Datenausführungsverhinderung kompatibel ist.

## <a name="syntax"></a>Syntax

> **/ NXCOMPAT**[**: NO**]

## <a name="remarks"></a>Hinweise

In der Standardeinstellung **/NXCOMPAT** ist.

**: No** können verwendet werden, um eine ausführbare Datei explizit als nicht kompatibel mit Datenausführungsverhinderung angeben.

Weitere Informationen über die Datenausführungsverhinderung finden Sie in diesen Artikeln:

- [Eine ausführliche Beschreibung des Features (Data Execution Prevention, DEP)](https://support.microsoft.com/help/875352/a-detailed-description-of-the-data-execution-prevention-dep-feature-in)

- [Datenausführungsverhinderung](/windows/desktop/Memory/data-execution-prevention)

- [Datenausführungsverhinderung (Windows Embedded)](/previous-versions/windows/embedded/ms913190\(v=winembedded.5\))

### <a name="to-set-this-linker-option-in-visual-studio"></a>So legen Sie diese Linkeroption in Visual Studio fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **Linker** > **Befehlszeile** Eigenschaftenseite.

1. Geben Sie die Option in der **zusätzliche Optionen** Feld. Wählen Sie **OK** oder **übernehmen** um die Änderung zu übernehmen.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)

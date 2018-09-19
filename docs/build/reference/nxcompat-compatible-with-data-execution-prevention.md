---
title: / NXCOMPAT (kompatibel mit Datenausführungsverhinderung) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 12/29/2017
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /NXCOMPAT
dev_langs:
- C++
helpviewer_keywords:
- /NXCOMPAT linker option
- -NXCOMPAT linker option
- NXCOMPAT linker option
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 52cf47335c1bed55ca38d508789d65902b335f0f
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45707628"
---
# <a name="nxcompat-compatible-with-data-execution-prevention"></a>/NXCOMPAT (kompatibel mit Datenausführungsverhinderung)

Gibt an, dass eine ausführbare Datei mit der Windows-Datenausführungsverhinderung kompatibel ist.

## <a name="syntax"></a>Syntax

> **/ NXCOMPAT**[**: NO**]

## <a name="remarks"></a>Hinweise

In der Standardeinstellung **/NXCOMPAT** ist.

**: No** können verwendet werden, um eine ausführbare Datei explizit als nicht kompatibel mit Datenausführungsverhinderung angeben.

Weitere Informationen über die Datenausführungsverhinderung finden Sie in diesen Artikeln:

- [Eine ausführliche Beschreibung des Features (Data Execution Prevention, DEP)](https://support.microsoft.com/en-us/help/875352/a-detailed-description-of-the-data-execution-prevention-dep-feature-in)

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

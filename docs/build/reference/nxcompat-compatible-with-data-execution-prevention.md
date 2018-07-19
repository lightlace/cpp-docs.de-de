---
title: / NXCOMPAT (kompatibel mit Datenausführungsverhinderung) | Microsoft Docs
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
ms.openlocfilehash: bb4f8a91545a196bc92fdc0ec44e89a7d5680185
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32374803"
---
# <a name="nxcompat-compatible-with-data-execution-prevention"></a>/NXCOMPAT (kompatibel mit Datenausführungsverhinderung)

Gibt an, dass eine ausführbare Datei mit der Funktion zur Datenausführungsverhinderung kompatibel ist.

## <a name="syntax"></a>Syntax

> **/ NXCOMPAT**[**: NO**]

## <a name="remarks"></a>Hinweise

Standardmäßig **NXCOMPAT** befindet sich auf.

**/NXCOMPAT:No** können verwendet werden, um eine ausführbare Datei explizit als nicht kompatibel mit Datenausführungsverhinderung angeben.

Weitere Informationen über die Datenausführungsverhinderung finden Sie in diesen Artikeln:

- [Eine ausführliche Beschreibung der Funktion (Data Execution Prevention, DEP)](http://go.microsoft.com/fwlink/p/?linkid=157771)

- [Datenausführungsverhinderung](http://go.microsoft.com/fwlink/p/?linkid=157770)

- [Datenausführungsverhinderung (Windows Embedded)](http://go.microsoft.com/fwlink/p/?linkid=157768)

### <a name="to-set-this-linker-option-in-visual-studio"></a>So legen Sie diese Linkeroption in Visual Studio fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **Linker** > **Befehlszeile** Eigenschaftenseite.

1. Geben Sie die Option in der **Zusatzoptionen** Feld. Wählen Sie **OK** oder **übernehmen** um die Änderung zu übernehmen.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)  
[Linkeroptionen](../../build/reference/linker-options.md)  

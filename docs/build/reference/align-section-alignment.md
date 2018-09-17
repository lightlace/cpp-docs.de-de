---
title: / ALIGN (Abschnittsausrichtung) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 12/29/2017
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.Alignment
- /align
dev_langs:
- C++
helpviewer_keywords:
- sections, specifying alignment
- ALIGN linker option
- /ALIGN linker option
- -ALIGN linker option
- section alignment
- sections
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cb92d4b16be7903004831ffb25e2891f498a8989
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45718249"
---
# <a name="align-section-alignment"></a>/ALIGN (Abschnittsausrichtung)

## <a name="syntax"></a>Syntax

> **/ ALIGN**[**:**_Anzahl_]

### <a name="arguments"></a>Argumente

*Anzahl*<br/>
Der Ausrichtungswert in Byte.

## <a name="remarks"></a>Hinweise

Die **/ALIGN** Option gibt die Ausrichtung der einzelnen Abschnitten im linearen Adressbereich des Programms an. Die *Anzahl* Argument in Bytes und muss eine Potenz von zwei sein. Der Standardwert ist 4 KB (4096). Der Linker gibt eine Warnung aus, wenn die Ausrichtung auf ein ungültiges Bild erzeugt.

Wenn Sie eine Anwendung z. B. einen Gerätetreiber schreiben, sollten Sie nicht die Ausrichtung ändern möchten.

Es ist möglich, ändern Sie die Ausrichtung eines bestimmten Abschnitts mit dem Ausrichtungsparameter, um die [/SECTION](../../build/reference/section-specify-section-attributes.md) Option.

Der Ausrichtungswert, die Sie angeben, darf nicht kleiner als die größte abschnittsausrichtung sein.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **Linker** > **Befehlszeile** Eigenschaftenseite.

1. Geben Sie die Option in der **zusätzliche Optionen** Feld. Wählen Sie **OK** oder **übernehmen** um die Änderung zu übernehmen.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)

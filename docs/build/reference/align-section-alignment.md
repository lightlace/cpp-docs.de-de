---
title: / ALIGN (Abschnittsausrichtung) | Microsoft Docs
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
ms.openlocfilehash: 543ea30b06f62939f378167d8598c73f66061f46
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="align-section-alignment"></a>/ALIGN (Abschnittsausrichtung)

## <a name="syntax"></a>Syntax

> **/ ALIGN**[**:**_Anzahl_]

### <a name="arguments"></a>Argumente

*Anzahl*  
Der Ausrichtungswert in Bytes.

## <a name="remarks"></a>Hinweise

Die **/AUSRICHTEN** Option gibt die Ausrichtung eines Abschnitts innerhalb des linearen Adressraums des Programms an. Die *Anzahl* Argument in Bytes und muss eine Potenz von zwei sein. Der Standardwert ist 4 KB (4096). Der Linker gibt eine Warnung aus, wenn die Ausrichtung einer ungültigen Abbild erzeugt.

Wenn Sie eine Anwendung z. B. ein Gerätetreiber schreiben, müssen Sie nicht die Ausrichtung zu ändern.

Es ist möglich, ändern Sie die Ausrichtung eines bestimmten Bereichs mit dem Ausrichtungsparameter, um die [/SECTION](../../build/reference/section-specify-section-attributes.md) Option.

Der Ausrichtungswert, die Sie angeben, darf nicht kleiner als die größte abschnittsausrichtung sein.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **Linker** > **Befehlszeile** Eigenschaftenseite.

1. Geben Sie die Option in der **Zusatzoptionen** Feld. Wählen Sie **OK** oder **übernehmen** um die Änderung zu übernehmen.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)  
[Linkeroptionen](../../build/reference/linker-options.md)  

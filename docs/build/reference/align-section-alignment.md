---
title: /ALIGN (Abschnittsausrichtung)
ms.date: 12/29/2017
f1_keywords:
- VC.Project.VCLinkerTool.Alignment
- /align
helpviewer_keywords:
- sections, specifying alignment
- ALIGN linker option
- /ALIGN linker option
- -ALIGN linker option
- section alignment
- sections
ms.openlocfilehash: d8d2e6a859c68af473d49dc04b76f0a15056aa56
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62295265"
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

Es ist möglich, ändern Sie die Ausrichtung eines bestimmten Abschnitts mit dem Ausrichtungsparameter, um die [/SECTION](section-specify-section-attributes.md) Option.

Der Ausrichtungswert, die Sie angeben, darf nicht kleiner als die größte abschnittsausrichtung sein.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **Linker** > **Befehlszeile** Eigenschaftenseite.

1. Geben Sie die Option in der **zusätzliche Optionen** Feld. Wählen Sie **OK** oder **übernehmen** um die Änderung zu übernehmen.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Linkerreferenz](linking.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)

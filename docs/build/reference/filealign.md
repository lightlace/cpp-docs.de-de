---
title: / FILEALIGN (Abschnitte in Dateien ausrichten)
ms.date: 10/23/2017
f1_keywords:
- /filealign
helpviewer_keywords:
- linker align sections
- /FILEALIGN linker option
- -FILEALIGN linker option
- FILEALIGN linker option
ms.assetid: c1017a35-8d71-4ad9-934b-a3e3ea037fa0
ms.openlocfilehash: d218ce4793e68fe3b700a0776fa5db665568f736
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50494579"
---
# <a name="filealign-align-sections-in-files"></a>/ FILEALIGN (Abschnitte in Dateien ausrichten)

Die **/filealign** Linkeroption können Sie die Ausrichtung der Abschnitte in Ihrer Ausgabedatei geschrieben werden, als ein Vielfaches von einer angegebenen Größe angeben.

## <a name="syntax"></a>Syntax

> __/ FILEALIGN:__*Größe*

### <a name="parameters"></a>Parameter

*size*<br/>
Der Abschnitt Ausrichtungsgröße in Bytes, die eine Potenz von zwei sein muss.

## <a name="remarks"></a>Hinweise

Die **/filealign** Option bewirkt, dass der Linker jeder Abschnitt in der Ausgabedatei an einer Begrenzung ausgerichtet werden, die ein Vielfaches von ist das *Größe* Wert. Standardmäßig verwendet der Linker eine feste Ausrichtung-Größe nicht.

Die **/filealign** Option kann verwendet werden, um die datenträgernutzung effizienter zu gestalten oder zu der Seite vom Datenträger wird schneller geladen. Eine kleinere Abschnittsgröße kann für apps nützlich sein, die auf kleineren Geräten oder auf Downloads kleiner halten, ausgeführt. Abschnittsausrichtung auf dem Datenträger hat keine Auswirkungen auf die Ausrichtung im Arbeitsspeicher.

Verwenden Sie [DUMPBIN](dumpbin-reference.md), um Informationen über Abschnitte in Ihrer Ausgabedatei anzuzeigen.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Befehlszeile** Eigenschaftenseite in der **Linker** Ordner.

1. Geben Sie den Optionsnamen **/filealign:** und die Größe in der **zusätzliche Optionen** Feld.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)
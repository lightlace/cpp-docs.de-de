---
title: / FILEALIGN (Align Abschnitte Dateien) | Microsoft Docs
ms.date: 10/23/2017
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /filealign
dev_langs:
- C++
helpviewer_keywords:
- linker align sections
- /FILEALIGN linker option
- -FILEALIGN linker option
- FILEALIGN linker option
ms.assetid: c1017a35-8d71-4ad9-934b-a3e3ea037fa0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c8a737801663a2c7c1e896166291a1635fbbe6c4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="filealign-align-sections-in-files"></a>/ FILEALIGN (Align-Abschnitte in Dateien)

Die **/filealign** (Linkeroption) können Sie die Ausrichtung der Abschnitte der Ausgabedatei geschrieben, als ein Vielfaches von einer angegebenen Größe angeben.

## <a name="syntax"></a>Syntax

> __/ FILEALIGN:__*Größe*

### <a name="parameters"></a>Parameter

*size*  
Der Abschnitt Ausrichtungsgröße in Bytes, die einer Potenz von zwei sein muss.

## <a name="remarks"></a>Hinweise

Die **/filealign** Option bewirkt, dass den Linker jeder Abschnitt in der Ausgabedatei an einer Begrenzung ausgerichtet, die ein Vielfaches von ist das *Größe* Wert. Standardmäßig verwendet der Linker eine feste Ausrichtungsgröße nicht.

Die **/filealign** Option kann verwendet werden, um die datenträgernutzung effizienter gestaltet werden, oder auf der Seite vom Datenträger wird schneller geladen. Eine geringere Abschnittsgröße an kann für apps nützlich sein, die auf kleinen Geräten oder Downloads kleinere beibehalten ausgeführt. Abschnittsausrichtung auf dem Datenträger wirkt sich nicht auf die Ausrichtung im Arbeitsspeicher aus.

Verwenden Sie [DUMPBIN](dumpbin-reference.md), um Informationen über Abschnitte in Ihrer Ausgabedatei anzuzeigen.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Befehlszeile** Eigenschaftenseite in der **Linker** Ordner.

1. Geben Sie den Optionsnamen **/filealign:** und die Größe in der **Zusatzoptionen** Feld.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
[Linkeroptionen](../../build/reference/linker-options.md)
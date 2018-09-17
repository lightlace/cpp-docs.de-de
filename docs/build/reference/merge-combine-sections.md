---
title: -MERGE (Abschnitte kombinieren) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /merge
- VC.Project.VCLinkerTool.MergeSections
dev_langs:
- C++
helpviewer_keywords:
- sections, combining
- /MERGE linker option
- sections, naming
- sections
- -MERGE linker option
- MERGE linker option
ms.assetid: 10fb20c2-0b3f-4c8d-98a8-f69aedf03d52
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 01768ffcfd647d3e05c0b96647d544e3d68e77d0
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45722662"
---
# <a name="merge-combine-sections"></a>/MERGE (Abschnitte kombinieren)

```
/MERGE:from=to
```

## <a name="remarks"></a>Hinweise

Die Option "/ Merge" kombiniert den ersten Abschnitt (*aus*) mit dem zweiten Abschnitt (*zu*), den so entstehende Abschnitt Benennung *zu*. Beispielsweise `/merge:.rdata=.text`.

Wenn der zweite Abschnitt nicht vorhanden ist, benennt der LINK im Abschnitt *aus* als *zu*.

Die Option "/ Merge" eignet sich zum Erstellen von VxDs und überschreiben die vom Compiler generierter Abschnittsnamen.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Klicken Sie auf die **Linker** Ordner.

1. Klicken Sie auf die **erweitert** Eigenschaftenseite.

1. Ändern der **Abschnitte zusammenfügen** Eigenschaft.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

1. Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MergeSections%2A>.

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)
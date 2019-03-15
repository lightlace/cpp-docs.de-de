---
title: /WX (Linkerwarnungen als Fehler behandeln)
ms.date: 11/04/2016
f1_keywords:
- /WX
helpviewer_keywords:
- /WX linker option
- -WX linker option
- WX linker option
ms.assetid: e4ba97c7-93f7-43ae-a4bb-d866790926c9
ms.openlocfilehash: b4b29ed364d39c5f105dded703b8530c08db35e6
ms.sourcegitcommit: faa42c8a051e746d99dcebe70fd4bbaf3b023ace
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2019
ms.locfileid: "57822092"
---
# <a name="wx-treat-linker-warnings-as-errors"></a>/WX (Linkerwarnungen als Fehler behandeln)

```
/WX[:NO]
```

## <a name="remarks"></a>Hinweise

/ WX bewirkt, dass keine Ausgabedatei generiert werden, wenn der Linker eine Warnung generiert wird.

Dies ist vergleichbar mit **/WX** für den Compiler (finden Sie unter [/w, / W0, / W1, / W2, / w3, / W4, / W1, / W2, / w3, / W4, / Wall, / WD, / we, / wo, / WV, / WX (Warnstufe)](compiler-option-warning-level.md) Informationen). Angeben von jedoch **/WX** für die Kompilierung, die nicht impliziert **/WX** werden auch in Kraft für die Linkphase; Sie müssen explizit angeben **/WX** für jedes Tool.

In der Standardeinstellung **/WX** ist nicht aktiv. Um linkerwarnungen als Fehler behandelt werden soll, geben Sie **/WX**. **/WX:No** ist derselbe, als wenn nicht **/WX**.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Klicken Sie auf die **Linker** Ordner.

1. Klicken Sie auf die Eigenschaftenseite **Befehlszeile** .

1. Geben Sie die Option in der **zusätzliche Optionen** Feld.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

1. Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Linker-Referenz](linking.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)

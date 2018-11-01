---
title: /ALLOWBIND (DLL-Bindung verhindern)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.PreventDLLBinding
- /allowbind
helpviewer_keywords:
- /ALLOWBIND linker option
- binding DLLs
- preventing DLL binding
- ALLOWBIND linker option
- -ALLOWBIND linker option
- DLLs [C++], preventing binding
ms.assetid: 30e37e24-12e4-407e-988a-39d357403598
ms.openlocfilehash: ffe32a1df1fb85c7ae47b07c1ada6c53b269f5f9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50667297"
---
# <a name="allowbind-prevent-dll-binding"></a>/ALLOWBIND (DLL-Bindung verhindern)

```
/ALLOWBIND[:NO]
```

## <a name="remarks"></a>Hinweise

/ALLOWBIND:NO legt ein Bit im Header einer DLL fest, das Bind.exe darauf hinweist, dass das Image nicht gebunden werden darf. Möglicherweise möchten Sie nicht, dass eine DLL gebunden wird, wenn sie digital signiert wurde (die Bindung macht die Signatur ungültig).

Sie können eine vorhandene DLL für die/ALLOWBIND-Funktionalität mit Bearbeiten der [/ALLOWBIND](../../build/reference/allowbind.md) Option des EDITBIN-Hilfsprogramms.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Erweitern Sie **Konfigurationseigenschaften**, **Linker**, und wählen Sie **Befehlszeile**.

1. Geben Sie `/ALLOWBIND:NO` in **zusätzliche Optionen**.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)<br/>
[BindImage-Funktion](/windows/desktop/api/imagehlp/nf-imagehlp-bindimage)<br/>
[BindImageEx-Funktion](/windows/desktop/api/imagehlp/nf-imagehlp-bindimageex)
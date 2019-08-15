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
ms.openlocfilehash: d963a7145ab2e8c8872dc21c485bdc8f877b0b76
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69493148"
---
# <a name="allowbind-prevent-dll-binding"></a>/ALLOWBIND (DLL-Bindung verhindern)

```
/ALLOWBIND[:NO]
```

## <a name="remarks"></a>Hinweise

/ALLOWBIND:NO legt ein Bit im Header einer DLL fest, das Bind.exe darauf hinweist, dass das Image nicht gebunden werden darf. Möglicherweise möchten Sie nicht, dass eine DLL gebunden wird, wenn sie digital signiert wurde (die Bindung macht die Signatur ungültig).

Sie können eine vorhandene DLL-Datei für die/ALLOWBIND-Funktionalität mit der [/ALLOWBIND](allowbind.md) -Option des EDITBIN-Hilfsprogramms bearbeiten.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen erhalten Sie unter [Set C++ compiler and build properties in Visual Studio (Festlegen der Compiler- und Buildeigenschaften (C++) in Visual Studio)](../working-with-project-properties.md).

1. Erweitern Sie **Konfigurations Eigenschaften**, **Linker**, und wählen Sie die **Befehlszeile**aus.

1. Geben `/ALLOWBIND:NO` Sie **zusätzliche Optionen**ein.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Linkerreferenz](linking.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)<br/>
[BindImage-Funktion](/windows/win32/api/imagehlp/nf-imagehlp-bindimage)<br/>
[BindImageEx-Funktion](/windows/win32/api/imagehlp/nf-imagehlp-bindimageex)

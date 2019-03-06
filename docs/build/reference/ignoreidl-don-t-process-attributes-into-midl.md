---
title: / IGNOREIDL (Don&#39;t Prozessattribute in MIDL)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.IgnoreEmbeddedIDL
- /ignoreidl
helpviewer_keywords:
- IGNOREIDL linker option
- -IGNOREIDL linker option
- /IGNOREIDL linker option
ms.assetid: 29514098-6a1c-4317-af2f-1dc268972780
ms.openlocfilehash: 1a78f99f61bbeff9c5d617fce374925d0541aafd
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57423156"
---
# <a name="ignoreidl-don39t-process-attributes-into-midl"></a>/ IGNOREIDL (Don&#39;t Prozessattribute in MIDL)

```
/IGNOREIDL
```

## <a name="remarks"></a>Hinweise

Die/IGNOREIDL-Option gibt an, dass jede [IDL-Attribute](../../windows/idl-attributes.md) in Quelle sollten Code nicht in einer IDL-Datei verarbeitet werden.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Klicken Sie auf die **Linker** Ordner.

1. Klicken Sie auf die **eingebettete IDL** Eigenschaftenseite.

1. Ändern der **Eingebettetes IDL ignorieren** Eigenschaft.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreEmbeddedIDL%2A>.

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)<br/>
[/IDLOUT (Namen der MIDL-Ausgabedateien)](../../build/reference/idlout-name-midl-output-files.md)<br/>
[/TLBOUT (TLB-Datei benennen)](../../build/reference/tlbout-name-dot-tlb-file.md)<br/>
[/MIDL (MIDL-Befehlszeilenoptionen angeben)](../../build/reference/midl-specify-midl-command-line-options.md)<br/>
[Erstellen eines attributierten Programms](../../windows/building-an-attributed-program.md)

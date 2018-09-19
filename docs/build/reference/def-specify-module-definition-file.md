---
title: -DEF (Moduldefinitionsdatei festlegen) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.ModuleDefinitionFile
- /def
dev_langs:
- C++
helpviewer_keywords:
- module definition files, specifying
- DEF linker option
- -DEF linker option
- module definition files
- /DEF linker option
ms.assetid: 6497fa68-65f0-48ca-8f66-b87166fc631a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0ec7458f5b81dd2b9d5aac49959b935f49377081
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45720395"
---
# <a name="def-specify-module-definition-file"></a>/DEF (Moduldefinitionsdatei festlegen)

```
/DEF:filename
```

## <a name="arguments"></a>Argumente

*filename*<br/>
Der Name des eine Moduldefinitionsdatei (.def) an den Linker übergeben werden.

## <a name="remarks"></a>Hinweise

Die/DEF-Option übergibt eine Moduldefinitionsdatei (.def) an den Linker an. Link kann nur eine DEF-Datei angegeben werden. Weitere Informationen über die DEF-Dateien, finden Sie unter [Moduldefinitionsdateien](../../build/reference/module-definition-dot-def-files.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Klicken Sie auf die **Linker** Ordner.

1. Klicken Sie auf die **Eingabe** Eigenschaftenseite.

1. Ändern der **Moduldefinitionsdatei** Eigenschaft.

Um eine DEF-Datei aus, in der Entwicklungsumgebung anzugeben, sollten Sie das Projekt zusammen mit anderen Dateien hinzufügen und geben dann die Datei an die/DEF-Option.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ModuleDefinitionFile%2A>.

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)
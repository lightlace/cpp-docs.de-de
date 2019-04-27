---
title: /DEF (Moduldefinitionsdatei festlegen)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.ModuleDefinitionFile
- /def
helpviewer_keywords:
- module definition files, specifying
- DEF linker option
- -DEF linker option
- module definition files
- /DEF linker option
ms.assetid: 6497fa68-65f0-48ca-8f66-b87166fc631a
ms.openlocfilehash: c08412fb50835485e7941b2bb1db088943387b71
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62272307"
---
# <a name="def-specify-module-definition-file"></a>/DEF (Moduldefinitionsdatei festlegen)

```
/DEF:filename
```

## <a name="arguments"></a>Argumente

*filename*<br/>
Der Name des eine Moduldefinitionsdatei (.def) an den Linker übergeben werden.

## <a name="remarks"></a>Hinweise

Die/DEF-Option übergibt eine Moduldefinitionsdatei (.def) an den Linker an. Link kann nur eine DEF-Datei angegeben werden. Weitere Informationen über die DEF-Dateien, finden Sie unter [Moduldefinitionsdateien](module-definition-dot-def-files.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Klicken Sie auf die **Linker** Ordner.

1. Klicken Sie auf die **Eingabe** Eigenschaftenseite.

1. Ändern der **Moduldefinitionsdatei** Eigenschaft.

Um eine DEF-Datei aus, in der Entwicklungsumgebung anzugeben, sollten Sie das Projekt zusammen mit anderen Dateien hinzufügen und geben dann die Datei an die/DEF-Option.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ModuleDefinitionFile%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Linkerreferenz](linking.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)

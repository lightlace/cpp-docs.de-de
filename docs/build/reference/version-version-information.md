---
title: /VERSION (Versionsinformationen)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.Version
- /version
helpviewer_keywords:
- -VERSION linker option
- Version Information linker option
- version numbers, specifying in .exe
- /VERSION linker option
- VERSION linker option
ms.assetid: b86d0e86-dca6-4316-aee2-d863ccb9f223
ms.openlocfilehash: 709ba836fb537fbcb594f7eb6aa2f2d43df5b4d1
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57414706"
---
# <a name="version-version-information"></a>/VERSION (Versionsinformationen)

```
/VERSION:major[.minor]
```

## <a name="arguments"></a>Argumente

*wichtige* und *kleinere*<br/>
Die Versionsnummer im Header des .exe oder .dll-Datei die gewünschten.

## <a name="remarks"></a>Hinweise

Die/Version-Option weist den Linker an, eine Versionsnummer im Header des .exe oder .dll-Datei zu speichern. Verwenden von DUMPBIN [/Headers](../../build/reference/headers.md) können Sie die Image-Version von OPTIONAL HEADER VALUES, die Auswirkung von/Version anzuzeigen.

Die *wichtigen* und *kleinere* Argumente sind Dezimalzahlen im Bereich von 0 bis 65.535. Der Standardwert ist 0.0.

Die mit/Version angegebene Informationen wirkt sich nicht auf die Versionsinformationen aus, die für eine Anwendung angezeigt wird, wenn Sie die Eigenschaften im Datei-Explorer anzeigen. Diese Informationen stammen aus einer Ressourcendatei, die zum Erstellen der Anwendung verwendet wird. Finden Sie unter [Versionsinfo-Editor](../../windows/version-information-editor.md) für Weitere Informationen.

Eine weitere Möglichkeit zum Einfügen einer Versionsnummer wird mit der [VERSION](../../build/reference/version-c-cpp.md) Moduldefinitionsdatei-Anweisung.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Klicken Sie auf die **Linker** Ordner.

1. Klicken Sie auf die **allgemeine** Eigenschaftenseite.

1. Ändern der **Version** Eigenschaft.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.Version%2A>.

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)

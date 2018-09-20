---
title: -Fm (Name der Zuordnungsdatei) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /fm
dev_langs:
- C++
helpviewer_keywords:
- -Fm compiler option [C++]
- mapfiles [C++], creating linker
- files [C++], creating map
- Fm compiler option [C++]
- /Fm compiler option [C++]
ms.assetid: 8154448a-93a7-4546-8e4c-5c44d0aff45d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bce549cd782c8d79066b16d2e3791ba906e9c4f9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46410532"
---
# <a name="fm-name-mapfile"></a>/Fm (Name der Zuordnungsdatei)

Weist den Linker erstellen eine Zuordnungsdatei mit der eine Liste der Segmente in der Reihenfolge, in der sie in der entsprechenden .exe-Datei oder DLL angezeigt werden.

## <a name="syntax"></a>Syntax

```
/Fmpathname
```

## <a name="remarks"></a>Hinweise

Standardmäßig erhält die Map-Name der Basisname der entsprechenden C- oder C++-Quelldatei mit ein. Zuordnungs-Erweiterung.

Angeben von **/FM** hat denselben Effekt, als ob Sie angegeben haben die [/Map (Zuordnungsdatei generieren)](../../build/reference/map-generate-mapfile.md) -Linkeroption.

Bei Angabe von [/c (Kompilieren ohne Verknüpfen)](../../build/reference/c-compile-without-linking.md) zu unterdrücken, verknüpfen, **/FM** hat keine Auswirkungen.

Globale Symbole in einer Zuordnungsdatei haben in der Regel eine oder mehrere führende Unterstriche, da der Compiler einen führenden Unterstrich Variablennamen hinzugefügt wird. Viele globale Symbole, die in der Map-Datei angezeigt werden, werden intern vom Compiler und die standard-Bibliotheken verwendet.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Klicken Sie auf den Ordner **C/C++** .

1. Klicken Sie auf die Eigenschaftenseite **Befehlszeile** .

1. Geben Sie die Compileroption im Feld **Zusätzliche Optionen** ein.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[Ausgabedatei (/F) Optionen](../../build/reference/output-file-f-options.md)<br/>
[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)<br/>
[Festlegen des Pfadnamens](../../build/reference/specifying-the-pathname.md)
---
title: /Fm (Name der Zuordnungsdatei)
ms.date: 11/04/2016
f1_keywords:
- /fm
helpviewer_keywords:
- -Fm compiler option [C++]
- mapfiles [C++], creating linker
- files [C++], creating map
- Fm compiler option [C++]
- /Fm compiler option [C++]
ms.assetid: 8154448a-93a7-4546-8e4c-5c44d0aff45d
ms.openlocfilehash: eebb1bc0c553dba1934aea75e2e63edc0f222fff
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62292405"
---
# <a name="fm-name-mapfile"></a>/Fm (Name der Zuordnungsdatei)

Weist den Linker erstellen eine Zuordnungsdatei mit der eine Liste der Segmente in der Reihenfolge, in der sie in der entsprechenden .exe-Datei oder DLL angezeigt werden.

## <a name="syntax"></a>Syntax

```
/Fmpathname
```

## <a name="remarks"></a>Hinweise

Standardmäßig erhält die Map-Name der Basisname der entsprechenden C- oder C++-Quelldatei mit ein. Zuordnungs-Erweiterung.

Angeben von **/FM** hat denselben Effekt, als ob Sie angegeben haben die [/Map (Zuordnungsdatei generieren)](map-generate-mapfile.md) -Linkeroption.

Bei Angabe von [/c (Kompilieren ohne Verknüpfen)](c-compile-without-linking.md) zu unterdrücken, verknüpfen, **/FM** hat keine Auswirkungen.

Globale Symbole in einer Zuordnungsdatei haben in der Regel eine oder mehrere führende Unterstriche, da der Compiler einen führenden Unterstrich Variablennamen hinzugefügt wird. Viele globale Symbole, die in der Map-Datei angezeigt werden, werden intern vom Compiler und die standard-Bibliotheken verwendet.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Klicken Sie auf den Ordner **C/C++** .

1. Klicken Sie auf die Eigenschaftenseite **Befehlszeile** .

1. Geben Sie die Compileroption im Feld **Zusätzliche Optionen** ein.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[Ausgabedatei (/F) Optionen](output-file-f-options.md)<br/>
[MSVC-Compileroptionen](compiler-options.md)<br/>
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)<br/>
[Festlegen des Pfadnamens](specifying-the-pathname.md)

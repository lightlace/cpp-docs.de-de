---
title: /LINKREPRO (Link-Reproduktion-Verzeichnisname)
description: Die Option Linker oder Bibliotheks Tool, um das Verzeichnis für eine Link Reproduktion festzulegen.
ms.date: 09/24/2019
f1_keywords:
- /LINKREPRO
helpviewer_keywords:
- LINKREPRO linker option
- /LINKREPRO linker option
- -LINKREPRO linker option
- linker repro reporting
ms.openlocfilehash: d81fb529cdbb0741c6dff58032dad97df89b4d4f
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2019
ms.locfileid: "71686917"
---
# <a name="linkrepro-link-repro-directory-name"></a>/LINKREPRO (Link-Reproduktion-Verzeichnisname)

Weist den Linker oder das Bibliotheks Tool an, eine Link Reproduktion in einem angegebenen Verzeichnis zu generieren.

## <a name="syntax"></a>Syntax

> **/LINKREPRO:** _Verzeichnisname_

### <a name="arguments"></a>Argumente

**/LINKREPRO:** _Verzeichnisname_\
Das vom Benutzer angegebene Verzeichnis, in dem die Link Reproduktion gespeichert werden soll. Verzeichnisnamen, die Leerzeichen enthalten, müssen in doppelte Anführungszeichen eingeschlossen werden.

## <a name="remarks"></a>Hinweise

Die **/LINKREPRO** -Option wird zum Erstellen einer *Link*Reproduktion verwendet. Es handelt sich um einen Satz von buildartefakte, mit denen Microsoft ein Problem reproduzieren kann, das bei der Verknüpfungs Zeit oder bei Bibliotheks Vorgängen auftritt. Dies ist nützlich für Probleme wie z. b. einen Back-End-Absturz, der Link-Zeit Code Generierung (LTCG), einen Linkertoolfehler LNK1000 Linker-Fehler oder einen Linker-Absturz umfasst. Das Tool erzeugt eine Link Reproduktion, wenn Sie die Option **/LINKREPRO** Linker angeben oder wenn Sie die Umgebungsvariable `link_repro` in Ihrer Befehlszeilen-Buildumgebung festlegen. Weitere Informationen finden Sie im Abschnitt [Link](../../overview/how-to-report-a-problem-with-the-visual-cpp-toolset.md#link-repros) Reproduktionen ( [melden eines Problems mit dem C++ Microsoft-Toolset](../../overview/how-to-report-a-problem-with-the-visual-cpp-toolset.md)).

Sowohl die **/LINKREPRO** Linker-Option als auch die `link_repro`-Umgebungsvariable erfordern, dass Sie ein Ausgabeverzeichnis für die Link Reproduktion angeben. Geben Sie in der Befehlszeile oder in der IDE das Verzeichnis mithilfe der Option **/LINKREPRO:** _Directory-Name_ an. Der von Ihnen angegebene _Verzeichnisname_ kann ein absoluter oder relativer Pfad sein, aber das Verzeichnis muss vorhanden sein. Die Befehlszeilenoption überschreibt alle Verzeichnis Werte, die in der `link_repro`-Umgebungsvariablen festgelegt sind.

Informationen dazu, wie Sie die Generierung der Verknüpfungs Reproduktion auf einen bestimmten Ziel Dateinamen beschränken, finden Sie unter der [/LINKREPROTARGET](linkreprotarget.md) -Option. Diese Option kann verwendet werden, um ein bestimmtes Ziel anzugeben, für das eine Link Reproduktion generiert werden soll. Es ist nützlich bei komplexen Builds, die den Linker oder das Bibliotheks Tool mehrmals aufrufen.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen erhalten Sie unter [Set C++ compiler and build properties in Visual Studio (Festlegen der Compiler- und Buildeigenschaften (C++) in Visual Studio)](../working-with-project-properties.md).

1. Wählen Sie die **Eigenschaften Seite Konfigurations Eigenschaften** > **Linker** > **Befehlszeile** aus.

1. Geben Sie im Feld **zusätzliche Optionen** die Option **/LINKREPRO:** _Directory-Name_ ein. Der von Ihnen angegebene Wert für den _Verzeichnisnamen_ muss vorhanden sein. Wählen Sie **OK** aus, um die Änderung zu übernehmen.

Nachdem Sie die Link Reproduktion generiert haben, öffnen Sie diese Eigenschaften Seite erneut, um die **/LINKREPRO** -Option aus ihren Builds zu entfernen.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-linkerverweis](linking.md)\
[MSVC-Linkeroptionen](linker-options.md)\
[/LINKREPROTARGET](linkreprotarget.md)

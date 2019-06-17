---
title: /VERBOSE (Statusmeldungen ausgeben)
ms.date: 06/13/2019
f1_keywords:
- /verbose
- VC.Project.VCLinkerTool.ShowProgress
helpviewer_keywords:
- -VERBOSE linker option
- linking [C++], session progress information
- Print Progress Messages linker option
- linker [C++], output dependency information
- /VERBOSE linker option
- dependencies [C++], dependency information in linker output
- VERBOSE linker option
ms.assetid: 9c347d98-4c37-4724-a39e-0983934693ab
ms.openlocfilehash: bbf7b5966c741535f26202979cbfd71f839cc537
ms.sourcegitcommit: e79188287189b76b34eb7e8fb1bfe646bdb586bc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2019
ms.locfileid: "67141670"
---
# <a name="verbose-print-progress-messages"></a>/VERBOSE (Statusmeldungen ausgeben)

Ausgaben von statusmeldungen bei der Verknüpfung.

## <a name="syntax"></a>Syntax

> **/VERBOSE**\[ **:** {**CLR**|**ICF**|**INCR**|**LIB**|**REF**|**SAFESEH**|**UNUSEDDELAYLOAD**|**UNUSEDLIBS**}\]

## <a name="remarks"></a>Hinweise

Der Linker sendet Informationen über den Status des Verknüpfungsvorgangs an das **Ausgabe** Fenster. In der Befehlszeile die Informationen an die Standardausgabe gesendet und kann in eine Datei umgeleitet werden.

| Option | Beschreibung |
| ------------ | ----------------- |
| /VERBOSE | Zeigt Einzelheiten über den Verknüpfungsvorgang an. |
| /VERBOSE:CLR | Zeigt Informationen zu bestimmten Linkeraktivität an Objekte und Metadaten, die mit kompiliert ["/ CLR"](clr-common-language-runtime-compilation.md). |
| /VERBOSE:ICF | Zeigt Informationen über die Linkeraktivität an, die durch die Verwendung von entsteht [/OPT: ICF](opt-optimizations.md). |
| /VERBOSE:INCR | Zeigt Informationen über den inkrementellen Verknüpfungsvorgang an. |
| /VERBOSE:LIB | Zeigt Statusmeldungen an, die sich nur auf die durchsuchten Bibliotheken beziehen.<br/> Die angezeigten Informationen umfassen den Suchvorgang Bibliothek. Jede Bibliothek und den Objektnamen an (mit vollständigem Pfad) aufgeführt, das Symbol aufgelöst wird aus der Bibliothek und eine Liste von Objekten, die auf das Symbol verweisen. |
| /VERBOSE:REF | Zeigt Informationen über die Linkeraktivität an, die durch die Verwendung von entsteht [/OPT: REF](opt-optimizations.md). |
| /VERBOSE:SAFESEH | Zeigt Informationen zu Modulen, die nicht kompatibel mit safe structured Exception handling, wenn [/SAFESEH](safeseh-image-has-safe-exception-handlers.md) nicht angegeben ist. |
| /VERBOSE:UNUSEDDELAYLOAD | Zeigt Informationen zu einer Verzögerung geladen, DLLs, die keine Symbole verwendet, wenn das Image erstellt wird. |
| /VERBOSE:UNUSEDLIBS | Zeigt Informationen über alle Bibliotheksdateien an, die nicht verwendet werden, wenn das Image erstellt wird. |

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen erhalten Sie unter [Set C++ compiler and build properties in Visual Studio (Festlegen der Compiler- und Buildeigenschaften (C++) in Visual Studio)](../working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **Linker** > **Befehlszeile** Eigenschaftenseite.

1. Die Option zum Hinzufügen der **zusätzliche Optionen** Feld.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ShowProgress%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Linkerreferenz](linking.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)

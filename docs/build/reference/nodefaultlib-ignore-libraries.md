---
title: /NODEFAULTLIB (Bibliotheken ignorieren)
ms.date: 03/26/2019
f1_keywords:
- VC.Project.VCLinkerTool.OVERWRITEAllDefaultLibraries
- VC.Project.VCLinkerTool.OVERWRITEDefaultLibraryNames
- /nodefaultlib
helpviewer_keywords:
- default libraries, removing
- -NODEFAULTLIB linker option
- libraries, ignore
- NODEFAULTLIB linker option
- /NODEFAULTLIB linker option
- ignore libraries linker option
ms.assetid: 7270b673-6711-468e-97a7-c2925ac2be6e
ms.openlocfilehash: 24528eb4c387c4cd0921ab089370d72b076ad640
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62320515"
---
# <a name="nodefaultlib-ignore-libraries"></a>/NODEFAULTLIB (Bibliotheken ignorieren)

> **/NODEFAULTLIB**[__:__*library*]

## <a name="arguments"></a>Argumente

*library*<br/>
Eine Bibliothek, die den Linker an, zu ignorieren, wenn er externe Verweise aufgelöst werden sollen.

## <a name="remarks"></a>Hinweise

Die/NODEFAULTLIB-Option weist den Linker an, mindestens eine Standardbibliothek aus der Liste der Bibliotheken zu entfernen, die beim Auflösen externer Verweise durchsucht.

Verwenden Sie zum Erstellen einer OBJ-Datei, die keine Verweise auf die Standardbibliotheken enthält [/Zl (Omit Default Library Name)](zl-omit-default-library-name.md).

/ NODEFAULTLIB entfernt standardmäßig alle Standardbibliotheken aus der Liste der Bibliotheken, die beim Auflösen externer Verweise durchsucht. Der optionale *Bibliothek* -Parameter können Sie die eine angegebene Bibliothek aus der Liste der Bibliotheken zu entfernen, beim Auflösen externer Verweise durchsucht. Geben Sie eine/NODEFAULTLIB-Option für jede Bibliothek, die Sie ausschließen möchten.

Der Linker löst Verweise auf externe Definitionen durchsuchen zuerst Bibliotheken, die Sie explizit angeben, und klicken Sie dann in Bibliotheken angegeben, mit der [DEFAULTLIB:](defaultlib-specify-default-library.md) Option, und klicken Sie dann in Bibliotheken mit dem Namen in OBJ-Datei Dateien.

/ NODEFAULTLIB:*Bibliothek* überschreibt die Option:*Bibliothek* wenn gleich *Bibliothek* Namen in beiden angegeben ist.

Wenn Sie die/NODEFAULTLIB verwenden, um das Programm ohne die C-Laufzeitbibliothek zu erstellen, müssen Sie möglicherweise auch [/Entry](entry-entry-point-symbol.md) an die Einstiegspunktfunktion in Ihrem Programm. Weitere Informationen finden Sie unter [CRT Library Features (CRT-Bibliotheksfunktionen)](../../c-runtime-library/crt-library-features.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **Linker** > **Eingabe** Eigenschaftenseite.

1. Wählen Sie die **alle Standardbibliotheken ignorieren** Eigenschaft. Oder geben Sie eine durch Semikolons getrennte Liste der Bibliotheken, die ignoriert werden sollen die **bestimmte Standardbibliotheken ignorieren** Eigenschaft. Die **Befehlszeile** auf der Seite zeigt die Auswirkungen der Änderungen, die Sie, um diese Eigenschaften vornehmen.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Weitere Informationen finden Sie unter <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreDefaultLibraryNames%2A> und <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreAllDefaultLibraries%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Linkerreferenz](linking.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)

---
title: /NODEFAULTLIB (Bibliotheken ignorieren)
ms.date: 11/04/2016
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
ms.openlocfilehash: 12a6e988828d1e4e2dbdc46d49da5ff2fe9e9d8d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50473774"
---
# <a name="nodefaultlib-ignore-libraries"></a>/NODEFAULTLIB (Bibliotheken ignorieren)

```
/NODEFAULTLIB[:library]
```

## <a name="arguments"></a>Argumente

*Bibliothek*<br/>
Eine Bibliothek, die den Linker an, zu ignorieren, wenn er externe Verweise aufgelöst werden sollen.

## <a name="remarks"></a>Hinweise

Die/NODEFAULTLIB-Option weist den Linker an, mindestens eine Standardbibliothek aus der Liste der Bibliotheken zu entfernen, die beim Auflösen externer Verweise durchsucht.

Verwenden Sie zum Erstellen einer OBJ-Datei, die keine Verweise auf die Standardbibliotheken enthält [/Zl (Omit Default Library Name)](../../build/reference/zl-omit-default-library-name.md).

/ NODEFAULTLIB entfernt standardmäßig alle Standardbibliotheken aus der Liste der Bibliotheken, die beim Auflösen externer Verweise durchsucht. Der optionale *Bibliothek* -Parameter können Sie die einer angegebenen Bibliothek oder Bibliotheken aus der Liste der Bibliotheken entfernen beim Auflösen externer Verweise durchsucht. Geben Sie eine/NODEFAULTLIB-Option für jede Bibliothek, die Sie ausschließen möchten.

Der Linker löst Verweise auf externe Definitionen, indem zuerst durchsucht, Bibliotheken, die Sie explizit angeben, und klicken Sie dann in Bibliotheken, die mit der Option/DEFAULTLIB angegeben und dann in den Standardbibliotheken, die mit dem Namen OBJ-Dateien.

/ NODEFAULTLIB:*Bibliothek* überschreibt [DEFAULTLIB:](../../build/reference/defaultlib-specify-default-library.md)*Bibliothek* wenn gleich *Bibliothek* Namen in beiden angegeben ist.

Bei Verwendung von/NODEFAULTLIB z. B. um das Programm ohne die C-Laufzeitbibliothek, erstellen Sie möglicherweise auch [/Entry](../../build/reference/entry-entry-point-symbol.md) in Ihrem Programm Einstiegspunkt (Funktion) an. Weitere Informationen finden Sie unter [CRT Library Features (CRT-Bibliotheksfunktionen)](../../c-runtime-library/crt-library-features.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Klicken Sie auf die **Linker** Ordner.

1. Klicken Sie auf die **Eingabe**Eigenschaftenseite.

1. Wählen Sie die **alle Standardbibliotheken ignorieren** Eigenschaft, oder geben Sie eine Liste der Bibliotheken, die ignoriert werden sollen die **Bibliothek ignorieren** Eigenschaft. Die **Befehlszeile** auf der Seite zeigt die Auswirkungen der Änderungen, die Sie, um diese Eigenschaften vornehmen.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Weitere Informationen finden Sie unter <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreDefaultLibraryNames%2A> und <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreAllDefaultLibraries%2A>.

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)
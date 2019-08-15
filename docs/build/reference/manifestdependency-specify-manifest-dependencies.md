---
title: /MANIFESTDEPENDENCY (Angeben von Manifestabhängigkeiten)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.AdditionalManifestDependencies
helpviewer_keywords:
- MANIFESTDEPENDENCY linker option
- /MANIFESTDEPENDENCY linker option
- -MANIFESTDEPENDENCY linker option
ms.assetid: e4b68313-33a2-4c3e-908e-ac2b9f7d6a73
ms.openlocfilehash: 43239efe70cc555d1a7e03c5d67e99e40ccd480e
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492710"
---
# <a name="manifestdependency-specify-manifest-dependencies"></a>/MANIFESTDEPENDENCY (Angeben von Manifestabhängigkeiten)

```
/MANIFESTDEPENDENCY:manifest_dependency
```

## <a name="remarks"></a>Hinweise

/MANIFESTDEPENDENCY ermöglicht Ihnen das Angeben von Attributen, die in den \<Abhängigkeits > Abschnitt der Manifest-Datei eingefügt werden.

Weitere Informationen zum Erstellen einer Manifest-Datei finden Sie unter [/Manifest (erstellen](manifest-create-side-by-side-assembly-manifest.md) eines parallelen Assemblymanifests).

Weitere Informationen \<zum Abhängigkeits > Abschnitt der Manifest-Datei finden Sie unter [Verleger Konfigurationsdateien](/windows/win32/SbsCs/publisher-configuration-files).

/MANIFESTDEPENDENCY-Informationen können auf zwei Arten an den Linker übermittelt werden:

- Direkt in der Befehlszeile (oder in einer Antwortdatei) mit/MANIFESTDEPENDENCY.

- Über das [comment](../../preprocessor/comment-c-cpp.md) -Pragma.

Das folgende Beispiel zeigt einen/MANIFESTDEPENDENCY-Kommentar, der über das Pragma übermittelt wird.

```cpp
#pragma comment(linker, "\"/manifestdependency:type='Win32' name='Test.Research.SampleAssembly' version='6.0.0.0' processorArchitecture='X86' publicKeyToken='0000000000000000' language='*'\"")
```

Dies führt zu folgendem Eintrag in der Manifest-Datei:

```xml
<dependency>
  <dependentAssembly>
    <assemblyIdentity type='Win32' name='Test.Research.SampleAssembly' version='6.0.0.0' processorArchitecture='X86' publicKeyToken='0000000000000000' language='*' />
  </dependentAssembly>
</dependency>
```

Dieselben/MANIFESTDEPENDENCY-Kommentare können wie folgt an der Befehlszeile übermittelt werden:

```cmd
"/manifestdependency:type='Win32' name='Test.Research.SampleAssembly' version='6.0.0.0' processorArchitecture='X86' publicKeyToken='0000000000000000' language='*'\"
```

Der Linker sammelt/MANIFESTDEPENDENCY-Kommentare, entfernt doppelte Einträge und fügt dann die resultierende XML-Zeichenfolge der Manifest-Datei hinzu.  Wenn der Linker widersprüchliche Einträge findet, wird die Manifestressource beschädigt, und die Anwendung kann nicht gestartet werden (es kann ein Eintrag zum Ereignisprotokoll hinzugefügt werden, der die Fehlerquelle anzeigt).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen erhalten Sie unter [Set C++ compiler and build properties in Visual Studio (Festlegen der Compiler- und Buildeigenschaften (C++) in Visual Studio)](../working-with-project-properties.md).

1. Wählen Sie die **Eigenschaften** > Seite der > linkermanifestressourcendatei aus.

1. Ändern Sie die Eigenschaft **zusätzliche Manifest-Abhängigkeiten** .

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

1. Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalManifestDependencies%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Linkerreferenz](linking.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)

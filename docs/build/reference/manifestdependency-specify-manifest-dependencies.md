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
ms.openlocfilehash: debff86b506545862ce4054bf4e210cdb8a29185
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57418398"
---
# <a name="manifestdependency-specify-manifest-dependencies"></a>/MANIFESTDEPENDENCY (Angeben von Manifestabhängigkeiten)

```
/MANIFESTDEPENDENCY:manifest_dependency
```

## <a name="remarks"></a>Hinweise

/ MANIFESTDEPENDENCY können Sie die Attribute angeben, die aufgenommen werden sollen die \<Dependency > im Abschnitt der Manifestdatei.

Finden Sie unter ["/ manifest" (Create-Seite-an-Seite-Assemblymanifest)](../../build/reference/manifest-create-side-by-side-assembly-manifest.md) Informationen zur Vorgehensweise: Erstellen Sie eine Manifestdatei.

Weitere Informationen zu den \<Abhängigkeit > Abschnitt finden Sie in der Manifestdatei, [Herausgeberkonfigurationsdateien](/windows/desktop/SbsCs/publisher-configuration-files).

/ MANIFESTDEPENDENCY-Informationen können an den Linker auf zwei Arten übergeben werden:

- Direkt in der Befehlszeile (oder in einer Antwortdatei) mit Linkerkommentar.

- Über die [Kommentar](../../preprocessor/comment-c-cpp.md) Pragma.

Das folgende Beispiel zeigt einen Linkerkommentar Kommentar über Pragma übergeben,

```cpp
#pragma comment(linker, "\"/manifestdependency:type='Win32' name='Test.Research.SampleAssembly' version='6.0.0.0' processorArchitecture='X86' publicKeyToken='0000000000000000' language='*'\"")
```

Dadurch ist in den folgenden Eintrag in der Manifestdatei:

```xml
<dependency>
  <dependentAssembly>
    <assemblyIdentity type='Win32' name='Test.Research.SampleAssembly' version='6.0.0.0' processorArchitecture='X86' publicKeyToken='0000000000000000' language='*' />
  </dependentAssembly>
</dependency>
```

Die gleichen Linkerkommentar Kommentare können wie folgt in der Befehlszeile übergeben werden:

```cmd
"/manifestdependency:type='Win32' name='Test.Research.SampleAssembly' version='6.0.0.0' processorArchitecture='X86' publicKeyToken='0000000000000000' language='*'\"
```

Der Linker Linkerkommentar Kommentare sammeln, doppelte Einträge, und klicken Sie dann die resultierende XML-Zeichenfolge zur Manifestdatei hinzufügen.  Wenn der Linker sucht nach widersprüchliche Einträge, die Manifestdatei ist beschädigt, und die Anwendung kann nicht gestartet (ein Eintrag kann hinzugefügt werden im Ereignisprotokoll zu erfassen, der angibt, die Ursache des Fehlers).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **Linker** > **Manifestdatei** Eigenschaftenseite.

1. Ändern der **zusätzliche Manifestabhängigkeiten** Eigenschaft.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

1. Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalManifestDependencies%2A>.

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)

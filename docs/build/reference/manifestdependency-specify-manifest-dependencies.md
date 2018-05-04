---
title: -MANIFESTDEPENDENCY (Angeben von Manifestabhängigkeiten) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.AdditionalManifestDependencies
dev_langs:
- C++
helpviewer_keywords:
- MANIFESTDEPENDENCY linker option
- /MANIFESTDEPENDENCY linker option
- -MANIFESTDEPENDENCY linker option
ms.assetid: e4b68313-33a2-4c3e-908e-ac2b9f7d6a73
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8f9b2de39f5b5340eff22c7e22244aca3d05af67
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="manifestdependency-specify-manifest-dependencies"></a>/MANIFESTDEPENDENCY (Angeben von Manifestabhängigkeiten)
```  
/MANIFESTDEPENDENCY:manifest_dependency  
```  
  
## <a name="remarks"></a>Hinweise  
 / MANIFESTDEPENDENCY können Sie die Attribute angeben, die in platziert werden, wird die \<Abhängigkeit > Abschnitt der Manifestdatei.  
  
 Finden Sie unter ["/ manifest" (Create-Seite-an-Seite-Assemblymanifest)](../../build/reference/manifest-create-side-by-side-assembly-manifest.md) Informationen zum Erstellen einer Manifestdatei.  
  
 Weitere Informationen zu den \<Abhängigkeit > Abschnitt finden Sie in der Manifestdatei, [Herausgeberkonfigurationsdateien](http://msdn.microsoft.com/library/aa375682).  
  
 / MANIFESTDEPENDENCY Informationen können an den Linker in einer von zwei Methoden übergeben werden:  
  
-   Direkt in der Befehlszeile (oder in einer Antwortdatei) mit/MANIFESTDEPENDENCY.  
  
-   Über die [Kommentar](../../preprocessor/comment-c-cpp.md) Pragma.  
  
 Das folgende Beispiel zeigt einen/MANIFESTDEPENDENCY-Kommentar über Pragma,  
  
```  
#pragma comment(linker, "\"/manifestdependency:type='Win32' name='Test.Research.SampleAssembly' version='6.0.0.0' processorArchitecture='X86' publicKeyToken='0000000000000000' language='*'\"")  
```  
  
 Dies führt in den folgenden Eintrag in der Manifestdatei:  
  
```  
<dependency>  
  <dependentAssembly>  
    <assemblyIdentity type='Win32' name='Test.Research.SampleAssembly' version='6.0.0.0' processorArchitecture='X86' publicKeyToken='0000000000000000' language='*' />  
  </dependentAssembly>  
</dependency>  
```  
  
 Die gleichen/MANIFESTDEPENDENCY Kommentare können in der Befehlszeile wie folgt übergeben:  
  
```  
"/manifestdependency:type='Win32' name='Test.Research.SampleAssembly' version='6.0.0.0' processorArchitecture='X86' publicKeyToken='0000000000000000' language='*'\"  
```  
  
 Der Linker erfasst/MANIFESTDEPENDENCY Kommentare, doppelte Einträge, und fügen Sie die resultierende XML-Zeichenfolge in die Manifestdatei hinzu.  Wenn der Linker sucht nach widersprüchliche Einträge, die Manifestdatei beschädigt und die Anwendung kann nicht gestartet (ein Eintrag kann in das Ereignisprotokoll, der angibt, die Ursache des Fehlers hinzugefügt werden).  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Erweitern Sie die **Konfigurationseigenschaften** Knoten.  
  
3.  Erweitern Sie die **Linker** Knoten.  
  
4.  Wählen Sie die **Manifestdatei** Eigenschaftenseite.  
  
5.  Ändern der **zusätzliche Manifest Abhängigkeiten** Eigenschaft.  
  
### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest  
  
1.  Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalManifestDependencies%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)
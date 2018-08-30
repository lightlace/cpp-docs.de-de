---
title: -MANIFESTDEPENDENCY (Manifestabhängigkeiten angeben) | Microsoft-Dokumentation
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
ms.openlocfilehash: d486047b708e0c3412aa63e0a0b026a2a4204f71
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43213898"
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
  
-   Direkt in der Befehlszeile (oder in einer Antwortdatei) mit Linkerkommentar.  
  
-   Über die [Kommentar](../../preprocessor/comment-c-cpp.md) Pragma.  
  
 Das folgende Beispiel zeigt einen Linkerkommentar Kommentar über Pragma übergeben,  
  
```  
#pragma comment(linker, "\"/manifestdependency:type='Win32' name='Test.Research.SampleAssembly' version='6.0.0.0' processorArchitecture='X86' publicKeyToken='0000000000000000' language='*'\"")  
```  
  
 Dadurch ist in den folgenden Eintrag in der Manifestdatei:  
  
```  
<dependency>  
  <dependentAssembly>  
    <assemblyIdentity type='Win32' name='Test.Research.SampleAssembly' version='6.0.0.0' processorArchitecture='X86' publicKeyToken='0000000000000000' language='*' />  
  </dependentAssembly>  
</dependency>  
```  
  
 Die gleichen Linkerkommentar Kommentare können wie folgt in der Befehlszeile übergeben werden:  
  
```  
"/manifestdependency:type='Win32' name='Test.Research.SampleAssembly' version='6.0.0.0' processorArchitecture='X86' publicKeyToken='0000000000000000' language='*'\"  
```  
  
 Der Linker Linkerkommentar Kommentare sammeln, doppelte Einträge, und klicken Sie dann die resultierende XML-Zeichenfolge zur Manifestdatei hinzufügen.  Wenn der Linker sucht nach widersprüchliche Einträge, die Manifestdatei ist beschädigt, und die Anwendung kann nicht gestartet (ein Eintrag kann hinzugefügt werden im Ereignisprotokoll zu erfassen, der angibt, die Ursache des Fehlers).  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).  
  
2.  Erweitern Sie den Knoten **Konfigurationseigenschaften**.  
  
3.  Erweitern Sie die **Linker** Knoten.  
  
4.  Wählen Sie die **Manifestdatei** Eigenschaftenseite.  
  
5.  Ändern der **zusätzliche Manifestabhängigkeiten** Eigenschaft.  
  
### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest  
  
1.  Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalManifestDependencies%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)
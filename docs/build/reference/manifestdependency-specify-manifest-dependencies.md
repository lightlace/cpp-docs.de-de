---
title: "/MANIFESTDEPENDENCY (Angeben von Manifestabh&#228;ngigkeiten)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.AdditionalManifestDependencies"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/MANIFESTDEPENDENCY (Linkeroption)"
  - "MANIFESTDEPENDENCY (Linkeroption)"
  - "-MANIFESTDEPENDENCY (Linkeroption)"
ms.assetid: e4b68313-33a2-4c3e-908e-ac2b9f7d6a73
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# /MANIFESTDEPENDENCY (Angeben von Manifestabh&#228;ngigkeiten)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/MANIFESTDEPENDENCY:manifest_dependency  
```  
  
## Hinweise  
 Mit \/MANIFESTDEPENDENCY können Sie Attribute angeben, die im \<dependency\>\-Abschnitt der Manifestdatei eingefügt werden.  
  
 Unter [\/MANIFEST \(Erstellen eines Manifests für eine parallele Assembly\)](../../build/reference/manifest-create-side-by-side-assembly-manifest.md) finden Sie weitere Informationen zur Erstellung einer Manifestdatei.  
  
 Weitere Informationen zum \<dependency\>\-Abschnitt der Manifestdatei, finden Sie unter [Herausgeber\-Konfigurationsdateien](http://msdn.microsoft.com/library/aa375682).  
  
 Informationen von \/MANIFESTDEPENDENCY können auf zwei Arten an den Linker übergeben werden:  
  
-   Direkt über die Befehlszeile \(bzw. in einer Antwortdatei\) mit \/MANIFESTDEPENDENCY.  
  
-   Über das [comment](../../preprocessor/comment-c-cpp.md)\-Pragma.  
  
 Im folgenden Beispiel wird ein \/MANIFESTDEPENDENCY\-Kommentar gezeigt, der mithilfe des Pragmas  
  
```  
#pragma comment(linker, "\"/manifestdependency:type='Win32' name='Test.Research.SampleAssembly' version='6.0.0.0' processorArchitecture='X86' publicKeyToken='0000000000000000' language='*'\"")  
```  
  
 übergeben wurde. Dies führt zu folgendem Eintrag in der Manifestdatei:  
  
```  
<dependency>  
  <dependentAssembly>  
    <assemblyIdentity type='Win32' name='Test.Research.SampleAssembly' version='6.0.0.0' processorArchitecture='X86' publicKeyToken='0000000000000000' language='*' />  
  </dependentAssembly>  
</dependency>  
```  
  
 Die gleichen \/MANIFESTDEPENDENCY\-Kommentare können über die Befehlszeile folgendermaßen übergeben werden:  
  
```  
"/manifestdependency:type='Win32' name='Test.Research.SampleAssembly' version='6.0.0.0' processorArchitecture='X86' publicKeyToken='0000000000000000' language='*'\"  
```  
  
 \/MANIFESTDEPENDENCY\-Kommentare werden vom Linker gesammelt, doppelte Einträge werden gelöscht, und die sich ergebende XML\-Zeichenfolge wird der Manifestdatei hinzugefügt.  Wenn ein Konflikt zwischen Einträgen auftritt, wird die Manifestdatei beschädigt und die Anwendung kann nicht gestartet werden. \(Möglicherweise wird dem Ereignisprotokoll ein Eintrag mit der Quelle des Fehlers hinzugefügt.\)  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Erweitern Sie den Knoten **Konfigurationseigenschaften**.  
  
3.  Erweitern Sie den Knoten **Linker**.  
  
4.  Wählen Sie die Eigenschaftenseite **Manifestdatei** aus.  
  
5.  Bearbeiten Sie die Eigenschaft **Zusätzliche Manifestabhängigkeiten**.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
1.  Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalManifestDependencies*>.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)
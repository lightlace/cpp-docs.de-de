---
title: "/MANIFEST (Erstellen eines Manifests f&#252;r eine parallele Assembly)"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.GenerateManifest"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/MANIFEST (Linkeroption)"
  - "MANIFEST (Linkeroption)"
  - "-MANIFEST (Linkeroption)"
ms.assetid: 98c52e1e-712c-4f49-b149-4d0a3501b600
caps.latest.revision: 20
caps.handback.revision: "20"
ms.author: "corob"
manager: "ghogen"
---
# /MANIFEST (Erstellen eines Manifests f&#252;r eine parallele Assembly)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/MANIFEST[:{EMBED[,ID=#]|NO}]  
```  
  
## Hinweise  
 \/MANIFEST gibt an, dass der Linker eine parallele Manifestdatei erstellen soll.  Weitere Informationen über Manifestdateien finden Sie in der [Manifestdateienreferenz](http://msdn.microsoft.com/library/aa375632).  
  
 Die Standardeinstellung ist "\/MANIFEST".  
  
 Die \/MANIFEST:EMBED\-Option gibt an, dass der Linker die Manifestdatei im Image als Ressource vom Typ "RT\_MANIFEST" einbetten soll.  Der optionale `ID`\-Parameter ist die Ressourcen\-ID, die für das Manifest verwendet werden soll.  Verwenden Sie den Wert 1 für eine ausführbare Datei.  Verwenden Sie den Wert 2 für eine DLL, damit diese private Abhängigkeiten angeben kann.  Wenn der `ID`\-Parameter nicht angegeben wird, ist der Standardwert 2, wenn die \/DLL\-Option festgelegt wird; andernfalls ist der Standardwert 1.  
  
 Ab [!INCLUDE[vs_orcas_long](../../atl/reference/includes/vs_orcas_long_md.md)] enthalten Manifestdateien für ausführbare Dateien einen Abschnitt, der Informationen zur Benutzerkontensteuerung \(UAC\) angibt.  Wenn Sie "\/MANIFEST" angeben, aber weder [\/MANIFESTUAC](../../build/reference/manifestuac-embeds-uac-information-in-manifest.md) noch [\/DLL](../../build/reference/dll-build-a-dll.md) angeben, wird ein UAC\-Standardfragment mit der UAC\-Ebene *asInvoker* in das Manifest eingefügt.  Weitere Informationen über UAC\-Ebenen finden Sie unter [\/MANIFESTUAC \(bettet UAC\-Informationen in Manifest ein\)](../../build/reference/manifestuac-embeds-uac-information-in-manifest.md).  
  
 Um das UAC\-Standardverhalten zu ändern, führen Sie einen der folgenden Schritte aus:  
  
-   Geben Sie die \/MANIFESTUAC\-Option an, und legen Sie die UAC\-Ebene auf den gewünschten Wert fest.  
  
-   Oder geben Sie die \/MANIFESTUAC:NO\-Option an, wenn Sie im Manifest kein UAC\-Fragment generieren möchten.  
  
 Wenn Sie nicht "\/MANIFEST", aber [\/MANIFESTDEPENDENCY](../../build/reference/manifestdependency-specify-manifest-dependencies.md)\-Kommentare angeben, wird eine Manifestdatei erstellt.  Wenn Sie "\/MANIFEST:NO" angeben, wird keine Manifestdatei erstellt.  
  
 Wenn Sie "\/MANIFEST" angeben, wird der Name der Manifestdatei aus dem Namen der Ausgabedatei und der Endung .MANIFEST zusammengesetzt.  Wenn die Ausgabedatei beispielsweise "MyFile.exe" heißt, hat die Manifestdatei den Namen "MyFile.exe.manifest".  Wenn Sie "\/MANIFESTFILE:*name*" angeben, hat das Manifest den Namen, den Sie in *name* angeben.  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Erweitern Sie den Knoten **Konfigurationseigenschaften**.  
  
3.  Erweitern Sie den Knoten **Linker**.  
  
4.  Wählen Sie die Eigenschaftenseite **Manifestdatei** aus.  
  
5.  Ändern Sie die Eigenschaft **Manifest generieren**.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
1.  Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.GenerateManifest*>.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)
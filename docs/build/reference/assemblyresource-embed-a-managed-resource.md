---
title: "/ASSEMBLYRESOURCE (Verwaltete Ressource einbetten)"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.EmbedManagedResourceFile"
  - "/ASSEMBLYRESOURCE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/ASSEMBLYRESOURCE (Linkeroption)"
  - "Assemblys [C++]"
  - "Assemblys [C++], Verknüpfen von Ressourcendateien"
  - "ASSEMBLYRESOURCE (Linkeroption)"
  - "-ASSEMBLYRESOURCE (Linkeroption)"
ms.assetid: 0ce6e1fb-921b-4b1b-a59c-d35388d789f2
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# /ASSEMBLYRESOURCE (Verwaltete Ressource einbetten)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/ASSEMBLYRESOURCE:filename[,[name][,PRIVATE]]  
```  
  
## Parameter  
 *filename*  
 Die verwaltete Ressource, die in diese Assembly eingebettet werden soll.  
  
 *name*  
 Optional.  Der logische Name der Ressource. Dieser wird zum Laden der Ressource verwendet.  Der Standardwert ist der Dateiname.  
  
 Sie können wahlweise angeben, ob die Datei im Assemblymanifest privat ist.  In der Standardeinstellung ist *name* in der Assembly öffentlich.  
  
## Hinweise  
 Verwenden Sie die Option **\/ASSEMBLYRESOURCE**, um eine Ressource in eine Assembly einzubetten.  
  
 Ressourcen sind in der Assembly öffentlich, wenn sie mit dem Linker erstellt wurden.  Der Linker lässt das Umbenennen der Ressource in der Assembly nicht zu.  
  
 Wenn *filename* eine .NET Framework\-Ressourcendatei \(RESOURCES\-Datei\) ist, die beispielsweise von [Resource File Generator \(Resgen.exe\)](../Topic/Resgen.exe%20\(Resource%20File%20Generator\).md) oder in der Entwicklungsumgebung erstellt wurde, kann sie von Membern im **System.Resources**\-Namespace aufgerufen werden. \(Weitere Informationen finden Sie unter [System.Resources.ResourceManager](https://msdn.microsoft.com/en-us/library/system.resources.resourcemanager.aspx).\)  Für alle anderen Ressourcen verwenden Sie die **GetManifestResource**\*\-Methoden in der **System.Reflection.Assembly**\-Klasse, um die Ressource zur Laufzeit aufzurufen.  
  
 Folgende Linkeroptionen beeinflussen außerdem das Erstellen von Assemblys:  
  
-   [\/ASSEMBLYDEBUG](../../build/reference/assemblydebug-add-debuggableattribute.md)  
  
-   [\/ASSEMBLYLINKRESOURCE](../../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)  
  
-   [\/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)  
  
-   [\/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md)  
  
-   [\/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)  
  
-   [\/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)  
  
-   [\/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Festlegen von Visual C\+\+\-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **Linker**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Eingabe**.  
  
4.  Ändern Sie die Eigenschaft **Verwaltete Ressourcendatei einbetten**.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
1.  Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EmbedManagedResourceFile*>.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)